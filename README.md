# AWS Serverless Microservice (Lambda + API Gateway + DynamoDB)

This project demonstrates a fully serverless microservice built using AWS Lambda, API Gateway, and DynamoDB.  
It includes CRUD operations, IAM least‑privilege access, CloudWatch logging, Postman testing, and AWS Lambda Power Tuning for performance optimization.


# Architecture
<img width="1536" height="1024" alt="architecture png" src="https://github.com/user-attachments/assets/82c99e66-f0bb-4b7c-bd4a-fbfe3ba9be39" />
The microservice uses the following AWS components:

 **API Gateway** – REST endpoint for client requests
<img width="1600" height="809" alt="api-gateway" src="https://github.com/user-attachments/assets/23fa55ea-2f6c-4cf9-a7e2-e22a944205a9" />

 **AWS Lambda** – Core compute for business logic
  <img width="1060" height="362" alt="lambda" src="https://github.com/user-attachments/assets/63dc5b7c-9818-4ef5-87e8-6e435955636c" />

 **DynamoDB** – NoSQL database for storage
  <img width="1279" height="680" alt="dynamodb" src="https://github.com/user-attachments/assets/60487af8-f2e1-4f86-a550-440f0fda53c9" />

 **IAM** – Least‑privilege execution role
 <img width="1151" height="569" alt="policy" src="https://github.com/user-attachments/assets/d8a01285-a4ce-45b0-b7df-8de09f0de59c" />

  **CloudWatch** – Logging and monitoring  


## IAM Policy (Least Privilege)

The Lambda function uses a custom IAM policy with only the required permissions:

### **DynamoDB**
- GetItem  
- PutItem  
- UpdateItem  
- DeleteItem  
- Query  
- Scan  

### **CloudWatch Logs**
- CreateLogGroup  
- CreateLogStream  
- PutLogEvents  



## Testing

### Functional Testing (Postman)

All endpoints were tested using Postman.

<img width="1560" height="800" alt="postman" src="https://github.com/user-attachments/assets/45374cf9-8c14-4d64-963e-5f23b7ae97c3" />


### Load Testing

Simulated multiple concurrent requests to validate performance.

<img width="1429" height="765" alt="128MB memorypostman result" src="https://github.com/user-attachments/assets/b11c6f43-d916-4291-aa40-1aa548c15a98" />

<img width="1558" height="810" alt="with1024MBmemorypostman results" src="https://github.com/user-attachments/assets/e277fcbd-94f9-40fb-a350-eb5f67737942" />



## Performance Optimization (AWS Lambda Power Tuning)

I ran AWS Lambda Power Tuning at **128 MB** and **1024 MB**.

| Memory | Duration | Cost |
|--------|----------|------|
| 128 MB | Slowest  | Higher |
| 1024 MB | Fastest | Lower |

### Power Tuning Results

<img width="1911" height="1039" alt="powertuning-128" src="https://github.com/user-attachments/assets/d34ec946-bf4e-48de-9147-4790372e386d" />

<img width="1759" height="787" alt="powertuning-1024" src="https://github.com/user-attachments/assets/4daf74a3-a23a-4671-aece-b280e9ff11bf" />
  
<img width="853" height="480" alt="Comparison" src="https://github.com/user-attachments/assets/257952ca-7c74-49ba-a152-a553dd645708" />


## Key Takeaways

- Increasing Lambda memory reduces execution time  
- Faster execution often lowers cost  
- Serverless architectures scale automatically  
- IAM least‑privilege is essential for security  


