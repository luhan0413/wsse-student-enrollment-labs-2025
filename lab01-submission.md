# Lab-01 作業交付

## 1. Repo 連結
- [Repo URL](https://github.com/luhan0413/wsse-student-enrollment-labs-2025.git)

## 2. PR 連結 (通過 CI)
- [PR #1 URL](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/pull/1/commits/d04101bf6c3711384e82beb6bce91b3de3f3e253)

## 3. Swagger Editor 截圖 (無紅字)
<!-- 請將 01-editor.png 拖拉至此處，或填入圖片連結 -->
![01-editor.png](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/bfdd98fab1d836eae1eb8caff2687fe5c8ce6748/%E6%88%AA%E5%9C%96/01-editor.png)

## 4. PR 綠燈截圖 (OpenAPI Minimal CI)
<!-- 請將 02-pr-green.png 拖拉至此處 -->
![02-pr-green.png](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/68382b42e70763bb44cb993d6825f74940a10f9f/%E6%88%AA%E5%9C%96/02-pre-green.png)

## 5. CI 內容截圖 (Job log)
<!-- 請將 03-actions-log.png 拖拉至此處 -->
![03-actions-log.png](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/bfdd98fab1d836eae1eb8caff2687fe5c8ce6748/%E6%88%AA%E5%9C%96/03-actions-log.png)
## 6. 重點片段連結 (檔案行號連結)

### 基礎路徑與方法
- [/health (含 security 覆寫)](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/9b7f9cf00c5923076bfc2ac5dc7c9410a085c9a0/openapi/openapi.yaml#L27-L41)
- [GET /students](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/9b7f9cf00c5923076bfc2ac5dc7c9410a085c9a0/openapi/openapi.yaml#L44-L63)
- [POST /students (含 201 + Location)](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/9b7f9cf00c5923076bfc2ac5dc7c9410a085c9a0/openapi/openapi.yaml#L65-L85)

### Schema 定義
- [Student Schema](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/9b7f9cf00c5923076bfc2ac5dc7c9410a085c9a0/openapi/openapi.yaml#L97-L106)
- [Error Schema](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/9b7f9cf00c5923076bfc2ac5dc7c9410a085c9a0/openapi/openapi.yaml#L108-L117)

### 安全性設定
- [ApiKey 定義與全域設定](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/9b7f9cf00c5923076bfc2ac5dc7c9410a085c9a0/openapi/openapi.yaml#L87-L93)
