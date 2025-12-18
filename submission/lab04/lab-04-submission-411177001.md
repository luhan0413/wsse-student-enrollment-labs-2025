# Lab-04 Submission

## 1. 健康檢查 / POST 新增
**指令：**
```bash
curl -i -X POST "https://rhi2d2icnj.execute-api.us-east-1.amazonaws.com/prod/api/v1/students" \
-H "Content-Type: application/json" \
-H "Authorization: Bearer eyJraWQiOiJNaTNraFg4cExqRXZ2YUJJNTFGZnZCcyswQ2I0cmdUenVtRHNyRE9FUW9BPSIsImFsZyI6IlJTMjU2In0.eyJzdWIiOiIwNDY4MzQwOC01MGUxLTcwYWEtMTRkYS1lNzlkMTQyMTA2N2EiLCJpc3MiOiJodHRwczpcL1wvY29nbml0by1pZHAudXMtZWFzdC0xLmFtYXpvbmF3cy5jb21cL3VzLWVhc3QtMV90cVdGb3hGZ1ciLCJ2ZXJzaW9uIjoyLCJjbGllbnRfaWQiOiI2amJvdG1sYjVyNTZlbjM3MzFnMWM4ZWdmYiIsImV2ZW50X2lkIjoiZjBmNjNmZDEtZDc2NC00YTNjLTg2ZmYtOGNmOWRlOGMyZDU0IiwidG9rZW5fdXNlIjoiYWNjZXNzIiwic2NvcGUiOiJzdHVkZW50LWFwaVwvc3R1ZGVudHMud3JpdGUgb3BlbmlkIHN0dWRlbnQtYXBpXC9zdHVkZW50cy5yZWFkIiwiYXV0aF90aW1lIjoxNzY2MDIyOTUwLCJleHAiOjE3NjYwMjY1NTAsImlhdCI6MTc2NjAyMjk1MCwianRpIjoiOTVjZjQ4ZDAtM2ZhYi00NTdmLTkwMTEtYzQxNTc1NGQ4M2UzIiwidXNlcm5hbWUiOiIwNDY4MzQwOC01MGUxLTcwYWEtMTRkYS1lNzlkMTQyMTA2N2EifQ.N3Fnd1qO-xs53eiK1CnYzRmZ2vsEqBCJ4OQpjZ0C-FlZqiaZ7o14N7oHnA_fprU5FSvKf-l-BRFAYDTrXl-H83wUDkxwjeS9Ux9nx7sm-59jbPhwqobTkY69Gx6ioeXXH504jZMVxcZ2ylEbX8MDHU_zhbTjUYyvQvL5nvUZmGVD-A8lva5ATMDobSpfH6mL4d9Xg5NxFmlcZA2qqFcEiMv_8jVV_fG2mZv0ogrgs7E_OPoEhXGJIj0IQu-ECHzevIA5Q5g3sKMALvppu2EdEkMrtckp5fyqhUVhBNn13v1AgItbzDvVod6NMLGQezE9HOB2sb3O7XegGa8qW2-tdw" \
-d '{"name":"TokenUser", "email":"token@secure.com"}'
```
**輸出：**
```bash
HTTP/2 201 
date: Thu, 18 Dec 2025 01:57:36 GMT
content-type: application/json
content-length: 91
x-amzn-requestid: b703dd1b-2122-4c61-9c26-e3daba46ccbd
x-amz-apigw-id: VwveVG-AoAMECiQ=
location: /api/v1/students/15b562bb-91b7-4875-b6d3-50d8188e81e0
x-amzn-trace-id: Root=1-69435f8e-46901b853b8457d679286e9f;Parent=4466bf4fcb73e15f;Sampled=0;Lineage=1:210e0fcd:0

{"id":"15b562bb-91b7-4875-b6d3-50d8188e81e0","name":"TokenUser","email":"token@secure.com"}
```
## 2. GET 分頁 (讀取清單 Limit=1)
**指令：**
```bash
curl "https://rhi2d2icnj.execute-api.us-east-1.amazonaws.com/prod/api/v1/students?limit=1" \
-H "Authorization: Bearer eyJraWQiOiJNaTNraFg4cExqRXZ2YUJJNTFGZnZCcyswQ2I0cmdUenVtRHNyRE9FUW9BPSIsImFsZyI6IlJTMjU2In0.eyJzdWIiOiIwNDY4MzQwOC01MGUxLTcwYWEtMTRkYS1lNzlkMTQyMTA2N2EiLCJpc3MiOiJodHRwczpcL1wvY29nbml0by1pZHAudXMtZWFzdC0xLmFtYXpvbmF3cy5jb21cL3VzLWVhc3QtMV90cVdGb3hGZ1ciLCJ2ZXJzaW9uIjoyLCJjbGllbnRfaWQiOiI2amJvdG1sYjVyNTZlbjM3MzFnMWM4ZWdmYiIsImV2ZW50X2lkIjoiZjBmNjNmZDEtZDc2NC00YTNjLTg2ZmYtOGNmOWRlOGMyZDU0IiwidG9rZW5fdXNlIjoiYWNjZXNzIiwic2NvcGUiOiJzdHVkZW50LWFwaVwvc3R1ZGVudHMud3JpdGUgb3BlbmlkIHN0dWRlbnQtYXBpXC9zdHVkZW50cy5yZWFkIiwiYXV0aF90aW1lIjoxNzY2MDIyOTUwLCJleHAiOjE3NjYwMjY1NTAsImlhdCI6MTc2NjAyMjk1MCwianRpIjoiOTVjZjQ4ZDAtM2ZhYi00NTdmLTkwMTEtYzQxNTc1NGQ4M2UzIiwidXNlcm5hbWUiOiIwNDY4MzQwOC01MGUxLTcwYWEtMTRkYS1lNzlkMTQyMTA2N2EifQ.N3Fnd1qO-xs53eiK1CnYzRmZ2vsEqBCJ4OQpjZ0C-FlZqiaZ7o14N7oHnA_fprU5FSvKf-l-BRFAYDTrXl-H83wUDkxwjeS9Ux9nx7sm-59jbPhwqobTkY69Gx6ioeXXH504jZMVxcZ2ylEbX8MDHU_zhbTjUYyvQvL5nvUZmGVD-A8lva5ATMDobSpfH6mL4d9Xg5NxFmlcZA2qqFcEiMv_8jVV_fG2mZv0ogrgs7E_OPoEhXGJIj0IQu-ECHzevIA5Q5g3sKMALvppu2EdEkMrtckp5fyqhUVhBNn13v1AgItbzDvVod6NMLGQezE9HOB2sb3O7XegGa8qW2-tdw"
```
**輸出：**
```bash
{"items":[{"createdAt":"2025-12-18T01:57:35.299Z","SK":"PROFILE","PK":"ID#15b562bb-91b7-4875-b6d3-50d8188e81e0","email":"token@secure.com","name":"TokenUser"}],"nextCursor":"eyJQSyI6IklEIzE1YjU2MmJiLTkxYjctNDg3NS1iNmQzLTUwZDgxODhlODFlMCIsIlNLIjoiUFJPRklMRSJ9"}
```

## 3. GET 續頁 
**指令：**
```bash
curl "https://rhi2d2icnj.execute-api.us-east-1.amazonaws.com/prod/api/v1/students?limit=1&cursor=eyJQSyI6IklEIzE1YjU2MmJiLTkxYjctNDg3NS1iNmQzLTUwZDgxODhlODFlMCIsIlNLIjoiUFJPRklMRSJ9" \
-H "Authorization: Bearer eyJraWQiOiJNaTNraFg4cExqRXZ2YUJJNTFGZnZCcyswQ2I0cmdUenVtRHNyRE9FUW9BPSIsImFsZyI6IlJTMjU2In0.eyJzdWIiOiIwNDY4MzQwOC01MGUxLTcwYWEtMTRkYS1lNzlkMTQyMTA2N2EiLCJpc3MiOiJodHRwczpcL1wvY29nbml0by1pZHAudXMtZWFzdC0xLmFtYXpvbmF3cy5jb21cL3VzLWVhc3QtMV90cVdGb3hGZ1ciLCJ2ZXJzaW9uIjoyLCJjbGllbnRfaWQiOiI2amJvdG1sYjVyNTZlbjM3MzFnMWM4ZWdmYiIsImV2ZW50X2lkIjoiZjBmNjNmZDEtZDc2NC00YTNjLTg2ZmYtOGNmOWRlOGMyZDU0IiwidG9rZW5fdXNlIjoiYWNjZXNzIiwic2NvcGUiOiJzdHVkZW50LWFwaVwvc3R1ZGVudHMud3JpdGUgb3BlbmlkIHN0dWRlbnQtYXBpXC9zdHVkZW50cy5yZWFkIiwiYXV0aF90aW1lIjoxNzY2MDIyOTUwLCJleHAiOjE3NjYwMjY1NTAsImlhdCI6MTc2NjAyMjk1MCwianRpIjoiOTVjZjQ4ZDAtM2ZhYi00NTdmLTkwMTEtYzQxNTc1NGQ4M2UzIiwidXNlcm5hbWUiOiIwNDY4MzQwOC01MGUxLTcwYWEtMTRkYS1lNzlkMTQyMTA2N2EifQ.N3Fnd1qO-xs53eiK1CnYzRmZ2vsEqBCJ4OQpjZ0C-FlZqiaZ7o14N7oHnA_fprU5FSvKf-l-BRFAYDTrXl-H83wUDkxwjeS9Ux9nx7sm-59jbPhwqobTkY69Gx6ioeXXH504jZMVxcZ2ylEbX8MDHU_zhbTjUYyvQvL5nvUZmGVD-A8lva5ATMDobSpfH6mL4d9Xg5NxFmlcZA2qqFcEiMv_8jVV_fG2mZv0ogrgs7E_OPoEhXGJIj0IQu-ECHzevIA5Q5g3sKMALvppu2EdEkMrtckp5fyqhUVhBNn13v1AgItbzDvVod6NMLGQezE9HOB2sb3O7XegGa8qW2-tdw"
```
**輸出：**
```bash
{"items":[{"createdAt":"2025-12-18T01:46:34.241Z","SK":"PROFILE","PK":"ID#5f367ee4-5621-4bdb-a425-5ea599537b20","email":"tester@internal.com","name":"LambdaTester"}],"nextCursor":"eyJQSyI6IklEIzVmMzY3ZWU0LTU2MjEtNGJkYi1hNDI1LTVlYTU5OTUzN2IyMCIsIlNLIjoiUFJPRklMRSJ9"}
```
## 4. 截圖放置：