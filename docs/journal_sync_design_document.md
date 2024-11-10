# Journal Synchronization Design Document

## Goal
- Synchronize vaults without using CouchDB.

## Motivation 
- **Running a CouchDB server can be complex**.
- **Full spec DBaaS** (like IBM Cloudant) is expensive and lacks suitable alternatives.
- A **secure, single-protocol solution** is needed.

## Prerequisites
- **Multiple server software implementations** should be available.
- **Saas options** must be usable, ideally with free trial options.
- A **self-hosted server instance** should be available as OSS, with transparency, availability of auditing, and verifiable actions.

## Methods and implementations

The traditional method uses PouchDB (Local) and CouchDB (Remote) to sync data by replicating missing documents. In this design, we avoid CouchDB and its protocols, focusing instead on simple operations: uploading, downloading, and retrieving lists.

This design uses any server type, including WebDAV, MinIO, S3, or R2, to store and sync journal entries.

1. **Client Data Management**:
	Each client stores its data in **PouchDB** and tracks the last synced entry in its journal.

2. **Sending Data**:
	When a client sends data, it **uploads the differences** between the last sync and the current journal, naming the file with the timestamp of its creation. This is called the "send" operation.

3. **Receiving Data**:
	Clients receive packs that have not yet been downloaded. These packs are ordered by timestamp, making it easy to receive them in the correct order. Once received, the packs are applied to the client's local database. PouchDB handles any conflicts automatically.

4. **Tracking Changes**:
	The client keeps a record of the document ID and revision of entries it has applied.
	When creating a new data pack, **the client skips the documents already marked as received and applied**, avoiding unnecessary data transfer.

5. **Efficient Synchronization**:
	Synchronization always starts with receiving data first. This ensures that only missing journal entries are transmitted, improving efficiency.
	
## Benefits
- Clients can sync data without direct communication, ensuring a **consistent server-side journal**.
- **No CouchDB dependency** makes the system more flexible and easier to maintain.
- The system uses **simple server-side storage** for efficient data exchange.

## Source Code
The implementation for this system is available in the repository.

## Test Strategy
The synchronization results were tested by comparing the changes made in the same vault: once using CouchDB and once using this new implementation. Both methods were checked for consistency.

## Documentation Strategy
- Provide a **quick setup guide** for new users.
- Avoid server configuration specifics, as **multiple server options** are available.
- Include a **MinIO setup example**, though it is not essential.
- Publish the design documents along with the code.

## Conclusion
The design introduces a novel method for synchronizing journals without relying on CouchDB. By using PouchDB and flexible server-side storage, this approach offers an efficient, decentralized system for syncing data across clients. The system is easy to maintain and avoids the complexity of traditional database synchronization methods.
