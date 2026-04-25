1. ## 目标

以llm-wiki知识库为基础的，实现claude code的自进化插件体系，实现知识库和插件的自学习、自优化、自扩展。

## llm-wiki

以 Karpathy 的 [llm-wiki.md](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) 为基座， 两种数据获取方式（可扩展多数据渠道）：本地知识库() + 联网 数据源爬取。

### 远程知识（定时任务比如每天5点开始执行）

git的ai相关的star数量前10的项目
每天ai项目trading最快的10个项目
ai资讯相关的比如大模型发布新的版本支持新的特性

### 本地数据

（word、excel、PPT、pdf）通过 office-skill 解析

### 具体场景(不管本地和远程都可以通过学习新的知识，通过create-skill创建skill更新旧的skill)

1. 比如导入一个ui框架的md就可以进行分析 生成新的ui相关的skill
2. 比如高星的项目提出的新的开发理论，对已经存在的skill进行优化

### 交付物

1. 一个知识库可以web访问，其中包含了ai相关和自己业务的知识，以及claude code 插件文档包含 skill，agent,hooks等
2. 一个claude code 插件市场。

### 期望结果

1. 可以docker化部署，实现知识库和插件市场独立运行。
2. 以前后端服务加claude code 服务器启动创建新的skill,提mr等等
