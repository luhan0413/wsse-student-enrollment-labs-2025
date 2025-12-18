# Lab-07 監控與告警整合 (Monitoring & Observability)
411177001 呂依涵

## 1. 實驗目的
本實驗旨在透過 AWS CDK 將可觀測性（Observability）工具整合至 Serverless 架構中。
實作項目包含：
1. **Logs**：設定 Lambda Log 保存期限，避免成本浪費。
2. **Metrics & Alarms**：定義錯誤指標，並設定當錯誤超過門檻時觸發 SNS Email 通知。
3. **Dashboard**：建立視覺化儀表板，即時監控系統健康狀況。
4. **X-Ray**：啟用分散式追蹤，觀察請求在服務間的流向與延遲。

---

## 2. 驗證截圖

以下截圖證明系統監控與告警功能運作正常。
驗證截圖均存放在：

#### (1) CloudWatch Alarm 狀態
![Alarm In Alarm 狀態](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/f47ff9504c5da84ecd5490b93c137b732eeeb1c0/submission/lab07/evidence/411177001-metrics.png)

#### (2) SNS Email 通知
![Email 通知信](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/f47ff9504c5da84ecd5490b93c137b732eeeb1c0/submission/lab07/evidence/411177001-alarm-email.png)

#### (3) CloudWatch Dashboard
![Dashboard](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/f47ff9504c5da84ecd5490b93c137b732eeeb1c0/submission/lab07/evidence/411177001-dashboard.png)

#### (4) CloudWatch Logs
![CloudWatch Logs](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/f47ff9504c5da84ecd5490b93c137b732eeeb1c0/submission/lab07/evidence/411177001-cloudwatch-logs.png)

#### (5) X-Ray Service Map
![X-Ray Service Map](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/f47ff9504c5da84ecd5490b93c137b732eeeb1c0/submission/lab07/evidence/411177001-xray-map.png)
