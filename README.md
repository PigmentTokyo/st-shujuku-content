# ST《数据库》教程内容仓库

这个仓库只保存 `st-shujuku.com` 的公开教程内容、后台上传图片和单文件 HTML 页面：

- `sections/secXX.json`：每个教程章节一个 JSON 文件。
- `uploads/`：Decap CMS 新上传的教程图片。
- `html-pages/<slug>.json`：HTML 页面的标题、网址标识、文件引用和启用状态。
- `html-uploads/*.html`：通过后台上传的 UTF-8 单文件 HTML，单个文件最大 5 MiB。

VitePress 源码、服务器脚本和密钥不在这个仓库中。后台保存后，服务器每分钟拉取 `main`，严格校验路径、JSON、图片和 HTML，再从受保护的 VitePress 项目构建并原子发布。

请勿手工修改 JSON 文件名与其中的 `id`/`slug` 对应关系。章节 `order` 必须是非负且不重复的整数。每个已发布 HTML 页面必须引用一个存在的上传文件；替换或删除条目后遗留的旧文件不会公开，可稍后从媒体库清理。

上传的 HTML 不会作为裸同源文件公开。构建器会把它嵌入没有 `allow-same-origin` 权限的沙箱 iframe，公开地址为 `https://st-shujuku.com/html/<slug>.html`。单文件内的脚本可以运行，但不能读取教程后台的登录状态、Cookie 或父页面。
