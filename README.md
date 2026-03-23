# arXiv 论文助手插件

一个用于 AstrBot 的插件，提供 arXiv 论文搜索和下载功能。

## 功能特性

1. **论文搜索**：通过关键词、作者、标题等条件搜索 arXiv 论文
2. **论文下载**：下载 arXiv 论文的 PDF 文件到本地
3. **论文信息获取**：获取论文的详细信息，包括标题、作者、摘要等
4. **已下载论文管理**：列出已下载的论文文件

## 安装方法

1. 将本插件文件夹 `astrbot_plugin_arxiv_paper` 放入 `data/plugins/` 目录中
2. 重启 AstrBot
3. 插件将自动安装依赖并启用

## 使用方法

插件提供了以下工具函数，可供 AI Agent 调用：

### 1. 搜索论文

**工具名称**: `search_arxiv_papers`

**参数**:
- `query` (必填): 搜索查询，可以是关键词、标题、作者等
- `max_results` (可选): 返回的最大结果数量，默认 10
- `sort_by` (可选): 排序方式，可选值: 'relevance' (相关性)、'lastUpdatedDate' (最近更新)、'submittedDate' (提交日期)，默认 'relevance'
- `sort_order` (可选): 排序顺序，可选值: 'ascending' (升序)、'descending' (降序)，默认 'descending'

**示例**:
- "搜索关于 transformer 的论文"
- "查找作者是 Yann LeCun 的最新论文"

### 2. 下载论文

**工具名称**: `download_arxiv_paper`

**参数**:
- `arxiv_id` (必填): arXiv 论文 ID，例如 '1706.03762' 或 'hep-th/9701168'
- `filename` (可选): 保存的文件名（不含扩展名），如果不指定则使用 arXiv ID

**示例**:
- "下载 arXiv:1706.03762"
- "下载论文 hep-th/9701168 并保存为 'string_theory'"

### 3. 获取论文信息

**工具名称**: `get_arxiv_paper_info`

**参数**:
- `arxiv_id` (必填): arXiv 论文 ID

**示例**:
- "获取论文 1706.03762 的详细信息"

### 4. 列出已下载论文

**工具名称**: `list_downloaded_papers`

**参数**:
- `limit` (可选): 显示的最大论文数量，默认 20

**示例**:
- "列出最近下载的 10 篇论文"

## 配置

默认下载目录为 `files/arxiv_papers/`，您可以通过修改插件代码中的 `DEFAULT_DOWNLOAD_DIR` 变量来更改。

## 注意事项

1. 插件需要网络连接才能访问 arXiv API
2. 下载的论文将保存在本地文件系统中
3. 遵守 arXiv 的使用条款，不要进行大规模的自动化下载
4. 如果遇到下载失败，请检查网络连接和 arXiv ID 的正确性

## 更新日志

### v1.0.0 (2026-03-22)
- 初始版本发布
- 支持 arXiv 论文搜索
- 支持 PDF 下载
- 支持论文信息获取
- 支持已下载论文列表查看

## 许可证

MIT

## 作者

win98
