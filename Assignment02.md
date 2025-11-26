# 1. Executive Summary
This report compares the cloud services offered by Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP), with a focus on remote data access and real-time applications. These types of workloads are becoming more common as modern systems rely on fast API responses, live communication, and continuous data streams. Each of the three cloud providers offers tools to support these needs, but they approach them in different ways based on their strengths.

The comparison looks at five key areas: RESTful API services, GraphQL support, WebSocket and real-time messaging, data streaming, and real-time analytics. AWS provides strong options for serverless APIs, IoT workloads, and large-scale streaming through services like API Gateway, AppSync, Kinesis, and AWS IoT Core. Azure stands out for enterprise-focused API management and real-time communication, especially with Azure API Management, Web PubSub, and SignalR Service. GCP is the strongest in high-speed event streaming and analytics with Cloud Pub/Sub, Dataflow, and BigQuery.

Two real-world examples are used to show how these differences matter in practice. For a stock trading platform that depends on extremely fast event processing, GCP is the most suitable because of its low-latency streaming and analytics tools. For a smart-building IoT system that needs reliable device connectivity and real-time sensor data, AWS is the best fit due to its mature IoT ecosystem.

Overall, the report shows that all three cloud providers can support remote data and real-time applications, but the best choice depends on the specific requirements of the project, such as scalability, cost, integration needs, and data processing complexity.

# 2. Introduction 

Cloud computing has become the main way companies build and run modern applications. Instead of buying their own hardware, organizations use cloud providers to host APIs, process data, and support real-time features like chat, live dashboards, and event streaming. This report focuses on three major cloud service providers (CSPs): Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).

AWS is Amazon’s public cloud platform that offers more than 200 services across compute, storage, databases, networking, analytics, and many other areas. It is widely used for building web applications, APIs, and large-scale data platforms using a pay-as-you-go pricing model. 

Microsoft Azure is Microsoft’s cloud platform for building, deploying, and managing applications across cloud, hybrid, and edge environments. It provides a broad range of services including compute, storage, networking, analytics, and AI, and it integrates tightly with other Microsoft tools such as Windows Server, Active Directory, and Office 365.

Google Cloud Platform is Google’s suite of cloud services that runs on the same global infrastructure as products like Google Search and Gmail. It offers infrastructure, platform, and serverless services with a strong focus on data analytics and machine learning through tools like BigQuery and Dataflow. 

In this report, we compare AWS, Azure, and GCP for remote data and real-time applications. The main focus is on RESTful APIs, GraphQL, WebSockets, data streaming, and stream analytics. The goal is to understand how each provider supports these workloads and to identify which platform may be a better fit for different real-world use cases.


# 3. Service Comparison 


### a) RESTful API Services 

| Cloud Provider | Main API Service            | What It’s Good At                                       | Pricing Style                        |
| -------------- | --------------------------- | ------------------------------------------------------- | ------------------------------------ |
| **AWS**        | Amazon API Gateway          | Great for serverless apps, easy Lambda integration      | Pay per API call                     |
| **Azure**      | Azure API Management (APIM) | Strong enterprise controls and API policies             | Tier-based pricing                   |
| **GCP**        | Google API Gateway / Apigee | Strong monitoring and analytics for large organizations | Pay-as-you-go or Apigee tier pricing |



- Based on the comparison, AWS seems best for quick serverless APIs, Azure fits well for organizations that need strong policy control, and GCP stands out when detailed analytics and API monitoring (through Apigee) are important. 
### b) GraphQL Services 

| Cloud Provider | GraphQL Support                   | Notes                                                        |
| -------------- | --------------------------------- | ------------------------------------------------------------ |
| **AWS**        | AWS AppSync (managed GraphQL) | Easiest option with built-in resolvers and real-time updates |
| **Azure**      | No native GraphQL service         | Requires hosting your own GraphQL server                     |
| **GCP**        | No native GraphQL service         | Usually deployed on Cloud Run, GKE, or App Engine            |

- AWS is the only provider that gives a ready-to-use GraphQL service, while Azure and GCP both require you to host your own GraphQL setup, which adds a bit more work for developers.

### c) WebSocket Services 

| Cloud Provider | Real-Time Service                                 | Strengths                                             |
| -------------- | ------------------------------------------------- | ----------------------------------------------------- |
| **AWS**        | API Gateway WebSocket APIs, AppSync subscriptions | Good for serverless real-time features                |
| **Azure**      | Web PubSub, SignalR Service               | Best dedicated real-time messaging services           |
| **GCP**        | Self-hosted WebSockets; Firebase                  | Flexible options, Firebase easiest for real-time sync |

- Azure clearly has the strongest real-time messaging options, AWS works well if you want a serverless approach to WebSockets, and GCP usually relies on Firebase or custom setups for real-time features.

### d) Data Streaming Services 

| Cloud Provider | Streaming Tools                  | Strengths                                                      |
| -------------- | -------------------------------- | -------------------------------------------------------------- |
| **AWS**        | Kinesis (Streams, Firehose), MSK | Very strong for large-scale, high-throughput streaming         |
| **Azure**      | Event Hubs                       | Best for Microsoft-based data and analytics workflows          |
| **GCP**        | Cloud Pub/Sub, Pub/Sub Lite      | Fast global event distribution and smooth BigQuery integration |


- AWS and GCP both offer excellent tools for handling high-speed data streams, while Azure’s streaming tools fit best when the rest of the system is already built around Microsoft services.

### e) Stream Analytics 

| Cloud Provider | Analytics Tools                     | Strengths                                                  |
| -------------- | ----------------------------------- | ---------------------------------------------------------- |
| **AWS**        | Kinesis Data Analytics, EMR, Glue   | Great for advanced and custom streaming pipelines          |
| **Azure**      | Azure Stream Analytics          | Easiest SQL-style real-time analytics, great with Power BI |
| **GCP**        | Dataflow (Beam), BigQuery streaming | Excellent for real-time analytics and ML pipelines         |



- Azure is the easiest platform for real-time analytics because of its simple SQL-style queries, GCP is the most powerful for analytics-heavy workloads, and AWS is great if you need more advanced or customized streaming pipelines.

# 4. Use Case Analysis 

1) Stock trading app:

    A fintech startup wants to build a real-time stock tracking platform where users can see live price movements, trade volumes, alerts, and market trends within seconds. The system must ingest thousands of events per second from market feeds, process them instantly, and update dashboards, trading signals, and risk alerts without delays. It also needs scalable analytics for historical and real-time queries.

    Best Choice: 
        - Google Cloud Platform (GCP)

    Justification:
        - GCP’s Cloud Pub/Sub works really well for fast-moving data like stock prices, trade updates, and market activity because it can handle a huge amount of messages with very low delay. It doesn’t require any servers to set up, so it’s easy for a small team to start using right away. For processing the incoming data, Cloud Dataflow (which uses Apache Beam) can run calculations in real time, such as tracking price trends, spotting unusual movements, or calculating running averages. After the data is processed, it can be sent straight into BigQuery, where it becomes available almost immediately for dashboards, alerts, or even automated trading models.  

    GCP is also fairly affordable for continuous data streaming and comes with built-in tools for analytics and machine learning, which makes it a strong option for a modern stock-trading platform that needs real-time insights.

2) IoT Sensor Monitoring for Smart Buildings

    A smart-building company wants to collect real-time data from hundreds of IoT sensors placed throughout the building. These sensors track things like temperature, humidity, motion, air quality, and energy usage. The system needs to process incoming data instantly to update dashboards, notify building staff about unusual activity, and help automate heating, cooling, and lighting based on live conditions. It also needs to store this information for long-term analysis and reporting.

    Best Choice:
        - Amazon Web Services (AWS)

    Justification:

    AWS works especially well for IoT scenarios because it provides AWS IoT Core, which allows thousands of devices to connect securely without requiring any servers to manage the device connections. IoT Core can forward real-time sensor data directly into services like Amazon Kinesis, where the data can be processed immediately for alerts or dashboard updates. Kinesis is designed for high-volume, continuous streams, so it can easily handle sensor readings coming in every second. After processing, the data can be stored in services like S3 or pushed into analytics tools for trend analysis or energy-usage reports.
    Overall, AWS offers an easy and reliable way to manage device connections, real-time data processing, and long-term storage, which makes it a strong fit for smart-building IoT systems.

# 5. Conclusion 

This report compared AWS, Azure, and GCP based on the services needed for remote data access and real-time applications. Although all three cloud providers offer strong and reliable platforms, each one shines in different areas. AWS is especially good for serverless APIs, IoT workloads, and complex streaming pipelines because of services like API Gateway, IoT Core, and Kinesis. Azure stands out for enterprise API governance and real-time communication, especially with services like API Management, SignalR, and Web PubSub. GCP is strongest in high-speed event streaming and real-time analytics, thanks to Cloud Pub/Sub, Dataflow, and BigQuery.

Each provider can support modern application needs, but the best choice depends on the scenario. For example, the stock trading use case benefits the most from GCP’s powerful real-time data processing tools, while the smart-building IoT system fits naturally with AWS because of its mature IoT ecosystem. Overall, the comparison shows that picking a cloud provider is not about which one is “best” in general, but which one aligns most closely with the specific workload’s performance, scalability, and integration needs.

# 6. References
Amazon Web Services. (2024). Amazon API Gateway Documentation. https://docs.aws.amazon.com/apigateway

Amazon Web Services. (2024). AWS AppSync Documentation. https://docs.aws.amazon.com/appsync

Amazon Web Services. (2024). Amazon Kinesis Documentation. https://docs.aws.amazon.com/kinesis

Amazon Web Services. (2024). AWS IoT Core Documentation. https://docs.aws.amazon.com/iot

Microsoft. (2024). Azure API Management Documentation. https://learn.microsoft.com/azure/api-management

Microsoft. (2024). Azure Web PubSub Documentation. https://learn.microsoft.com/azure/azure-web-pubsub

Microsoft. (2024). Azure SignalR Service Documentation. https://learn.microsoft.com/azure/azure-signalr

Microsoft. (2024). Azure Stream Analytics Documentation. https://learn.microsoft.com/azure/stream-analytics

Google Cloud. (2024). Google API Gateway Documentation. https://cloud.google.com/api-gateway

Google Cloud. (2024). Apigee API Management Documentation. https://cloud.google.com/apigee

Google Cloud. (2024). Cloud Pub/Sub Documentation. https://cloud.google.com/pubsub

Google Cloud. (2024). Cloud Dataflow Documentation. https://cloud.google.com/dataflow

### 7. AI Usage Disclosure

I used generative AI (ChatGPT, Claude) to help brainstorm and find the use cases, help find documentation to compare cloud services, and review the clarity of my writing and see if i have grammatical errors or if the structure of the report is accurate. 

However, all the creative ideas, research and analysis is my own work. 