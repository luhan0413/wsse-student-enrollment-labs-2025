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

## 3. 實作佐證畫面 (Evidence)

以下為本次實驗要求的 6 張關鍵截圖：

### (1) SNS Topic 詳細資訊
![SNS Topic](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/29bb9ad97ac9727faea3560412e2ffdcdfd636b1/submission/lab05/evidence/411177001-sns-topic.png)

### (2) SQS Queue 詳細資訊
![SQS Queue](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/29bb9ad97ac9727faea3560412e2ffdcdfd636b1/submission/lab05/evidence/411177001-sqs-queue.png)

### (3) Producer Lambda 程式碼 (發送端)
![Producer Code](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/29bb9ad97ac9727faea3560412e2ffdcdfd636b1/submission/lab05/evidence/411177001-lambda-producer.png)

### (4) Consumer Lambda 程式碼 (接收端)
![Consumer Code](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/29bb9ad97ac9727faea3560412e2ffdcdfd636b1/submission/lab05/evidence/411177001-lambda-consumer.png)

### (5) Postman 測試成功 (201 Created)
![Postman Result](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/29bb9ad97ac9727faea3560412e2ffdcdfd636b1/submission/lab05/evidence/411177001-api-post-201.png)

### (6) CloudWatch Logs 執行記錄
![CloudWatch Logs](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/29bb9ad97ac9727faea3560412e2ffdcdfd636b1/submission/lab05/evidence/411177001-logs.png)

截圖照片url: https://github.com/luhan0413/wsse-student-enrollment-labs-2025/tree/main/submission/lab05/evidence
