# Lab-01 作業交付

## 1. Repo 連結
- [Repo URL](https://github.com/luhan0413/wsse-student-enrollment-labs-2025.git)

## 2. PR 連結 (通過 CI)
- [PR #1]([https://github.com/你的帳號/你的專案名稱/pull/1](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/pull/1/commits/d04101bf6c3711384e82beb6bce91b3de3f3e253))

## 3. Swagger Editor 截圖 (無紅字)
<!-- 請將 01-editor.png 拖拉至此處，或填入圖片連結 -->
![01-editor.png](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/bfdd98fab1d836eae1eb8caff2687fe5c8ce6748/%E6%88%AA%E5%9C%96/01-editor.png)

## 4. PR 綠燈截圖 (OpenAPI Minimal CI)
<!-- 請將 02-pr-green.png 拖拉至此處 -->
![02-pr-green.png](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/bfdd98fab1d836eae1eb8caff2687fe5c8ce6748/%E6%88%AA%E5%9C%96/02-pr-green.png)

## 5. CI 內容截圖 (Job log)
<!-- 請將 03-actions-log.png 拖拉至此處 -->
![03-actions-log.png](https://github.com/luhan0413/wsse-student-enrollment-labs-2025/blob/bfdd98fab1d836eae1eb8caff2687fe5c8ce6748/%E6%88%AA%E5%9C%96/03-actions-log.png)
## 6. 重點片段連結 (檔案行號連結)

### 基礎路徑與方法
- [/health (含 security 覆寫)](https://github.com/.../openapi.yaml#L26-L39)
- [GET /students](https://github.com/.../openapi.yaml#L42-L55)
- [POST /students (含 201 + Location)](https://github.com/.../openapi.yaml#L57-L70)

### Schema 定義
- [Student Schema](https://github.com/.../openapi.yaml#L79-L87)
- [Error Schema](https://github.com/.../openapi.yaml#L90-L96)

### 安全性設定 (若已做)
- [ApiKey 定義與全域設定](https://github.com/.../openapi.yaml#L22-L23)
