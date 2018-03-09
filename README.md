# 区块链学习实践手册 (blockchain-handbook)

**区块链**（英语：blockchain）是用分布式数据库识别、传播和记载信息的智能化对等网络, 也称为价值互联网。中本聪在2008年，于[《比特币白皮书》](https://bitcoin.org/bitcoin.pdf)中提出区块链概念，并在2009年创立了比特币社会网络，开发出第一个区块，即**创世区块**。

区块链共享价值体系首先被众多的加密货币效仿，并在工作量证明上和算法上进行了改进，如采用权益证明和 SCrypt 算法。随后，区块链生态系统在全球不断进化，出现了首次代币发售**ICO**；智能合约区块链以太坊；“轻所有权、重使用权”的资产代币化共享经济；和区块链国家。目前，人们正在利用这一共享价值体系，在各行各业开发去中心化电脑程序(Decentralized applications, Dapp)，在全球各地构建去中心化自主组织和去中心化自主社区(Decentralized autonomous society, DAS)。

本书记录了本人从零开始学习区块链的心路历程，着重于经验分享和总结，同时也会有相关的概念解析，希望能够和大家一起为区块链的发展做出贡献。

在线浏览地址：https://blockchain.qikqiak.com

Github地址：https://github.com/cnych/blockchain-handbook


## 如何使用本书

**在线浏览**

访问 https://blockchain.qikqiak.com

**本地查看**

1. 将代码克隆到本地
2. 安装 gitbook：[Setup and Installation of GitBook](https://github.com/GitbookIO/gitbook/blob/master/docs/setup.md)
3. 执行 gitbook serve
4. 在浏览器中访问 http://localhost:4000
5. 生成的文档在 `_book` 目录下

**下载 PDF/ePub/Mobi 格式文档本地查看**

访问 [gitbook](https://www.gitbook.com/book/ydzsio/blockchain-handbook/details) 可以看到下载地址，可以下载根据最新文档生成的 **PDF/ePub/Mobi** 格式文档（文档的注脚中注明了更新时间），同时也可以直接在 gitbook 中阅读，不过 gitbook 不太稳定打开速度较慢，建议大家直接在 https://blockchain.qikqiak.com 浏览。


## 生成电子书
`GitBook`不仅可以生成静态网站，也可以将内容输出为电子书(ePub，Mobi，PDF)格式。

```
＃生成PDF文件
$ gitbook pdf ./ ./mybook.pdf

＃生成ePub文件
$ gitbook epub ./ ./mybook.epub

＃生成Mobi文件
$ gitbook mobi ./ ./mybook.mobi
```

**安装ebook-convert**

`ebook-convert`是生成电子书所必需的(epub，mobi，pdf)插件。

**Linux系统**

安装[Caliber应用程序](https://calibre-ebook.com/download)。

```
sudo aptitude install calibre
```
在某些Linux发行版中安装nodejs，您还需要手动创建一个nodejs软链接：

```
sudo ln -s /usr/bin/nodejs /usr/bin/node
```

**苹果OS X系统**

下载[Caliber应用程序](https://calibre-ebook.com/download)应用程序。将`calibre.app`移动到您的应用程序文件夹后，创建一个指向`ebook-convert`工具的软件链接：
```
sudo ln -s /Applications/calibre.app/Contents/MacOS/ebook-convert /usr/bin
```

这样就可以在任何目录下执行目录执行ebook-convert命令。

如果出现`Operation not permitted`异常，说明系统权限限制，需要配置环境变量的方式解决

```
sudo ln -s /Applications/calibre.app/Contents/MacOS/ebook-convert /usr/bin
ln: /usr/bin/ebook-convert: Operation not permitted
```

环境变量配置

先启动ebook-convert完成第一次启动配置，然后关闭。接着在命令行窗口修改环境配置文件，加入`EBOOK_PATH`（ebook-convert命令的所在目录）

```
vim ~/.bash_profile

export EBOOK_PATH=/Applications/calibre.app/Contents/MacOS
export PATH=$PATH:$EBOOK_PATH
```
然后刷新一下刚刚的配置:

```
source ~/.bash_profile
```

最后测试一下`ebook-convert`指令是否能正常被调用：

```
$ ebook-convert --version
ebook-convert (calibre 2.81.0)
Created by: Kovid Goyal <kovid@kovidgoyal.net>
```

大功告成！下面就可以使用`gitbook pdf ./ ./mybook.pdf` 命令把你的项目生成pdf文档了！

# 封面

所有格式电子书都可以创建封面。在安装完可以自己提供一个，或使用[autocover](https://plugins.gitbook.com/plugin/autocover)插件生成一个。

要创建封面，请在您的书的根目录下放置一个 `cover.jpg` 文件。还可以添加 `cover_small.jpg` 指定一个较小版本的封面。封面图片格式必须是 **JPEG** 文件。

一个合格的封面应遵守以下准则：
* `cover.jpg`的大小为1800x2360像素，`cover_small.jpg`为200x262像素
* 无边框
* 清晰可见的书名
* 任何重要的文本应该在小版本中可见

# 生成PDF

进入文档项目目录，输入`gitbook pdf ./ ./gitbook.pdf`

```
$ cd ~/gitbook-cn

$ gitbook pdf ./ ./gitbook.pdf
```

* pdf： 表示生成pdf格式，还有epub、mobi可选
* ./ ： 表示需要生成书籍的项目根目录
* ./gitbook.pdf : 表示生成书籍的名称
* 如果你的书籍有多种语言，就会生成多本书籍，书籍的名称会以语言结尾


## 如何贡献

### 提 issue

如果你发现文档中的错误，或者有好的建议、不明白的问题、不要犹豫，欢迎[提交issue](https://github.com/cnych/blockchain-handbook/issues/new)。

### 发起 Pull Request

当你发现文章中明确的错误或者逻辑问题，在你自己的 fork 的分支中，创建一个新的 branch，修改错误，push 到你的 branch，然后在[提交issue](https://github.com/cnych/blockchain-handbook/issues/new) 后直接发起 Pull Request。

### 贡献文档

#### 文档的组织规则

- 如果要创建一个大的主题就在最顶层创建一个目录；
- 所有的图片都放在最顶层的 `images` 目录下，原则上文章中用到的图片都保存在本地；
- 所有的文档的文件名使用英文命名，可以包含数字和中划线；
- `etc`、`manifests`目录专门用来保存配置文件和文档中用到的其他相关文件；

#### 添加文档

1. 在该文章相关主题的目录下创建文档；
2. 在 `SUMMARY.md` 中在相应的章节下添加文章链接；
3. 执行 `gitbook serve` 测试是否报错，访问 http://localhost:4000 查看该文档是否出现在相应主题的目录下；
4. 提交PR

## 社区&读者交流

- **微信群**：`区块链六点半`，扫描我的微信二维码，[阳明](https://blog.qikqiak.com/about)，或直接搜索微信号*iEverything*后拉您入群，请增加备注（姓名-公司/学校/博客/社区/研究所/机构等）。

