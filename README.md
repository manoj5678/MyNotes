# MyNotes
MyNotes is an all new app that lets their users upload small notes to the cloud so that they are stored safely and can be retrieved later from any location. The mobile application is ready, but the back-end team is just starting the development



Architecture Explination

Application Backend - The backend application is deployed on ECS which is an Elastic Container Service provider by AWS for orchestration of containers. We have deployed the backend application in two different availability zones for high availability. ECS backend service will be served through an Application Load Balancer.

Application Frontend - The frontend application is deployed on S3 (Simple Storage Service) + Cloudfront. The code will be deployed onto S3 Storage and served via Cloudfront. We have used S3+Cloudfront to achieve high availability and to get low latency. S3 is highly available and it scales as per the requirement, Cloudfront will cache the frontend site on an edge location near by the customer’s region. We have used Cloudfront here to achieve low latency for customers. 

Database - Database is hosted on RDS (Relational Database Service), by using RDS we can deploy our Database as Multi AZ(Deployed in all availability zones) and we can also use Read Replicas for improving the performance of the application. Read Replicas can be used to perform read operations for the application by which we can decrease the load on the main database.`

DNS - We have used Route53 for mapping the DNS for our application. 




