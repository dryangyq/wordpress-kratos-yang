该项目是原kratos的一个分支。  
原主题的地址是：  
https://github.com/vtrois/kratos  
因为我需要一些定制的功能，就fork出来一个新的分支，自己用。如果你对原有的主题开发也有不满意的地方，欢迎使用我的这个版本。当然，版权仍然是属于原主题。
主题预览：<a href="https://yangyq.net" target="_blank">老杨说话的地方</a>。

该仓库已同步到多个git托管平台，包括<a href="https://github.com/dryangyq/wordpress-kratos-yang.git" target="_blank">Github</a>、<a href="https://gitee.com/dryangyq/wordpress-kratos-yang.git" target="_blank">Gitee</a>、
<a href="https://gitlab.com/dryangyq/wordpress-kratos-yang.git" target="_blank">Gitlab</a>和<a href="https://code.aliyun.com/dryangyq/wordpress-kratos-yang.git" target="_blank">阿里云Code</a>。这些代码库都和<a href="https://git.yangyq.net/laoyang/wordpress-kratos-yang.git" target="_blank">源库</a>保持一致和同步，在任何平台上关注都可以。

**Github因为网络原因，同步会出现失败情况，无法保证最新。**

主要修改的地方主要包括：
1. 为移动端增加了侧边栏显示。之前的版本，在移动端无法看到最近评论，这个版本加入了这个功能。当然只是在首页，在文章页面，为了减少数据传输，仍然没有侧边栏。
2. 文章聚合widget，将最新文章优先显示。原来的版本，是显示最热门文章，但是不知道什么原因，热点文章总是没几个，而且我认为，大部分人上来，应该时主要为了看最新文章的吧。
3. 删除了配置页面中的关于主题，精简、精简、精简。
4. 删除了资源托管选项，删除了媒体托管选项。
5. 文章配置中，删除了文章版权信息，删除了网易云音乐。
6. 删除了社交相关配置选项。
7. 增加了在页脚显示国旗的选项。

# 修复Bug
1. 如果使用了插件，会改变comment的div名称，class="comments" 变成了comments-area，因此，评论的样式不好用了。

此时，在主题的额外CSS中添加：

```
.k-main .details .comments-area {
  margin-top: 16px;
  padding: 1.6px 16px 16px;
  border-radius: 2px;
  background-color: #fff;
  -webkit-box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  -moz-box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
}

.k-main .details .post-2 .comments-area {
  -webkit-box-shadow: none;
  -moz-box-shadow: none;
  box-shadow: none;
}
```

就可以了。该问题属于和插件的冲突问题，因此，在额外CSS中添加，不修改主题本身。