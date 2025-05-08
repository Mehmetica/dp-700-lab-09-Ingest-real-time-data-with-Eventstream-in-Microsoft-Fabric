# dp-700-lab-09-Ingest-real-time-data-with-Eventstream-in-Microsoft-Fabric
📈 Real-Time Stock Market Analytics with Microsoft Fabric
This project demonstrates how to use Microsoft Fabric Real-Time Intelligence to ingest, store, analyze, and visualize real-time stock market data using eventstreams, eventhouses, and KQL queries.

🔧 Lab Steps Overview
1. Workspace Creation
Created a new workspace in Microsoft Fabric with Fabric capacity enabled.

2. Eventstream Setup
Connected to the Stock market sample data source from the Real-Time Hub.

Renamed the eventstream to stock-data and the associated stream to stock-data-stream.

3. Eventhouse Creation
Created a new Eventhouse to store and analyze real-time data.

Generated a KQL database and created a table named stock.

4. Stream-to-Table Connection
Connected the stock-data eventstream to the stock table in the Eventhouse.

Verified live data ingestion from the stream into the table.

5. Data Analysis with KQL
Ran sample KQL (Kusto Query Language) queries, including:

kql
Kopyala
Düzenle
stock
| take 100
and

kql
Kopyala
Düzenle
stock
| where ["time"] > ago(5m)
| summarize avgPrice = avg(todecimal(bidPrice)) by symbol
| project symbol, avgPrice
6. Real-Time Dashboard Creation
Pinned the live query result to a new dashboard called Stock Dashboard.

Visualized average stock prices using a Column chart tile.

7. Alert Setup with Activator
Configured an Activator alert to monitor when the average price for any stock symbol increases by more than 100.

Set action to send an email notification.

8. Resource Cleanup
All created resources can be deleted by removing the workspace via Workspace Settings.

🧰 Technologies & Tools
Microsoft Fabric Real-Time Hub

Eventstream

Eventhouse & KQL Database

Kusto Query Language (KQL)

Dashboards for visualization

Activator for real-time alerting

💡 Real-World Applications
This project simulates a stock market data pipeline but the same architecture can be applied to:

Monitoring IoT sensor data (e.g., temperature, pressure, speed)

Analyzing financial transactions in real time

Detecting anomalies in application logs or security events

Real-time logistics and supply chain tracking

📌 Notes
This example provides a foundational structure for streaming data analytics in Microsoft Fabric.
![Screenshot 2025-05-06 at 11 18 29](https://github.com/user-attachments/assets/d0517f3d-8660-4cbe-89b6-0f7ad760f4c9)
![Screenshot 2025-05-06 at 11 18 02](https://github.com/user-attachments/assets/7c0041c4-0323-4ecd-ae97-9c9b8d069d83)
![Screenshot 2025-05-06 at 10 54 36](https://github.com/user-attachments/assets/bbf54222-c957-4ff1-a458-a1302aa78ac5)
![Screenshot 2025-05-06 at 10 46 24](https://github.com/user-attachments/assets/483cc890-394b-4d9d-a2c1-1fd540f88808)
![Screenshot 2025-05-06 at 10 46 12](https://github.com/user-attachments/assets/796e95a0-20ee-4d89-af94-0d2dae486669)
![Screenshot 2025-05-06 at 10 45 35](https://github.com/user-attachments/assets/e5123f4d-d57a-492f-bb79-bf04cd425e8a)
![Screenshot 2025-05-06 at 10 44 02](https://github.com/user-attachments/assets/6f380242-4ec8-4f91-a4eb-9eda2d1087c3)
![Screenshot 2025-05-06 at 10 41 05](https://github.com/user-attachments/assets/d45205b1-6c8e-44c6-bbb5-1faf5e6746f3)
![Screenshot 2025-05-06 at 10 34 10](https://github.com/user-attachments/assets/e6a2810b-f095-4bb3-940d-80880fe8294d)
![Screenshot 2025-05-06 at 10 28 57](https://github.com/user-attachments/assets/5edfa38c-0f56-43f5-8e70-557f8bdff2fb)
![Screenshot 2025-05-06 at 10 28 54](https://github.com/user-attachments/assets/0e245324-d7d9-4c9b-80eb-b14f1d33d15c)



For production use, consider integrating windowing functions, data filtering, advanced transformations, and external alerting mechanisms.
