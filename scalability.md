### AWS Aurora Scalability
    The scaling policy defines the minimum and maximum number of Aurora Replicas that Aurora Auto Scaling can manage. 
    Based on the policy, Aurora Auto Scaling adjusts the number of Aurora Replicas up or down in response to actual 
    workloads, determined by using Amazon CloudWatch metrics and target values.
    
    A scaling policy could use the predefined average CPU utilization metric. Such a policy can keep CPU utilization at, 
    or close to, a specified percentage of utilization, such as 40 percent.

### AWS DynamoDB Scalability
    Amazon DynamoDB auto scaling uses the AWS Application Auto Scaling service to dynamically adjust provisioned 
    throughput capacity on your behalf, in response to actual traffic patterns. This enables a table or a global 
    secondary index to increase its provisioned read and write capacity to handle sudden increases in traffic, 
    without throttling.
    
    The auto scaling process:

    1. You create an Application Auto Scaling policy for your DynamoDB table.
    2. DynamoDB publishes consumed capacity metrics to Amazon CloudWatch.
    3. If the table's consumed capacity exceeds your target utilization (or falls below the target) for a specific 
    length of time, Amazon CloudWatch triggers an alarm. You can view the alarm on the console and receive 
    notifications using Amazon SNS.
    4. The CloudWatch alarm invokes Application Auto Scaling to evaluate your scaling policy.
    5. Application Auto Scaling issues an UpdateTable request to adjust your table's provisioned throughput.
    6. DynamoDB processes the UpdateTable request, dynamically increasing (or decreasing) the table's provisioned 
    throughput capacity so that it approaches your target utilization.
    
