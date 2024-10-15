# DA Integration Use cases

This section provides an overview of how the Viction Data Availability (DA) Layer integrates with Layer 2 (L2) rollups. The integration involves implementing a Light Client as an intermediary component. This Light Client encapsulates the necessary logic to enable rollups to maintain IDs (commitments to the transaction blob data) on the Viction network while storing the full transaction data on the DA Layer. The diagram below outlines each step of this workflow, offering a high-level understanding of the integration process.

The Light Client plays a crucial role in this architecture by ensuring the integrity and availability of transaction data. It achieves this by:

* **Storing IDs on Viction(L1)**: Preserving the cryptographic commitment to the transaction data, which allows for verification and auditing on the Viction network.
* **Managing Data Storage on the DA Layer**: Offloading the actual transaction data to the Viction DA Layer, thereby optimizing storage efficiency and scalability.

By providing this intermediary layer, the integration facilitates a seamless connection between L2 rollups and the Viction DA Layer, enhancing scalability without compromising data integrity or availability.

<figure><img src="../../.gitbook/assets/VictionDA-Integration Usecase.png" alt=""><figcaption><p>Viction - Data Availability (DA) Layer Architecture</p></figcaption></figure>

**Note**: The current version of the Light Client is undergoing active testing and will be updated soon with new improvements.

\
