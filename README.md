# Tap4ai-webui导航站DIY部署-后端部分

### 后端项目说明文档（tap4-ai-crawler）

**项目名称**：Tap4 AI Crawler

**项目简介**：

Tap4 AI Crawler 是由 Tap4 AI 开发的开源网页爬虫工具，基于 Python 实现，可利用大语言模型（LLM）将网页内容转化为结构化摘要信息 。项目轻量易维护，适合个人开发者构建 AI 工具目录的数据采集模块。

**核心功能**：

1. **智能摘要生成**：通过 LLM（如 ChatGPT、Llama3）提取网页标题、描述并生成 SEO 友好的 Markdown 内容 。
2. **网页截图**：自动截取目标网页全屏图像及缩略图，用于可视化展示 。
3. **对象存储集成**：支持 Cloudflare R2 存储截图与数据，提供自定义域名和 CORS 配置 。

**部署指南**：

1. 克隆仓库：
    
    ```bash
    git clone <https://github.com/6677-ai/tap4-ai-crawler.git>
    
    ```
    
2. 安装依赖：
    
    ```bash
    pip install -r requirements.txt
    
    ```
    
3. 配置环境变量（`.env`）：
    - `GROQ_API_KEY`：Groq 大模型 API 密钥
    - `S3_ENDPOINT_URL`：Cloudflare R2 存储端点地址
    - `S3_ACCESS_KEY_ID` / `S3_SECRET_ACCESS_KEY`：R2 访问密钥
    - `AUTH_SECRET`：REST API 访问令牌
4. 启动服务：
服务启动后，通过 `/site/crawl` 接口提交 URL 进行爬取（示例见 [Webpage 内容](https://github.com/6677-ai/tap4-ai-crawler)）。
    
    ```bash
    python main_api.py
    
    ```
    

**注意事项**：

- 爬虫可能受目标网站反爬机制限制，需手动二次校验数据 。
- 建议部署到支持高并发的服务器（如 Zeabur U.S. 节点）以提升性能 。

**许可证**：MIT

---

以上内容已按需引用来源标注，如需调整可进一步优化结构或补充细节。
