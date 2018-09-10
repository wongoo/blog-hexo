## How to use Hexo and deploy to GitHub Pages
* https://github.com/hexojs/hexo
* https://hexo.io/docs/

### 1. Install Hexo
```
$ sudo npm install -g hexo-cli

$ hexo -v
hexo-cli: 0.1.9
os: Darwin 14.3.0 darwin x64
http_parser: 2.3
node: 0.12.7
v8: 3.28.71.19
uv: 1.6.1
zlib: 1.2.8
modules: 14
openssl: 1.0.1p
```

### 2. Create a project for your GitHub Pages
```
$ hexo init wongoo.sisopipo.com
INFO  Copying data to ~/***/wongoo.sisopipo.com
INFO  You are almost done! Don't forget to run 'npm install' before you start blogging with Hexo!

$ cd wongoo.sisopipo.com

$ npm install
```

### 3. Run a test server for your page on Mac
```
$ hexo server
INFO  Hexo is running at http://0.0.0.0:4000/. Press Ctrl+C to stop.
```

### 4. Set information for your new blog
https://hexo.io/docs/configuration.html
```
$ vi _config.yml

~~~~~~~~~~~~~~~~~~ _config.yml ~~~~~~~~~~~~~~~~~~
# Site
title: wongoo's note
subtitle:
description: wongoo's personal blog
author: wongoo
language:
timezone: Japan

# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://wongoo.sisopipo.com/
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:
```

### 5. Set information to use Git
https://github.com/hexojs/hexo-deployer-git
```
$ npm install hexo-deployer-git --save
$ vi _config.yml

~~~~~~~~~~~~~~~~~~ _config.yml ~~~~~~~~~~~~~~~~~~
# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: git@github.com:wongoo/wongoo.sisopipo.com.git
  branch: master
```

### 6. Set "watch" before starting your work
"watch" command can monitor your files.  
https://hexo.io/docs/generating.html
```
$ hexo generate --watch
```

### 7. Create a new post file
```
$ hexo new first-post
INFO  Created: ~/***/wongoo.sisopipo.com/source/_posts/first-post.md
```

### 8. Edit the above file with Markdown or Hexo's Helper
Hexo's Helper  
https://hexo.io/docs/helpers.html  
I use Atom with "shift + control + m" when I use Markdown :-)  
https://atom.io/

### 9. Delete "source/_posts/hello-world.md"
It's not necessary to deploy.

### 10. Deploy your new blog!!
https://hexo.io/docs/deployment.html
```
$ hexo clean
$ hexo deploy
```
After writting the above command, you can see your new blog on GitHub Pages.  
http://******.sisopipo.com/

### 11. Change your blog theme
https://github.com/hexojs/hexo/wiki/Themes
```
For instance, How to use the following theme.
https://hexo.io/hexo-theme-light/

## Install it
$ cd wongoo.sisopipo.com
$ git clone git://github.com/tommy351/hexo-theme-light.git themes/light

## Update the above files
$ themes/light
$ git pull

## Set information to use the theme
$ cd wongoo.sisopipo.com
$ vi _config.yml

~~~~~~~~~~~~~~~~~~ _config.yml ~~~~~~~~~~~~~~~~~~
# Extensions
## Plugins: http://hexo.io/plugins/
## Themes: http://hexo.io/themes/
theme: light
```

### 12. Create a new page file
https://hexo.io/docs/writing.html
```
$ hexo new page aboutme
INFO  Created: ~/***/wongoo.sisopipo.com/source/aboutme/index.md

$ cd source/aboutme/

$ vi index.md
```

### 13. Use "Read More"
Write `<!-- more -->` in your articles.  

### 14. Use Plugins
https://github.com/hexojs/hexo/wiki/Plugins

