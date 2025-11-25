# 1. Executive Summary


# 2. Introduction 

- Cloud computing has become the main way companies build and run modern applications. Instead of buying their own hardware, organizations use cloud providers to host APIs, process data, and support real-time features like chat, live dashboards, and event streaming. This report focuses on three major cloud service providers (CSPs): Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).

- AWS is Amazon’s public cloud platform that offers more than 200 services across compute, storage, databases, networking, analytics, and many other areas. It is widely used for building web applications, APIs, and large-scale data platforms using a pay-as-you-go pricing model. 
- Microsoft Azure is Microsoft’s cloud platform for building, deploying, and managing applications across cloud, hybrid, and edge environments. It provides a broad range of services including compute, storage, networking, analytics, and AI, and it integrates tightly with other Microsoft tools such as Windows Server, Active Directory, and Office 365.
- Google Cloud Platform is Google’s suite of cloud services that runs on the same global infrastructure as products like Google Search and Gmail. It offers infrastructure, platform, and serverless services with a strong focus on data analytics and machine learning through tools like BigQuery and Dataflow. 
- In this report, we compare AWS, Azure, and GCP for remote data and real-time applications. The main focus is on RESTful APIs, GraphQL, WebSockets, data streaming, and stream analytics. The goal is to understand how each provider supports these workloads and to identify which platform may be a better fit for different real-world use cases.


# 3. Service Comparison 
Compare the three CSPs across these categories:

### a) RESTful API Services (15%)

| Cloud Provider | Main API Service            | What It’s Good At                                       | Pricing Style                        |
| -------------- | --------------------------- | ------------------------------------------------------- | ------------------------------------ |
| **AWS**        | Amazon API Gateway          | Great for serverless apps, easy Lambda integration      | Pay per API call                     |
| **Azure**      | Azure API Management (APIM) | Strong enterprise controls and API policies             | Tier-based pricing                   |
| **GCP**        | Google API Gateway / Apigee | Strong monitoring and analytics for large organizations | Pay-as-you-go or Apigee tier pricing |



- I beleive AWS is best for serverless APIs, Azure is best for enterprise API governance, and GCP provides prowerful analytics through Apigee 
### b) GraphQL Services (15%)

| Cloud Provider | GraphQL Support                   | Notes                                                        |
| -------------- | --------------------------------- | ------------------------------------------------------------ |
| **AWS**        | **AWS AppSync (managed GraphQL)** | Easiest option with built-in resolvers and real-time updates |
| **Azure**      | No native GraphQL service         | Requires hosting your own GraphQL server                     |
| **GCP**        | No native GraphQL service         | Usually deployed on Cloud Run, GKE, or App Engine            |

- AWS is the only one with a fully managed GraphQL service. Azure and GCP require you to host GraphQL yourself.

### c) WebSocket Services (10%)

| Cloud Provider | Real-Time Service                                 | Strengths                                             |
| -------------- | ------------------------------------------------- | ----------------------------------------------------- |
| **AWS**        | API Gateway WebSocket APIs, AppSync subscriptions | Good for serverless real-time features                |
| **Azure**      | **Web PubSub**, **SignalR Service**               | Best dedicated real-time messaging services           |
| **GCP**        | Self-hosted WebSockets; Firebase                  | Flexible options, Firebase easiest for real-time sync |

- Azure offers the most complete real-time/WebSocket services, AWS works well for serverless apps, and GCP often relies on Firebase or self-hosting.

### d) Data Streaming Services (10%)

| Cloud Provider | Streaming Tools                  | Strengths                                                      |
| -------------- | -------------------------------- | -------------------------------------------------------------- |
| **AWS**        | Kinesis (Streams, Firehose), MSK | Very strong for large-scale, high-throughput streaming         |
| **Azure**      | Event Hubs                       | Best for Microsoft-based data and analytics workflows          |
| **GCP**        | Cloud Pub/Sub, Pub/Sub Lite      | Fast global event distribution and smooth BigQuery integration |


- AWS and GCP are very strong in high-speed event streaming. Azure fits best with Microsoft-based workloads.

### e) Stream Analytics (10%)

| Cloud Provider | Analytics Tools                     | Strengths                                                  |
| -------------- | ----------------------------------- | ---------------------------------------------------------- |
| **AWS**        | Kinesis Data Analytics, EMR, Glue   | Great for advanced and custom streaming pipelines          |
| **Azure**      | **Azure Stream Analytics**          | Easiest SQL-style real-time analytics, great with Power BI |
| **GCP**        | Dataflow (Beam), BigQuery streaming | Excellent for real-time analytics and ML pipelines         |



- Azure is simplest for streaming analytics, GCP is strongest for analytical workflows, and AWS is best for complex pipelines.

# 4. Use Case Analysis (15%)
Present two real-world scenarios for real-time applications
Recommend the most suitable CSP for each with justification
Consider: cost, performance, ease of integration, ecosystem

1) Finance application for stock trading

# 5. Conclusion (5%)
Summary of findings and overall recommendations
# 6. References