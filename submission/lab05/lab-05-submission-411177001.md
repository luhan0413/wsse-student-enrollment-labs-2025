# LAB-05：非同步整合實作報告
411177001 呂依涵
---

## 1. 實驗目標
目標是當使用者透過 API 新增學生資料時，系統能自動觸發後續的非同步流程：
`API Gateway` -> `Producer Lambda` -> `DynamoDB` -> `SNS` -> `SQS` -> `Consumer Lambda` -> `CloudWatch Logs`。

## 2. 系統架構圖
1. **Producer Lambda (/students)**: 負責將資料寫入 DynamoDB 並發布訊息至 SNS Topic。
2. **SNS Topic (主题)**: 接收 Producer 的事件並廣播給所有訂閱者。
3. **SQS Queue (佇列)**: 訂閱 SNS，接收訊息並緩衝，等待 Consumer 處理。
4. **Consumer Lambda**: 由 SQS 觸發，解析訊息並將結果記錄至 CloudWatch Logs。

## 3. 實作步驟摘要
1. **建立基礎設施**：建立 Amazon SNS 標準主題與 Amazon SQS 標準佇列，並設定 SNS 訂閱 SQS。
2. **授權設定**：
    - 為 Producer Lambda 角色新增 `sns:Publish` 權限。
    - 為 Consumer Lambda 角色新增 `AWSLambdaSQSQueueExecutionRole` 權限。
3. **Producer 程式開發**：修改 `/students` API，加入 AWS SDK v3 的 `SNSClient`，在成功寫入資料庫後呼叫 `PublishCommand`。
4. **Consumer 程式開發**：建立新的 Lambda 函式，設定 SQS 為觸發源，撰寫程式碼解析 `event.Records` 中的 SNS 訊息。
5. **整合測試**：透過 Postman 發送帶有 Cognito Token 的 POST 請求，並到 CloudWatch 觀察日誌。

## 4. 實作佐證畫面 (Evidence)

以下為本次實驗要求的 6 張關鍵截圖：

### (1) SNS Topic 詳細資訊
![SNS Topic](./evidence/<你的學號>-sns-topic.png)

### (2) SQS Queue 詳細資訊
![SQS Queue](./evidence/<你的學號>-sqs-queue.png)

### (3) Producer Lambda 程式碼 (發送端)
![Producer Code](./evidence/<你的學號>-lambda-producer.png)

### (4) Consumer Lambda 程式碼 (接收端)
![Consumer Code](./evidence/<你的學號>-lambda-consumer.png)

### (5) Postman 測試成功 (201 Created)
![Postman Result](./evidence/<你的學號>-api-post-201.png)

### (6) CloudWatch Logs 執行記錄
![CloudWatch Logs](./evidence/<你的學號>-logs.png)

