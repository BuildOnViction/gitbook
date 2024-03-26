---
description: VRC725 is the simplest form of Non-Fungible Token on Viction
---

# VRC725 Specification

VRC725 is the official standard for Non-fungible tokens in Viction ecosystem.

### **Abstract**

The following standard allows for the implementation of a standard API for NFTs within smart contracts. This standard provides basic functionality to track and transfer NFTs.

We considered use cases of NFTs being owned and transacted by individuals as well as consignment to third party brokers/wallets/auctioneers (“operators”). NFTs can represent ownership over digital or physical assets. We considered a diverse universe of assets, and we know you will dream up many more:

* Physical property — houses, unique artwork
* Virtual collectibles — unique pictures of kittens, collectible cards
* “Negative value” assets — loans, burdens and other responsibilities

In general, all houses are distinct and no two kittens are alike. NFTs are _distinguishable_ and you must track the ownership of each one separately.

This standards also support gas-free protocol by enabling mechanism that those protocol can utilize while maintaince the security of the token itself.

### **Motivation**

A standard interface allows wallet/broker/auction applications to work with any NFT on Viction. We provide for simple VRC725 smart contracts as well as contracts that track an _arbitrarily large_ number of NFTs. Additional applications are discussed below.

VRC725 can work both with VictionZ with some limitation, which you can consider, or without VictionZ. The permit extension required by VRC725 is suffient for any gas-less protocol to work with.

### **Specification**

VRC725 is based on ERC721. VRC725 includes IERC721Metadata extension to make it easier for use. Moreorver, it also includes two custom permit implementation inspired by [EIP-4494](https://eips.ethereum.org/EIPS/eip-4494) to support gas-free operation.

```solidity
interface IERC721 is IERC165 {
    event Transfer(address indexed from, address indexed to, uint indexed tokenId);
    event Approval(address indexed owner, address indexed approved, uint indexed tokenId);
    event ApprovalForAll(address indexed owner, address indexed operator, bool approved);

    function balanceOf(address owner) external view returns (uint balance);
    function getApproved(uint tokenId) external view returns (address operator);
    function isApprovedForAll(address owner, address operator) external view returns (bool);
    function ownerOf(uint tokenId) external view returns (address owner);
    function approve(address to, uint tokenId) external;
    function transferFrom(address from, address to, uint tokenId) external;
    function safeTransferFrom(address from, address to, uint tokenId) external;
    function safeTransferFrom(address from, address to, uint tokenId, bytes calldata data) external;
    function setApprovalForAll(address operator, bool _approved) external;
}
```

Source: [IERC721.sol](https://github.com/BuildOnViction/vrc725/blob/main/contracts/interfaces/IERC721.sol)

```solidity
interface IERC721Metadata is IERC721 {
    function name() external view returns (string memory);
    function symbol() external view returns (string memory);
    function tokenURI(uint tokenId) external view returns (string memory);
}
```

Source: [IERC721Metadata.sol](https://github.com/BuildOnViction/vrc725/blob/main/contracts/interfaces/IERC721Metadata.sol)

```solidity
interface IERC4494 is IERC165 {
    function permit(address spender, uint256 tokenId, uint256 deadline, bytes memory sig) external;
    function nonces(uint256 tokenId) external view returns(uint256);
    function DOMAIN_SEPARATOR() external view returns(bytes32);
}
```

Source: [IERC4494.sol](https://github.com/BuildOnViction/vrc725/blob/main/contracts/interfaces/IERC4494.sol)

```solidity
interface IVRC725 is IERC721, IERC4494, IERC721Metadata {
    function permitForAll(address owner, address spender, uint256 deadline, bytes memory signature) external;
    function nonceByAddress(address owner) external view returns(uint256);
}
```

Source: [IVRC725.sol](https://github.com/BuildOnViction/vrc725/blob/main/contracts/interfaces/IVRC725.sol)

**Methods**

* `balanceOf`: Returns the number of tokens in `owner`'s account.

```solidity
function balanceOf(address owner) external view returns (uint balance);
```

* `getApproved`: Returns the account approved for `tokenId` token.

```solidity
function getApproved(uint tokenId) external view returns (address operator);
```

* `isApprovedForAll`: Returns if the `operator` is allowed to manage all of the assets of `owner`.

```solidity
function isApprovedForAll(address owner, address operator) external view returns (bool);
```

* `ownerOf`: Returns the owner of the `tokenId` token.

```solidity
function ownerOf(uint tokenId) external view returns (address owner);
```

* `approve`: Gives permission to `to` to transfer `tokenId` token to another account.

```solidity
function approve(address to, uint tokenId) external;
```

* `transferFrom`: Transfers `tokenId` token from `from` to `to`.

```solidity
function transferFrom(address from, address to, uint tokenId) external;
```

* `safeTransferFrom`: Safely transfers `tokenId` token from `from` to `to`, checking first that contract recipients are aware of the ERC721 protocol to prevent tokens from being forever locked.

```solidity
function safeTransferFrom(address from, address to, uint tokenId) external;
```

* `safeTransferFrom`: Safely transfers `tokenId` token from `from` to `to`.

```solidity
function safeTransferFrom(address from, address to, uint tokenId, bytes calldata data) external;
```

* `setApprovalForAll`: Approve or remove `operator` as an operator for the caller. Operators can call {transferFrom} or {safeTransferFrom} for any token owned by the caller.

```solidity
function setApprovalForAll(address operator, bool _approved) external;
```

* `name`: Returns the token collection name.

```solidity
function name() external view returns (string memory);
```

* `symbol`: Returns the token collection symbol.

```solidity
function symbol() external view returns (string memory);
```

* `tokenURI`: Returns the Uniform Resource Identifier (URI) for `tokenId` token.

```solidity
function tokenURI(uint tokenId) external view returns (string memory);
```

* `estimateFee`: Calculate fee needed to transfer `amount` of tokens.

```solidity
function estimateFee(uint256 value) public view returns (uint256) 
```

* `issuer`:Owner of the token

```solidity
function issuer() public view returns (address) 
```

* `nonces`: Returns the nonce of an NFT - useful for creating permits

```solidity
function nonces(uint256 tokenId) external view override returns(uint256)
```

* `isUsedNonce`: Is used nonce

```solidity
function isUsedNonce(address owner, uint256 nonce) external view returns(bool) 
```

* `minFee`: The amount fee that will be lost when transferring.

```solidity
function minFee() public view returns (uint256)
```

* `permit`: Approve for one `tokenId` by using pre-signed signature, allow other users or smart contract to perform the transfer without `owner` calling approve first.

```solidity
function permit(address spender, uint256 tokenId, uint256 deadline, bytes memory sig) external
```

* `permitForAll`: Approve for a `spender` by using pre-signed signature, allow other users or smart contract to perform the transfer without `owner` calling approve first.

```solidity
function permitForAll(address owner, address spender, uint256 nonce, uint256 deadline, bytes memory signature)
```

**Events**

* `Transfer`

```solidity
event Transfer(address indexed from, address indexed to, uint indexed tokenId);
```

Emitted when `tokenId` token is transferred from `from` to `to`. This event MUST be emitted when tokens are transferred in functions `transfer` ,`transferFrom` and `safeTransferFrom`.

* `Approval`

```solidity
event Approval(address indexed owner, address indexed approved, uint indexed tokenId);
```

Emitted when `owner` enables `approved` to manage the `tokenId` token. This event MUST be emitted on any successful call to `approve` function and `permit` function.

* `ApprovalForAll`

```solidity
event ApprovalForAll(address indexed owner, address indexed operator, bool approved);
```

Emitted when `owner` enables or disables (`approved`) `operator` to manage all of its assets.This event MUST be emitted on any successful call to `setApprovalForAll` function and `permitForAll` function.

### **Requirement**

For a contract to meet VRC725 requirements, it must satisfy the following conditions:

* Implement `IVRC725` which includes `IERC721`, `IERC721Metadata`.
* Must implement 2 functions: `permit` as defined in EIP- 4494 and its custom variant `permitForAll`.

```solidity
function permit(address spender, uint256 tokenId, uint256 deadline, bytes memory sig) external;
function permitForAll(address owner, address spender, uint256 nonce, uint256 deadline, bytes memory signature);
```

* Have 3 first storage slots in the contracts as follow, this is not required but necessary for integration with VictionZ.

```solidity
mapping (address => uint256) private _balances;
uint256 private _minFee;
address private _owner;
```

### **Implementation**

To implement VRC725, use can extend ERC721 contract from OpenZeppelin contract libraries or your existing NFT contract. The major differences are that `permit` and `permitForAll` functions are required, and the position in storage slots of `_balances`, `_minFee`, `_owner`.

Otherwise, you can inherit the [VRC725](https://github.com/BuildOnViction/vrc725/blob/main/contracts/VRC725.sol) from our repository.&#x20;

````solidity
/**
 * @dev Implementation of https://eips.ethereum.org/EIPS/eip-721[ERC721] Non-Fungible Token Standard, including
 * the Metadata extension, but not including the Enumerable extension, which is available separately as
 * {ERC721Enumerable}.
 */
abstract contract VRC725 is ERC165, IVRC725 {
    using Address for address;
    using Strings for uint256;

    // Mapping owner address to token count
    // The order of _balances, _minFee, _issuer must not be changed to pass validation of gas sponsor application
    mapping (address => uint256) private _balances;
    uint256 private _minFee; // minFee must always be 0 to ensure that VictionZ will work properly in the case you apply for it
    address private _owner;
    address private _newOwner;

    bool isAlreadyInit;

    // EIP 712
    bytes32 private _HASHED_NAME;
    bytes32 private _HASHED_VERSION;
    bytes32 private constant _TYPE_HASH = keccak256("EIP712Domain(string name,string version,uint256 chainId,address verifyingContract)");

    // Permit type hash using for EIP712
    bytes32 public constant PERMIT_TYPEHASH =
        keccak256(
            'Permit(address spender,uint256 tokenId,uint256 nonce,uint256 deadline)'
        );

    // Permit for all type hash using for EIP712
    bytes32 public constant PERMIT_FOR_ALL_TYPEHASH =
        keccak256(
            'PermitForAll(address spender,uint256 nonce,uint256 deadline)'
        );

    mapping(uint256 => uint256) private _nonces;
    mapping(address => uint256) private _noncesByAddress;

    // Token name
    string private _name;

    // Token symbol
    string private _symbol;

    // Mapping from token ID to owner address
    mapping(uint256 => address) private _owners;

    // Mapping from token ID to approved address
    mapping(uint256 => address) private _tokenApprovals;

    // Mapping from owner to operator approvals
    mapping(address => mapping(address => bool)) private _operatorApprovals;

    event Fee(address indexed from, address indexed to, address indexed issuer, uint256 value);
    event OwnershipTransferred(address indexed previousOwner, address indexed newOwner);

    /**
     * @dev Init function called by child contract
     */
    function __VRC725_init(string memory name_, string memory symbol_, address owner_) internal {
        require(!isAlreadyInit, "VRC725: Contract already init");
        __ERC721_init(name_, symbol_);
        __EIP712_init(name_, "1");

        _owner = owner_;
        isAlreadyInit = true;
    }

    /**
     * @dev Throws if called by any account other than the owner.
     */
    modifier onlyOwner() {
        require(_owner == msg.sender, "VRC725: caller is not the owner");
        _;
    }

    /**
     * @dev Initializes the contract by setting a `name` and a `symbol` to the token collection.
     */
    function __ERC721_init(string memory name_, string memory symbol_) private {
        _name = name_;
        _symbol = symbol_;

        _minFee = 0;
    }

    /**
     * @notice Owner of the token
     */
    function owner() public view returns (address) {
        return _owner;
    }

    /**
     * @notice Owner of the token
     */
    function issuer() public view returns (address) {
        return _owner;
    }

    /**
     * @dev The amount fee that will be lost when transferring.
     */
    function minFee() public view returns (uint256) {
        return _minFee;
    }

    /**
     * @dev See {IERC165-supportsInterface}.
     */
    function supportsInterface(bytes4 interfaceId) public view virtual override(ERC165, IERC165) returns (bool) {
        return
            interfaceId == type(IERC721).interfaceId ||
            interfaceId == type(IERC721Metadata).interfaceId ||
            interfaceId == type(IERC4494).interfaceId ||
            interfaceId == type(IVRC725).interfaceId ||
            super.supportsInterface(interfaceId);
    }

    /**
     * @dev See {IERC721-balanceOf}.
     */
    function balanceOf(address owner) public view virtual override returns (uint256) {
        require(owner != address(0), "ERC721: address zero is not a valid owner");
        return _balances[owner];
    }

    /**
     * @dev See {IERC721-ownerOf}.
     */
    function ownerOf(uint256 tokenId) public view virtual override returns (address) {
        address owner = _ownerOf(tokenId);
        require(owner != address(0), "ERC721: invalid token ID");
        return owner;
    }

    /**
     * @dev See {IERC721Metadata-name}.
     */
    function name() public view virtual override returns (string memory) {
        return _name;
    }

    /**
     * @dev See {IERC721Metadata-symbol}.
     */
    function symbol() public view virtual override returns (string memory) {
        return _symbol;
    }

    /**
     * @dev See {IERC721Metadata-tokenURI}.
     */
    function tokenURI(uint256 tokenId) public view virtual override returns (string memory) {
        _requireMinted(tokenId);

        string memory baseURI = _baseURI();
        return bytes(baseURI).length > 0 ? string(abi.encodePacked(baseURI, tokenId.toString())) : "";
    }

    /**
     * @dev Base URI for computing {tokenURI}. If set, the resulting URI for each
     * token will be the concatenation of the `baseURI` and the `tokenId`. Empty
     * by default, can be overridden in child contracts.
     */
    function _baseURI() internal view virtual returns (string memory) {
        return "";
    }

    /**
     * @dev See {IERC4494-permit}.
     */
    function permit(address spender, uint256 tokenId, uint256 deadline, bytes memory signature) external override {
        require(deadline >= block.timestamp, 'VRC725: Permit deadline expired');
        bytes32 digest = _getPermitDigest(spender, tokenId, _nonces[tokenId], deadline);

        (address recoverAddress,, ) = ECDSA.tryRecover(digest, signature);
        require(
            // if the recovered address is owner or approved on token id,
            recoverAddress != address(0)
                && _isApprovedOrOwner(recoverAddress, tokenId)
                // try to recover signature using SignatureChecker, which allows to recover signature made by contracts
                || SignatureChecker.isValidSignatureNow(ownerOf(tokenId), digest, signature)
            , "VRC725: Invalid permit signature"
        );

        _approve(spender, tokenId);
    }

    /**
     * @dev Permit for all
     */
    function permitForAll(address owner, address spender, uint256 deadline, bytes memory signature) external {
        require(deadline >= block.timestamp, 'VRC725: Permit deadline expired');
        bytes32 digest = _getPermitForAllDigest(spender, _noncesByAddress[owner], deadline);

        (address recoverAddress,, ) = ECDSA.tryRecover(digest, signature);
        require(
            // if the recovered address is owner,
            recoverAddress == owner || SignatureChecker.isValidSignatureNow(owner, digest, signature)
            , "VRC725: Invalid permit signature"
        );

        _setApprovalForAll(owner, spender, true);

        _noncesByAddress[owner]++;
    }

    /**
     * @dev See {IERC721-approve}.
     */
    function approve(address to, uint256 tokenId) public virtual override {
        address owner = VRC725.ownerOf(tokenId);
        require(to != owner, "ERC721: approval to current owner");

        require(
            msg.sender == owner || isApprovedForAll(owner, msg.sender),
            "ERC721: approve caller is not token owner or approved for all"
        );

        _approve(to, tokenId);
    }

    /**
     * @dev See {IERC721-getApproved}.
     */
    function getApproved(uint256 tokenId) public view virtual override returns (address) {
        _requireMinted(tokenId);

        return _tokenApprovals[tokenId];
    }

    /**
     * @dev See {IERC721-setApprovalForAll}.
     */
    function setApprovalForAll(address operator, bool approved) public virtual override {
        _setApprovalForAll(msg.sender, operator, approved);
    }

    /**
     * @dev See {IERC721-isApprovedForAll}.
     */
    function isApprovedForAll(address owner, address operator) public view virtual override returns (bool) {
        return _operatorApprovals[owner][operator];
    }

    /**
     * @dev See {IERC721-transferFrom}.
     */
    function transferFrom(
        address from,
        address to,
        uint256 tokenId
    ) public virtual override {
        //solhint-disable-next-line max-line-length
        require(_isApprovedOrOwner(msg.sender, tokenId), "ERC721: caller is not token owner or approved");

        _transfer(from, to, tokenId);
    }

    /**
     * @dev See {IERC721-safeTransferFrom}.
     */
    function safeTransferFrom(
        address from,
        address to,
        uint256 tokenId
    ) public virtual override {
        safeTransferFrom(from, to, tokenId, "");
    }

    /**
     * @dev See {IERC721-safeTransferFrom}.
     */
    function safeTransferFrom(
        address from,
        address to,
        uint256 tokenId,
        bytes memory data
    ) public virtual override {
        require(_isApprovedOrOwner(msg.sender, tokenId), "ERC721: caller is not token owner or approved");
        _safeTransfer(from, to, tokenId, data);
    }

    /**
     * @dev Safely transfers `tokenId` token from `from` to `to`, checking first that contract recipients
     * are aware of the ERC721 protocol to prevent tokens from being forever locked.
     *
     * `data` is additional data, it has no specified format and it is sent in call to `to`.
     *
     * This internal function is equivalent to {safeTransferFrom}, and can be used to e.g.
     * implement alternative mechanisms to perform token transfer, such as signature-based.
     *
     * Requirements:
     *
     * - `from` cannot be the zero address.
     * - `to` cannot be the zero address.
     * - `tokenId` token must exist and be owned by `from`.
     * - If `to` refers to a smart contract, it must implement {IERC721Receiver-onERC721Received}, which is called upon a safe transfer.
     *
     * Emits a {Transfer} event.
     */
    function _safeTransfer(
        address from,
        address to,
        uint256 tokenId,
        bytes memory data
    ) internal virtual {
        _transfer(from, to, tokenId);
        require(_checkOnERC721Received(from, to, tokenId, data), "ERC721: transfer to non ERC721Receiver implementer");
    }

    /**
     * @dev Returns the owner of the `tokenId`. Does NOT revert if token doesn't exist
     */
    function _ownerOf(uint256 tokenId) internal view virtual returns (address) {
        return _owners[tokenId];
    }

    /**
     * @dev Returns whether `tokenId` exists.
     *
     * Tokens can be managed by their owner or approved accounts via {approve} or {setApprovalForAll}.
     *
     * Tokens start existing when they are minted (`_mint`),
     * and stop existing when they are burned (`_burn`).
     */
    function _exists(uint256 tokenId) internal view virtual returns (bool) {
        return _ownerOf(tokenId) != address(0);
    }

    /**
     * @dev Returns whether `spender` is allowed to manage `tokenId`.
     *
     * Requirements:
     *
     * - `tokenId` must exist.
     */
    function _isApprovedOrOwner(address spender, uint256 tokenId) internal view virtual returns (bool) {
        address owner = VRC725.ownerOf(tokenId);
        return (spender == owner || isApprovedForAll(owner, spender) || getApproved(tokenId) == spender);
    }

    /**
     * @dev Safely mints `tokenId` and transfers it to `to`.
     *
     * Requirements:
     *
     * - `tokenId` must not exist.
     * - If `to` refers to a smart contract, it must implement {IERC721Receiver-onERC721Received}, which is called upon a safe transfer.
     *
     * Emits a {Transfer} event.
     */
    function _safeMint(address to, uint256 tokenId) internal virtual {
        _safeMint(to, tokenId, "");
    }

    /**
     * @dev Same as {xref-ERC721-_safeMint-address-uint256-}[`_safeMint`], with an additional `data` parameter which is
     * forwarded in {IERC721Receiver-onERC721Received} to contract recipients.
     */
    function _safeMint(
        address to,
        uint256 tokenId,
        bytes memory data
    ) internal virtual {
        _mint(to, tokenId);
        require(
            _checkOnERC721Received(address(0), to, tokenId, data),
            "ERC721: transfer to non ERC721Receiver implementer"
        );
    }

    /**
     * @dev Mints `tokenId` and transfers it to `to`.
     *
     * WARNING: Usage of this method is discouraged, use {_safeMint} whenever possible
     *
     * Requirements:
     *
     * - `tokenId` must not exist.
     * - `to` cannot be the zero address.
     *
     * Emits a {Transfer} event.
     */
    function _mint(address to, uint256 tokenId) internal virtual {
        require(to != address(0), "ERC721: mint to the zero address");
        require(!_exists(tokenId), "ERC721: token already minted");

        _beforeTokenTransfer(address(0), to, tokenId, 1);

        // Check that tokenId was not minted by `_beforeTokenTransfer` hook
        require(!_exists(tokenId), "ERC721: token already minted");

        unchecked {
            // Will not overflow unless all 2**256 token ids are minted to the same owner.
            // Given that tokens are minted one by one, it is impossible in practice that
            // this ever happens. Might change if we allow batch minting.
            // The ERC fails to describe this case.
            _balances[to] += 1;
        }

        _owners[tokenId] = to;

        emit Transfer(address(0), to, tokenId);

        _afterTokenTransfer(address(0), to, tokenId, 1);
    }

    /**
     * @dev Destroys `tokenId`.
     * The approval is cleared when the token is burned.
     * This is an internal function that does not check if the sender is authorized to operate on the token.
     *
     * Requirements:
     *
     * - `tokenId` must exist.
     *
     * Emits a {Transfer} event.
     */
    function _burn(uint256 tokenId) internal virtual {
        address owner = VRC725.ownerOf(tokenId);

        _beforeTokenTransfer(owner, address(0), tokenId, 1);

        // Update ownership in case tokenId was transferred by `_beforeTokenTransfer` hook
        owner = VRC725.ownerOf(tokenId);

        // Clear approvals
        delete _tokenApprovals[tokenId];

        unchecked {
            // Cannot overflow, as that would require more tokens to be burned/transferred
            // out than the owner initially received through minting and transferring in.
            _balances[owner] -= 1;
        }
        delete _owners[tokenId];

        emit Transfer(owner, address(0), tokenId);

        _afterTokenTransfer(owner, address(0), tokenId, 1);
    }

    /**
     * @dev Transfers `tokenId` from `from` to `to`.
     *  As opposed to {transferFrom}, this imposes no restrictions on msg.sender.
     *
     * Requirements:
     *
     * - `to` cannot be the zero address.
     * - `tokenId` token must be owned by `from`.
     *
     * Emits a {Transfer} event.
     */
    function _transfer(
        address from,
        address to,
        uint256 tokenId
    ) internal virtual {
        require(VRC725.ownerOf(tokenId) == from, "ERC721: transfer from incorrect owner");
        require(to != address(0), "ERC721: transfer to the zero address");

        _beforeTokenTransfer(from, to, tokenId, 1);

        // Check that tokenId was not transferred by `_beforeTokenTransfer` hook
        require(VRC725.ownerOf(tokenId) == from, "ERC721: transfer from incorrect owner");

        // Clear approvals from the previous owner
        delete _tokenApprovals[tokenId];

        unchecked {
            // `_balances[from]` cannot overflow for the same reason as described in `_burn`:
            // `from`'s balance is the number of token held, which is at least one before the current
            // transfer.
            // `_balances[to]` could overflow in the conditions described in `_mint`. That would require
            // all 2**256 token ids to be minted, which in practice is impossible.
            _balances[from] -= 1;
            _balances[to] += 1;
        }
        _owners[tokenId] = to;

        // increment nonce using for permit
        _incrementNonce(tokenId);

        emit Transfer(from, to, tokenId);

        _afterTokenTransfer(from, to, tokenId, 1);
    }

    /**
     * @dev Approve `to` to operate on `tokenId`
     *
     * Emits an {Approval} event.
     */
    function _approve(address to, uint256 tokenId) internal virtual {
        _tokenApprovals[tokenId] = to;
        emit Approval(VRC725.ownerOf(tokenId), to, tokenId);
    }

    /**
     * @dev Approve `operator` to operate on all of `owner` tokens
     *
     * Emits an {ApprovalForAll} event.
     */
    function _setApprovalForAll(
        address owner,
        address operator,
        bool approved
    ) internal virtual {
        require(owner != operator, "ERC721: approve to caller");
        _operatorApprovals[owner][operator] = approved;
        emit ApprovalForAll(owner, operator, approved);
    }

    /**
     * @dev Reverts if the `tokenId` has not been minted yet.
     */
    function _requireMinted(uint256 tokenId) internal view virtual {
        require(_exists(tokenId), "ERC721: invalid token ID");
    }

    /**
     * @dev Internal function to invoke {IERC721Receiver-onERC721Received} on a target address.
     * The call is not executed if the target address is not a contract.
     *
     * @param from address representing the previous owner of the given token ID
     * @param to target address that will receive the tokens
     * @param tokenId uint256 ID of the token to be transferred
     * @param data bytes optional data to send along with the call
     * @return bool whether the call correctly returned the expected magic value
     */
    function _checkOnERC721Received(
        address from,
        address to,
        uint256 tokenId,
        bytes memory data
    ) private returns (bool) {
        if (to.isContract()) {
            try IERC721Receiver(to).onERC721Received(msg.sender, from, tokenId, data) returns (bytes4 retval) {
                return retval == IERC721Receiver.onERC721Received.selector;
            } catch (bytes memory reason) {
                if (reason.length == 0) {
                    revert("ERC721: transfer to non ERC721Receiver implementer");
                } else {
                    /// @solidity memory-safe-assembly
                    assembly {
                        revert(add(32, reason), mload(reason))
                    }
                }
            }
        } else {
            return true;
        }
    }

    /**
     * @dev Hook that is called before any token transfer. This includes minting and burning. If {ERC721Consecutive} is
     * used, the hook may be called as part of a consecutive (batch) mint, as indicated by `batchSize` greater than 1.
     *
     * Calling conditions:
     *
     * - When `from` and `to` are both non-zero, ``from``'s tokens will be transferred to `to`.
     * - When `from` is zero, the tokens will be minted for `to`.
     * - When `to` is zero, ``from``'s tokens will be burned.
     * - `from` and `to` are never both zero.
     * - `batchSize` is non-zero.
     *
     * To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks].
     */
    function _beforeTokenTransfer(
        address from,
        address to,
        uint256, /* firstTokenId */
        uint256 batchSize
    ) internal virtual {
        if (batchSize > 1) {
            if (from != address(0)) {
                _balances[from] -= batchSize;
            }
            if (to != address(0)) {
                _balances[to] += batchSize;
            }
        }
    }

    /**
     * @dev Hook that is called after any token transfer. This includes minting and burning. If {ERC721Consecutive} is
     * used, the hook may be called as part of a consecutive (batch) mint, as indicated by `batchSize` greater than 1.
     *
     * Calling conditions:
     *
     * - When `from` and `to` are both non-zero, ``from``'s tokens were transferred to `to`.
     * - When `from` is zero, the tokens were minted for `to`.
     * - When `to` is zero, ``from``'s tokens were burned.
     * - `from` and `to` are never both zero.
     * - `batchSize` is non-zero.
     *
     * To learn more about hooks, head to xref:ROOT:extending-contracts.adoc#using-hooks[Using Hooks].
     */
    function _afterTokenTransfer(
        address from,
        address to,
        uint256 firstTokenId,
        uint256 batchSize
    ) internal virtual {}

    /**
     * @dev Builds the permit digest to sign
     * @param spender the address to approve
     * @param tokenId the index of the NFT to approve the spender on
     * @param nonce the nonce to make a permit for
     * @param deadline a timestamp expiry for the permit
     */
    function _getPermitDigest(address spender, uint256 tokenId, uint256 nonce, uint256 deadline) internal view returns (bytes32) {
        return _hashTypedDataV4(
            keccak256(abi.encode(
                PERMIT_TYPEHASH,
                spender,
                tokenId,
                nonce,
                deadline
            ))
        );
    }

    /**
     * @dev Builds the permit for all digest to sign
     * @param spender the address to approve
     * @param nonce the nonce to make a permit for
     * @param deadline a timestamp expiry for the permit
     */
    function _getPermitForAllDigest(address spender, uint256 nonce, uint256 deadline) internal view returns (bytes32) {
        return _hashTypedDataV4(
            keccak256(abi.encode(
                PERMIT_FOR_ALL_TYPEHASH,
                spender,
                nonce,
                deadline
            ))
        );
    }

    /**
     * @dev Helper to easily increment a nonce for a given tokenId
     */
    function _incrementNonce(uint256 tokenId) internal {
        _nonces[tokenId]++;
    }

    /**
     * @dev See {IERC4494-DOMAIN_SEPARATOR}.
     */
    function DOMAIN_SEPARATOR() external view override returns(bytes32) {
        return _domainSeparatorV4();
    }

    /**
     * @dev See {IERC4494-nonces}.
     */
    function nonces(uint256 tokenId) external view override returns(uint256) {
        require(_exists(tokenId), "ERC721: invalid token ID");
        return _nonces[tokenId];
    }

    /**
     * @dev Find nonce by address
     */
    function nonceByAddress(address owner) external view returns(uint256) {
        return _noncesByAddress[owner];
    }

    /// ------------------------------------- Ownable -------------------------------------

    /**
     * @dev Accept the ownership transfer. This is to make sure that the contract is
     * transferred to a working address
     *
     * Can only be called by the newly transfered owner.
     */
    function acceptOwnership() external {
        require(msg.sender == _newOwner, "VRC725: only new owner can accept ownership");
        address oldOwner = _owner;
        _owner = _newOwner;
        _newOwner = address(0);
        emit OwnershipTransferred(oldOwner, _owner);
    }

    /**
     * @dev Transfers ownership of the contract to a new account (`newOwner`).
     *
     * Can only be called by the current owner.
     */
    function transferOwnership(address newOwner) external virtual onlyOwner {
        require(newOwner != address(0), "VRC725: new owner is the zero address");
        _newOwner = newOwner;
    }

    /// ------------------------------------- EIP-712 -------------------------------------

    /* solhint-enable var-name-mixedcase */

    /**
     * @dev Initializes the domain separator and parameter caches.
     *
     * The meaning of `name` and `version` is specified in
     * https://eips.ethereum.org/EIPS/eip-712#definition-of-domainseparator[EIP 712]:
     *
     * - `name`: the user readable name of the signing domain, i.e. the name of the DApp or the protocol.
     * - `version`: the current major version of the signing domain.
     *
     * NOTE: These parameters cannot be changed except through a xref:learn::upgrading-smart-contracts.adoc[smart
     * contract upgrade].
     */
    function __EIP712_init(string memory name_, string memory version) private {
        __EIP712_init_unchained(name_, version);
    }

    function __EIP712_init_unchained(string memory name_, string memory version) internal {
        bytes32 hashedName = keccak256(bytes(name_));
        bytes32 hashedVersion = keccak256(bytes(version));
        _HASHED_NAME = hashedName;
        _HASHED_VERSION = hashedVersion;
    }

    /**
     * @dev Returns the domain separator for the current chain.
     */
    function _domainSeparatorV4() internal view returns (bytes32) {
        return _buildDomainSeparator(_TYPE_HASH, _EIP712NameHash(), _EIP712VersionHash());
    }

    function _buildDomainSeparator(
        bytes32 typeHash,
        bytes32 nameHash,
        bytes32 versionHash
    ) private view returns (bytes32) {
        return keccak256(abi.encode(typeHash, nameHash, versionHash, block.chainid, address(this)));
    }

    /**
     * @dev Given an already https://eips.ethereum.org/EIPS/eip-712#definition-of-hashstruct[hashed struct], this
     * function returns the hash of the fully encoded EIP712 message for this domain.
     *
     * This hash can be used together with {ECDSA-recover} to obtain the signer of a message. For example:
     *
     * ```solidity
     * bytes32 digest = _hashTypedDataV4(keccak256(abi.encode(
     *     keccak256("Mail(address to,string contents)"),
     *     mailTo,
     *     keccak256(bytes(mailContents))
     * )));
     * address signer = ECDSA.recover(digest, signature);
     * ```
     */
    function _hashTypedDataV4(bytes32 structHash) internal view virtual returns (bytes32) {
        return ECDSA.toTypedDataHash(_domainSeparatorV4(), structHash);
    }

    /**
     * @dev The hash of the name parameter for the EIP712 domain.
     *
     * NOTE: This function reads from storage by default, but can be redefined to return a constant value if gas costs
     * are a concern.
     */
    function _EIP712NameHash() internal virtual view returns (bytes32) {
        return _HASHED_NAME;
    }

    /**
     * @dev The hash of the version parameter for the EIP712 domain.
     *
     * NOTE: This function reads from storage by default, but can be redefined to return a constant value if gas costs
     * are a concern.
     */
    function _EIP712VersionHash() internal virtual view returns (bytes32) {
        return _HASHED_VERSION;
    }
}

````

Source: [VRC725.sol](https://github.com/BuildOnViction/vrc725/blob/main/contracts/VRC725.sol)

### **Example**

The following example demonstrates a token using the VRC725.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity >=0.6.2;

import "../extensions/VRC725Enumerable.sol";

contract TestNFT is VRC725Enumerable {
    constructor(string memory name, string memory symbol, address issuer) {
        __VRC725_init(name, symbol, issuer);
    }

    function _estimateFee(uint256) internal view override returns (uint256) {
        return minFee();
    }

    function mint(address owner, uint256 tokenId) external onlyOwner {
        _safeMint(owner, tokenId);
    }
}
```

Source: [TestNFT.sol](https://github.com/BuildOnViction/vrc725/blob/main/contracts/tests/TestNFT.sol)

### **Enable zero-gas transaction**

VRC725 is not required to apply for VictionZ. Zero-gas operation will be applied through TransferHelper ([click here for example](https://github.com/BuildOnViction/vrc725/blob/main/contracts/helpers/VRC725Helper.sol)) which is integrated VRC25.

In the case you need to apply for VictionZ to support more Zero-gas operations in your token, VRC725 is still compatible with VictionZ. Please refer to [VIC ZeroGas](../integration/vic-zerogas-integration.md) page for instruction.
