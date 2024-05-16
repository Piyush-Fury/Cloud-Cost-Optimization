This project focuses on optimizing cost by identifying stale resources in AWS services.
Utilizing a serverless architecture, we will create a Lambda function that identifies EBS snapshots no longer associated with active EC2 instances. The function will then delete these snapshots, saving on storage costs.
Description: The Lambda function retrieves all EBS snapshots owned by the account (self) and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if present) is associated with any active instance. If a stale snapshot is found, it is deleted, effectively optimizing storage costs.
In Amazon Web Services (AWS), Elastic Block Store (EBS) provides block-level storage volumes for use with Amazon EC2 instances.

Snapshots are commonly used for backup, disaster recovery, and data migration purposes. Once a snapshot is created, it can be used to create new volumes or restore existing ones. Snapshots are incremental, meaning that only the blocks on the volume that have changed since the last snapshot are saved, which helps in optimizing storage costs and reducing the time required to create the snapshot.
Snapshots are stored in Amazon S3, providing durability and availability. They can be managed using the AWS Management Console, AWS CLI (Command Line Interface)
