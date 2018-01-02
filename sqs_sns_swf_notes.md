## SQS Notes - aCloud Guru

#### Simple Queue Service
  - Web service that gives you access to a message queue
  - If you lose your EC2 instance, SQS will store the job for the next instance to pick up
  - SQS is always a pull based system
  - SQS can decouple the components of an application
  - 256 kb limit for SQS messages
  - Queue resolves issues that arise if the producer is producing more work than the consumer can process
  - Can build auto scaling into SQS

#### Types of Queues
  - Standard Queues
    - Default queue type
    - Nearly unlimited number of transactions per second
    - Best effort ordering
  - FIFO Queues
    - Limited to 300 transactions per second
    - Order is strictly preserved
    - Duplicates are not introduced to the queue

#### Key Facts
  - Pull based system
  - 256kb in size
  - 1 minute to 14 day life cycle
  - Visibility timeout the amount of time that the message is invisible to the SQS queue (timeout 12 hours)
  - Guarantees that your messages will be processed at least once
  - Long polling: A way to retrieve messages from your SQS queue (use long polling to control costs - timeout between polling; charged on a per poll basis)

## SNS Notes - aCloud Guru

#### Simple Notification Service
  - Set up, operate and send notifications from the cloud
  - Pub/Sub messaging paradigm
  - Push oriented, no need to poll for messages from Queue

#### Delivery
  - SMS text, email, SQS or HTTP endpoint
  - Can combined SQS and SNS
  - Redundant storage across multiple AZs

#### Topics
  - Group recipients using topics
  - An access point for allowing recipients to dynamically subscribe for identical copies of the same notification
  - Multiple endpoint types

## SWF Notes - aCloud Guru

#### Simple Workflow Service
   - Web service to coordinate work across distributed application components
   - Media processing, web application back-ends, business process workflows, analytics pipelines
   - Tasks are processing steps in an application which may include executing code, scripts, human actions

#### Workers & Deciders
  - Worker is a program that interacts with SWF to get tasks and process the task to return a results
  - Decider is a program that controls the coordination of tasks, their ordering, concurrency, scheduling to the application logic
  - Worker and decider can run on cloud infrastructure
  - SWF stores tasks and assigns them to a worker
  - Ensures that a task is only assigned once and is never duplicated
  - Maintains application's state durably, workers and deciders don't have to keep track of execution state.
  - Run independently and scale quickly

#### Domains
  - Isolate a set of types, execution and task lists from others within the account
  - Parameters supplied in JSON
  - Maximum workflow is one year and it is measured in seconds

#### SQS vs SWF
  - SQS is message oriented while SWF is task oriented
  - SWF ensures a task is assigned only once and never duplicated; SQS messages may be duplicated or processed more than once
  - SWF tracks all tasks and events in an application; SQS requires you implement your own application level tracking
