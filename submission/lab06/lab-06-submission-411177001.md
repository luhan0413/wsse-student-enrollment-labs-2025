# Lab-06 作業報告：IaC 與 CI/CD 自動化部署
---

## 1. 實驗目標
**AWS CDK (TypeScript)** 實現基礎設施即程式碼 (IaC)，並結合
**GitHub Actions** 建立 CI/CD 自動化部署流程，達成以下目標：
1. 使用 CDK 定義 DynamoDB、Lambda、SNS 與 SQS 等雲端資源。
2. 實作 Producer/Consumer 的事件驅動架構。
3. 設定 GitHub OIDC Role 以實現安全的自動化部署。
4. 驗證 API 寫入資料與背景非同步處理流程。


## 2. 截圖證明清單 (Evidence)
所有證明截圖皆已存放於 : https://github.com/luhan0413/wsse-student-enrollment-labs-2025/tree/402bf3b41b6e0174db2ddede21c110398b14d9d5/submission/lab06/evidence
### (1) GitHub Actions 執行成功 (綠色勾勾)
![alt text](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/402bf3b41b6e0174db2ddede21c110398b14d9d5/submission/lab06/evidence/411177001-actions-success.png)
### (2) CDK 部署狀態 (終端機 Outputs)
![alt text](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/402bf3b41b6e0174db2ddede21c110398b14d9d5/submission/lab06/evidence/411177001-cdk-deploy.png)
### (3) API 功能驗證 (curl 回傳 201)
![alt text](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/402bf3b41b6e0174db2ddede21c110398b14d9d5/submission/lab06/evidence/411177001-post-201.png)
### (4) DynamoDB 資料表 (Students)
![alt text](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/402bf3b41b6e0174db2ddede21c110398b14d9d5/submission/lab06/evidence/411177001-ddb-table.png)
### (5) SNS Topic 詳細資訊
![alt text](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/402bf3b41b6e0174db2ddede21c110398b14d9d5/submission/lab06/evidence/411177001-sns-topic.png)
### (6) SQS Queue 詳細資訊
![alt text](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/402bf3b41b6e0174db2ddede21c110398b14d9d5/submission/lab06/evidence/411177001-sqs-queue.png)
### (7) Producer Lambda 函數
![alt text](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/402bf3b41b6e0174db2ddede21c110398b14d9d5/submission/lab06/evidence/411177001-lambda-producer.png)
### (8) Consumer Lambda 函數
![alt text](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/402bf3b41b6e0174db2ddede21c110398b14d9d5/submission/lab06/evidence/411177001-lambda-consumer.png)
### (9) CloudWatch Logs 系統日誌
![alt text](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/402bf3b41b6e0174db2ddede21c110398b14d9d5/submission/lab06/evidence/411177001-logs.png)
