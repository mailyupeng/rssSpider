rssSpider
=========

#简介#

  网络爬虫，使用NodeJs抓取RSS新闻。提供RSS服务的站点超级多，百度、网易、新浪、虎嗅网 等等站点，基于java  c++、php的rss抓取网上很多。今天说说NodeJs抓取RSS信息

  最新做一个新闻项目，项目流程很简单，使用nodejs去网络上面抓取新闻，存到mongodb数据库，然后对客户端提供http服务。客户端的实现网上有很多源码，上一篇文字介绍了，怎么从rss地址抓取新闻的url地址和链接等等，未抓取新闻正文和新闻的概要图片。对于一个新闻客户端来说，没有图片是致命的打击，图文并茂才能吸引用户 。

  本项目抓取了新闻的标题、来源、url地址、描述、正文、新闻的图片，提供新闻列表服务、单个新闻查询服务，觉得项目还ok，请点个赞吧，哈哈

#项目介绍#
项目开发环境：nodejs、mongodb

**运行方式 **

<code> 
  node app.js
</code>

**本项目以网易的rss进行测试 http://www.163.com/rss**

**关键抓取代码，在service目录**


##项目特色##
1.  多站点同时抓取，需要抓取的站点可以在配置文件中配置
2.  抓取的新闻正文的准确率非常高，包括图片
3.  nodejs实现，抓取效率非常高
4.  可以配置抓取的时间，和新闻正文的开始标签，过滤掉广告无用的图片和广告（iframe广告）
5.  已经提供了，新闻列表和新闻查询的http服务，为android或者其他客户端完美提供数据源支持



项目的详细介绍地址：
文章1：http://blog.csdn.net/kissliux/article/details/19560603

文章2：http://blog.csdn.net/kissliux/article/details/20466889

#2014.3.4  更新日志
1.  重新架构项目，使用jshint进行代码验证
2.  RSS抓取到新闻链接后，继续抓取新闻正文，提取出新闻正文中的有用图片、和正文。 新闻进行列表显示的时候，如果有图片，更能吸引眼球，本项目抓取网易的新闻正和图片，正确率在90%以上
3.  为其他客户端提供新闻查询的http服务，查询新闻列表(标题、图片、描述)，获取新闻正文

*客户端请求新闻列表协议* 见源码中的文档


#2014.2.27 更新日志
1、使用express 提供新闻服务，为android客户端和其他客户端提供服务

2、加入分页支持

3、使用chreeio插件，遍历web网页全文，抓取新闻标题和url地址。(针对m.baidu.com测试)实验。



