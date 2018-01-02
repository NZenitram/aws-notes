## Well Architected Framework - aCloud Guru


#### Intro
  - A set of questions to evaluate how well aligned your design is

### General Design Principles
  - Stop guessing your capacity needs
  - Test systems at production scale
    -  Production scale test environment
  - Automate to make architectural experimentation easier
    - Create and replicate resources at a low cost
  - Allow for evolutionary architectures
  - Data-driven architectures
  - Improve through game days

### Security - Pillar One
  - Apply security at all layers
    - Subnets, Access Control Lists, ELB Ports, instance level security (e.g. anti-virus)
  - Enable traceability
  - Automate responses to security events
  - Focus on securing your system
  - Automate security best practices
    - Base image and harden the operating system on a per AMI basis. Use hardened AMI to deploy the rest of the instances
  - Shared Responsibility Model
    - Customer is responsible for the security of data IN the cloud, AWS responsible for the security of the cloud
#### Security in the cloud consists of four areas
  - Data protection
    - Organize and classify data in to segments: Should data be publicly available? Only to members? The Board? Organize data into a least privilege access system.
  - Privilege Management
  - Infrastructure Controls
  - Detective controls
  - Privilege Management: Access Control Lists, Role Based Access Controls, Password Management


### Reliability
### Performance Efficiency
### Cost Optimization
### Operational Excellence
