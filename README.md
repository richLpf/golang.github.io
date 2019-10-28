# Introduction

> 开发条件

`node` `npm` `gitbook-cli`

> 具体过程

```
# 安装gitbook-cli
npm install -g gitbook-cli
gitbook -V

git clone git@github.com:richLpf/golang.github.io.git

cd ./golang.github.io

# local: git checkout dev

gitbook install

# 本地运行 http://localhost:4000
gitbook serve 

git checkout master 

git merge dev

# 打包发布
gitbook build ./ ./docs

# 提交
git add .

git commit -m "test"

git push

```

静态网站地址： https://richlpf.github.io/golang.github.io/