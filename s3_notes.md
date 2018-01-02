## S3 Notes - aCloud Guru

### Simple Storage Service
  - Object based storage
  - Difference between object storage and block based storage (Cannot install OS's for example)
  - 0 bytes to 5 TB in size
  - Unlimited storage
  - Universal namespace, names must be unique globally
  - S3 uses DNS namespace for your bucket and files names
  - Receive HTTP 200 code in the upload was successful
  - Key Value Store
  - Supports Versioning

#### Data Consistency Model
  - Read after write consistency for PUTS of new Objects
    - Read object immediately after upload
  - Eventual consistency for overwrite PUTS or DELETES
    - Updating for overwriting files may take some time to propagate. User will either get the new version or the old version after an update. File will not be corrupt.

#### Object Attrs
  - Key (Name of the object)
  - Value (This in the data and is made up of a sequence of bytes)
  - Version ID
  - Metadata
  - Sub-resources
    - Access Control lists (who can access this object, fine grained permissions on individual objects)
    - Torrent

#### Tiered Storage options and Lifecycle management
  - Lifecycle management allows a user to select how long data lives in a specific tier
  - S3 support encryption and versioning
  - Secure your data using access control lists and bucket policies
  - S3 (11 x 9's durability with 99.99% availability)
  - S3-IA (Infrequently accessed - Lower fee than S3 but there is a retrieval fee.)
  - S3-RRS (Reduced Redundancy Storage - Durability drops to 99.99% but is less expensive that standard S3)
  - Glacier - Data archival only. Very cheap storage with expensive and longer retrieval time.

#### Cross Region replication
  - Create a new bucket in a different region
  - Need versioning enables for both buckets 
  - Management > Replication > Select Source > Enable
