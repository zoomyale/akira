# Akira

一个基于 [Attila](https://github.com/zutrinken/attila) 的 [Ghost](https://github.com/tryghost/ghost/) 中文主题，和 Attila 一样，是强调内容的简约主题。

具体效果可参见 [我的博客](https://zoomyale.com/)。

在原主题的基础上，Akira 主要针对中文显示效果做了调整，包括中文排版、样式优化，并且增加了社交账号配置，精简了主题包，删除不适用于中文的文件，以提升加载速度。

## 截图

![screenshot.jpg](https://i.loli.net/2020/05/06/CqUyxLacTS4zifP.jpg)

## 特性

优化后独有的特性：

* 支持[汉字标准格式](https://hanzi.pro/)
* 为中文展示优化的样式
* 适配各系统的中文黑体
* 可自定义的社交账号链接及图标
* 带导航的 404 页
* 支持 [Gitalk](https://gitalk.github.io/)

原主题支持的特性：

* 响应式设计
* 暗黑模式（跟随系统自动切换）
* 文章阅读进度
* 带行号的代码块
* 支持 [Disqus](https://disqus.com/)

## 设置语言

Akira 是专为中文展示优化的主题，换言之，无法保证中文以外的文字展示效果。

为保证样式展示正常，请务必在 Ghost 后台 SETTINGS > General > Publication Language 中，将语言设置为 `zh`。

## 社交账号配置

![icons.png](https://i.loli.net/2020/05/06/vAd7U4QtcbKuCn9.png)

Akira 支持配置社交账号及图标，方法如下。

1. 进入 Ghost 后台的 __Design__
2. 在 __Secondary Navigation__ 中配置标签（即导航项名称栏）和社交链接，目前支持的社交账号有：

| 社交账号          | 标签（不区分大小写）    |
|---------------|---------------|
| Twitter       | twitter       |
| Facebook      | facebook      |
| Github        | github        |
| LinkedIn      | linkedin      |
| StackOverflow | stackoverflow |
| Instagram     | instagram     |
| Tumblr        | tumblr        |
| Dribbble      | dribbble      |
| Behance       | behance       |
| Slack         | slack         |
| Steam         | steam         |
| Reddit        | reddit        |
| GitLab        | gitlab        |
| Telegram      | telegram      |
| Podcast       | podcast       |
| 微信            | wechat        |
| 新浪微博          | weibo         |


## 设置 [Disqus](https://disqus.com/)

1. 进入 Ghost 后台的 __Code injection__
2. 把这段代码加到 __Blog Header__（注意替换引号中内容）:  

````
<script>var disqus = 'YOUR_DISQUS_SHORTNAME';</script>
````

## 设置 [Gitalk](https://gitalk.github.io/)

1. 创建 GitHub Application，如果没有点击[这里申请](https://github.com/settings/applications/new)，`Authorization callback URL` 填写 Blog 域名
2. 进入 Ghost 后台的 __Code injection__
3. 把配置代码加到 __Blog Footer__，详细设置项说明可参考[官方文档](https://github.com/gitalk/gitalk/blob/master/readme-cn.md)（注意替换引号中内容）:  

````
<script>
	var gitalk = new Gitalk({
        clientID: 'GitHub Application Client ID',
		clientSecret: 'GitHub Application Client Secret',
		repo: 'GitHub repo',
		owner: 'GitHub repo owner',
		admin: ['GitHub repo owner and collaborators, only these guys can initialize github issues'],
		id: location.pathname,
        language: 'zh-CN'
    });
</script>
````

另外，需注意若同时设置了 Disqus 和 Gitalk，会优先使用 Disqus。


## 主题开发

安装 [Grunt](https://gruntjs.com/getting-started/)：

	npm install -g grunt-cli

安装 Grunt 依赖：

	npm install

构造 Grunt 项目：

	grunt build

Grunt 打包：

	grunt compress

打包后的主题文件会写入到 `dist/<theme-name>.zip`，你可以直接将该 zip 文件上传到 Ghost。

## License

[MIT License](https://github.com/zutrinken/attila/blob/master/LICENSE)