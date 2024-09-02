# aimss.github.io


[VISION PAPER] Toward a Push-based Stream Programming Model with AIMSS: An Active In-Memory Storage System for Exascale ML/AI.

Link: https://github.com/granular-storage/aimss.github.io/blob/main/aimss-push-model-system-vision-paper-final.pdf

Exascale machine learning and artificial intelligence (ML/AI) applications demand scalable, efficient, and fault-tolerant data management. 

This paper presents the vision for an Active In-Memory Storage System (AIMSS), a novel architecture that integrates storage and processing by delegating 
data movement responsibilities from applications to the storage layer. 

AIMSS leverages a log-structured in-memory framework and a push-based stream programming model to optimize data access patterns, enhance scalability and 
resilience, accelerate recovery, and mitigate power fluctuations in large-scale HPC environments.

AIMSS leverages the following key principles:

Active Data Management: AIMSS actively handles data movement tasks (ingestion, output writing, shuffling) traditionally performed by applications. This 
enables data-based optimizations based on global I/O knowledge.

Push-based Stream Programming: AIMSS employs a novel push-based stream programming model that allows applications to delegate data movement control to 
the storage layer. This facilitates efficient resource utilization and simplified application development.

Log-structured In-memory Storage: AIMSS utilizes a log-structured in-memory storage framework with immutable data access patterns, enabling efficient 
data movement and simplified fault tolerance.

Unified CPU-GPU Deployment: AIMSS is deployed across CPU-GPU HPC infrastructure, leveraging their combined memory resources for efficient data movement 
and processing.

By actively managing data movement and leveraging application knowledge through the push-based stream model, AIMSS enables several critical 
optimizations:

1. Scalable Data Movement Partitioning: AIMSS dynamically partitions and distributes data across in-memory storage resources, optimizing data locality 
and minimizing network traffic.

2. Faster Stream Storage Recovery: AIMSS leverages application stream offsets to prioritize the recovery of critical data partitions during node 
failures, significantly reducing recovery time compared to full log recovery.

3. Straggler Mitigation: AIMSS monitors stream processing progress and can dynamically reallocate resources or reschedule tasks to mitigate the impact of 
stragglers.

4. Power Jitter Reduction: AIMSS utilizes its knowledge of remaining computations to efficiently schedule tasks on idle GPUs during synchronization 
operations like checkpointing, reducing synchronized power fluctuations.

5. Reduced I/O Interference: AIMSS can be shared my multiple applications (leveraging immutable streams) on HPC supercomputers to enable reduced I/O 
interference due to global knowledge of data access patterns.

Future work will focus on developing a detailed design and implementation of AIMSS, including optimizing data movement algorithms, evaluating performance 
and scalability on large-scale HPC infrastructure, and integrating AIMSS with LLM training frameworks. 

We believe that AIMSS will significantly improve the efficiency and scalability of exascale ML/AI applications by transforming data management from a 
passive to an active role.

