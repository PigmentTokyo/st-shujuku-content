# ST《数据库》教程内容仓库

这个仓库只保存 `st-shujuku.com` 的教程内容和后台上传图片：

- `sections/secXX.json`：每个教程章节一个 JSON 文件。
- `uploads/`：Decap CMS 新上传的图片。

VitePress 源码、服务器脚本和密钥不在这个仓库中。后台保存内容后，GitHub webhook 会让服务器校验提交，再从受保护的 VitePress 项目构建并原子发布。

请勿手工修改 JSON 文件名与其中的 `id` 对应关系。`order` 必须是非负且不重复的整数。
