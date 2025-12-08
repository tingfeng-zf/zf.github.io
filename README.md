你好，这是张锋的博客
访问地址：https://tingfeng-zf.github.io/zf.github.io
前文：博客文件夹名字为：zf-test
1.创建一个新的Hexo项目
hexo init zf-blog

2.进入项目文件
cd zf-blog

3.安装Hexo项目所需的依赖
npm install
# 如果机房下载慢，将我分发的文件夹放到D盘，以管理员模式打开Git Bash执行如下命令使用离线安装：
# npm install --registry=file:///d/hexo-offline-packages

4.创建测试文章
#gitbash 创建新文章
hexo new "张锋-12:19"
# 编辑文章内容
# 文件位置：source/_posts/我的第一篇文章.md
vim source/_posts/张锋-12:19.md

# 你好，世界！
## 这是第一篇文章
- 你好！
欢迎光临！

- 世界！
hello world!
哈哈哈！


5.启动本地服务器测试
hexo s

6. 编辑文章内容
自由发挥

https:
https://github.com/tingfeng-zf/zf.github.io

ssh:
git@github.com:tingfeng-zf/zf.github.io

3-1：设置Git全局用户名和邮箱
# 设置Git全局用户名和邮箱（重要！）
git config --global user.name "tingfeng-zf"
git config --global user.email "tingfeng_0510@outlook.com"

#仓库名：zf.github.io
3-2:
ssh-keygen -t rsa -b 4096 -C "tingfeng_0510@outlook.com"

cat ~/.ssh/id_rsa.pub

3. 添加公钥到GitHub
1. 登录 GitHub → Settings → SSH and GPG keys → New SSH key
2. 粘贴公钥内容到 Key ，设置标题（如zf-test ）
3. 点击 Add SSH key

4. 测试 SSH 连接
ssh -T git@github.com
# 看到 "Hi username! You've successfully authenticated..." 表示成功

3.3 配置 Hexo 部署到 GitHub
1. 在 Hexo 项目根目录（ C:\Users\zf\zf-test ）下安装 hexo-deployer-git ，以管理员身份启动 Git
Bash 执行：
npm install hexo-deployer-git --save
#这一步已经在zf-test目录下运行了

2. 编辑 Hexo 项目根目录下的 _config.yml文件
ls





vim _config.yml
#注意：你的用户名/你的用户名 需要替换为你自己的用户名
deploy:
type: git
repo: git@github.com:tingfeng-zf/zf.github.io.git
branch: main

3. 保存文件后，可以验证配置是否正确：
hexo config deploy

4.首次部署到 Github
# 清理并生成静态文件
hexo clean && hexo g
# 部署到 Gitee
hexo deploy
# 一键部署：hexo clean && hexo generate && hexo deploy

出现下面的提示则成功：
remote: Resolving deltas: 100% (xx/xx), done.
To github.com:用户名/用户名.github.io.git
........................................................
branch 'master' set up to track 'git@github.com:用户名/用户名.github.io.git/main'.
INFO Deploy done: git

5.验证访问： 
https://tingfeng-zf.github.io/zf.github.io/

#在vim _config.yml这一步时，
url: https://tingfeng-zf.github.io
root: /zf.github.io/
页面才终于打开了
