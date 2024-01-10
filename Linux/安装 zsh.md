# 安装 zsh
`ubuntu` 下：
```shell
sudo apt-get install zsh
```

`mac`下：
```shell
brew install zsh
```
后面的内容两个系统通用

# 安装 oh-my-zsh
```shell
wget https://gitee.com/mirrors/oh-my-zsh/raw/master/tools/install.sh
```
然后给`install.sh`添加权限：
```shell
chmod +x install.sh
```

然后执行`install.sh`：
```shell
./install.sh
```
如果发现很慢，可以修改为`gitee`
```shell
vim install.sh
```
进入编辑状态：
找到以下部分：
```sh
# Default settings
ZSH=${ZSH:-~/.oh-my-zsh}
REPO=${REPO:-ohmyzsh/ohmyzsh}
REMOTE=${REMOTE:-https://github.com/${REPO}.git}
BRANCH=${BRANCH:-master}
```
然后将中间两行改为：
```sh
REPO=${REPO:-mirrors/oh-my-zsh}
REMOTE=${REMOTE:-https://gitee.com/${REPO}.git}
```
然后保存退出：`ESC + :wq`
重新执行即可。

# 配置 zsh
```shell
vim ~/.zshrc
```
### 修改主题：
```shell
ZSH_THEME="robbyrussell"
```
改为
```shell
ZSH_THEME="ys"
```
### 修改插件：
```
plugins=(git)
```
改为
```
plugins=(git zsh-syntax-highlighting zsh-autosuggestions)
```
- 如果`.bash_profile`中有配置内容的话，还需要增加一行：
```shell
source ~/.bash_profile
```

接下来我们可以更新配置文件：
```shell
source .zshrc
```
发现同上报错是正常的，因为我们还没有下载插件，直接就配置了。

# 安装插件
### 1. 安装zsh-syntax-highlighting
```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
- 用不了 Github的， 可以用下面这个 gitee的
```shell
git clone https://gitee.com/zjy_1671/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
### 2. 安装zsh-autosuggestions
```shell
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
- 用不了 Github的， 可以用下面这个 gitee的
```shell
git clone https://gitee.com/chenweizhen/zsh-autosuggestions.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

安装完成后，重新更新配置：
```shell
source .zshrc
```
在编辑指令的时候，对于之前使用过的指令，按`→`即可快速补全，非常好用。


### 参照
[CSDN参考地址](https://blog.csdn.net/qwe641259875/article/details/107201760)