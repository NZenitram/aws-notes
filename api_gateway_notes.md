## API Gateway Notes - aCloud Guru

#### Api Gateway
  - API caching speeds up endpoints response time
  - Caches responses with a TTL
  - You can throttle requests to prevent attacks
  - Connects to Cloudwatch
  - Maintains same origin policy, may need to activate CORS

#### Exam Tips
  - Caching capabilities to increase performance
  - Low cost, scales automatically
  - Throttle gateway requests to prevent attacks
  - Use CORS for multiple domains

## Kinesis 101 - aCloud Guru

#### Streaming Data
  - Data that is generate continuously
  - Data sent simultaneously in small sizes
    - Purchases from online stores, stock prices, game data, geospatial data

#### Core Services
  - Streams
    - 24 hrs to 7 days of storage
    - Stored in 'shards'
    - EC2 instances consume the shard data
    - Consumed data is then sent to storage service
    - Total capacity of stream is the sum of the total number of shards
  - Firehose
    - No sharding, completely automated
    - Can be sent straight to S3 for storage
    - No retention. Used, then stored
  - Analytics
    - Allows us to run SQL queries on the data provided by Firehose or Streams

  - Know the difference between streams and firehose
  - Understand at a high level what Kinesis analytics is
