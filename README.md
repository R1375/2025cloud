# 2025cloud Docker 專案

這是一個為了完成課程作業而創建的專案，展示如何使用 Docker 和 GitHub Actions 來自動化構建和部署容器映像。

## 打包應用程式

使用以下指令打包應用程式：

```bash
docker build -t R1375/2025cloud:v1.0 .
## 自動化 Container Image 產生邏輯

本專案使用 GitHub Actions 實現自動化 Docker 映像的構建和發布，具體流程如下：

```mermaid
graph TD
    A[開發者提交代碼] --> B[GitHub 檢測變更]
    B --> C[觸發 GitHub Actions]
    C --> D[構建 Docker 映像]
    D --> E{構建成功?}
    E -->|是| F{是 Pull Request?}
    F -->|否| G[推送到 Docker Hub]
    F -->|是| H[不推送，僅驗證]
    E -->|否| I[構建失敗，顯示錯誤]
    G --> J[標記為 latest 和 commit hash]
