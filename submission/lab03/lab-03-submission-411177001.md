
### 1. 健康檢查 (GET /health)
**指令：**
```bash
curl -s https://rhi2d2icnj.execute-api.us-east-1.amazonaws.com/prod/api/v1/health
```
**輸出：**
```bash
{"status":"ok"}
```
### 2. 讀取學生清單 (GET /students)
**指令：**
```bash
curl -s -H "Authorization: Bearer eyJraWQiOiJNaTNraFg4cExqRXZ2YUJJNTFGZnZCcyswQ2I0cmdUenVtRHNyRE9FUW9BPSIsImFsZyI6IlJTMjU2In0.eyJzdWIiOiIwNDY4MzQwOC01MGUxLTcwYWEtMTRkYS1lNzlkMTQyMTA2N2EiLCJpc3MiOiJodHRwczpcL1wvY29nbml0by1pZHAudXMtZWFzdC0xLmFtYXpvbmF3cy5jb21cL3VzLWVhc3QtMV90cVdGb3hGZ1ciLCJ2ZXJzaW9uIjoyLCJjbGllbnRfaWQiOiI2amJvdG1sYjVyNTZlbjM3MzFnMWM4ZWdmYiIsImV2ZW50X2lkIjoiZjgyODdlYmEtYTYyOS00ZjVkLTk3YTQtODc2MzJlODhlYWFlIiwidG9rZW5fdXNlIjoiYWNjZXNzIiwic2NvcGUiOiJzdHVkZW50LWFwaVwvc3R1ZGVudHMud3JpdGUgb3BlbmlkIHN0dWRlbnQtYXBpXC9zdHVkZW50cy5yZWFkIiwiYXV0aF90aW1lIjoxNzY1OTk1MzI2LCJleHAiOjE3NjU5OTg5MjYsImlhdCI6MTc2NTk5NTMyNywianRpIjoiMDExMTIzYzktMWMxMy00NWI3LTkwZDEtYWFiODYyYzE3ZjI2IiwidXNlcm5hbWUiOiIwNDY4MzQwOC01MGUxLTcwYWEtMTRkYS1lNzlkMTQyMTA2N2EifQ.Bpj_bwF5Kg1UPWELmNTML_u7VYl7q2Tv_kj-bAJpBxDrFPwsIP14ZTUajAheAmgxhF_ZPfc3CIp3pGU3cL-ZopLqAkdMLpwztHuGMHTdWjb8NkUiIQvWhMu4NX2vPlQYdahfQb-zyjqtZ1S4aXvE4vFS01SDM6AiqZz4ZB379bHz413VaLU8WI7_i_gzWwbUMEpTIaGJFcQmUDP41pRiAv-yQHNdUfvh4vQzo5VigKzYHD5Vs3TgQmvMchmk1y75_e-uAgLjSXncDnWwKrAuYJHtOrV2swADYC_njD3WYPXtoq5b-yNhPb4kQ0tcselkN6wufAR5ZNi5N5rlfSlBng" \
"https://rhi2d2icnj.execute-api.us-east-1.amazonaws.com/prod/api/v1/students?limit=2"
```
**輸出：**
```bash
{"items":[{"id":1,"name":"Student-1","email":"s1@example.edu"},{"id":2,"name":"Student-2","email":"s2@example.edu"}],"nextCursor":null}  
```

### 3. 新增學生 (POST /students)
**指令：**
```bash
curl -s -X POST -H "Authorization: Bearer eyJraWQiOiJNaTNraFg4cExqRXZ2YUJJNTFGZnZCcyswQ2I0cmdUenVtRHNyRE9FUW9BPSIsImFsZyI6IlJTMjU2In0.eyJzdWIiOiIwNDY4MzQwOC01MGUxLTcwYWEtMTRkYS1lNzlkMTQyMTA2N2EiLCJpc3MiOiJodHRwczpcL1wvY29nbml0by1pZHAudXMtZWFzdC0xLmFtYXpvbmF3cy5jb21cL3VzLWVhc3QtMV90cVdGb3hGZ1ciLCJ2ZXJzaW9uIjoyLCJjbGllbnRfaWQiOiI2amJvdG1sYjVyNTZlbjM3MzFnMWM4ZWdmYiIsImV2ZW50X2lkIjoiZjgyODdlYmEtYTYyOS00ZjVkLTk3YTQtODc2MzJlODhlYWFlIiwidG9rZW5fdXNlIjoiYWNjZXNzIiwic2NvcGUiOiJzdHVkZW50LWFwaVwvc3R1ZGVudHMud3JpdGUgb3BlbmlkIHN0dWRlbnQtYXBpXC9zdHVkZW50cy5yZWFkIiwiYXV0aF90aW1lIjoxNzY1OTk1MzI2LCJleHAiOjE3NjU5OTg5MjYsImlhdCI6MTc2NTk5NTMyNywianRpIjoiMDExMTIzYzktMWMxMy00NWI3LTkwZDEtYWFiODYyYzE3ZjI2IiwidXNlcm5hbWUiOiIwNDY4MzQwOC01MGUxLTcwYWEtMTRkYS1lNzlkMTQyMTA2N2EifQ.Bpj_bwF5Kg1UPWELmNTML_u7VYl7q2Tv_kj-bAJpBxDrFPwsIP14ZTUajAheAmgxhF_ZPfc3CIp3pGU3cL-ZopLqAkdMLpwztHuGMHTdWjb8NkUiIQvWhMu4NX2vPlQYdahfQb-zyjqtZ1S4aXvE4vFS01SDM6AiqZz4ZB379bHz413VaLU8WI7_i_gzWwbUMEpTIaGJFcQmUDP41pRiAv-yQHNdUfvh4vQzo5VigKzYHD5Vs3TgQmvMchmk1y75_e-uAgLjSXncDnWwKrAuYJHtOrV2swADYC_njD3WYPXtoq5b-yNhPb4kQ0tcselkN6wufAR5ZNi5N5rlfSlBng" \
-H "Content-Type: application/json" \
-d '{"name":"Ann","email":"ann@example.edu"}' \
"https://rhi2d2icnj.execute-api.us-east-1.amazonaws.com/prod/api/v1/students" -i
```
**輸出：**
```bash
HTTP/2 201 
date: Wed, 17 Dec 2025 18:18:31 GMT
content-type: application/json
content-length: 59
x-amzn-requestid: 761f11a7-c7e9-44e6-8347-b2896ca05cd3
x-amz-apigw-id: VvsOvF6aIAMEQXg=
location: /api/v1/students/1765995511575
x-amzn-trace-id: Root=1-6942f3f7-7bebaa73588ea14a1eac9720;Parent=2cc228d128d75e8e;Sampled=0;Lineage=1:210e0fcd:0

{"id":1765995511575,"name":"Ann","email":"ann@example.edu"}
```
