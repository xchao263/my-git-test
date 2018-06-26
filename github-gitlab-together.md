## github 与 gitlab 在本地同时共存解决方案
## 采用修改 ~/.ssh/config 配置实现
## 步骤：

## 1、在 ~/.ssh/config 文件中添加如下内容
Host github.com
  User xchao263@gmail.com
  HostName github.com
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/id_rsa_github


Host git.tusvn.com
  User xiongchao@tusvn.com
  HostName git.tusvn.com
  PreferredAuthentications publickey
  IdentityFile ~/.ssh/id_rsa

## 2、生成 github 的公私密钥
## ssh-keygen -t rsa -b 4096 -f ~/.ssh/id_rsa_github -C 'xhao263@gmail.com'

## 将 github 公钥拷贝到剪切板
## clip < ~/.ssh/id_rsa_github.pub

## 在 github 站点上 配置 SSH KEY
## 粘贴 ~/.ssh/id_rsa_github.pub 中的内容 到 github SSH keys

## 3、本地项目
## 配置使用 github 
## git clone git@github.com:xchao263/my-git-test.git
## git config --local user.name  'xchao263'
## git config --local user.email 'xchao263@gmail.com'
