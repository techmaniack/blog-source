+++
date = "2016-07-12T22:06:43+05:30"
draft = false
title = "Hello hugo!"
author = "kn330"

+++


I have been wanting to start my blog again for a long time. Github Pages sounded a reliable option and moreover it is free!.  

Github pages allows you to host a website directly from your github repository. This means that you do not need to get into the hassles of setting up a server or deal with cloud services like heroku. Just push your code to github and the content gets served from Githubs servers.  

With the recent update your content gets served over https but bear in mind that Github Pages is not for anything serious. (Don't plan to run a social network out of it. You will not be able to do it anyways). You do not get a database with Github Pages. For more information on the features and limitations of Github Pages head [here](https://help.github.com/articles/what-is-github-pages)  

Github prefers Jekyll to setup your blog, I am using Hugo. Hugo is a static web site generator written in Go. It is just a matter of choice. I am also taking the liberty to simplify the deployment process, for a more cleaner git work flow head here. 

1. __Install Hugo on your local machine.__  
   Download and install the package for your operating system from [here](https://github.com/spf13/hugo/releases).  
   I am using Ubuntu 64 bit and if you are using the same then follow these commands:  
   `$ wget https://github.com/spf13/hugo/releases/download/v0.16/hugo_0.16-1_amd64.deb`  
   `$ sudo dpkg -i hugo_0.16-1_amd64.deb`  
   That's it you are good to go. Check your hugo installation with hugo help  
   `$ hugo help`  
   
2. __Setting up your hugo project.__  
   Setup a new hugo project with the command:  
   `$hugo new site blog`  
   This will create a new directory named `blog/` with the boiler plate hugo code.
   
3. __Writing your first post.__  
   You would now want to write a post. Go ahead and do it as follows  
   `$ cd blog/`  
   `$ hugo new post/hello-world.md`  
   This will create the file `content/post/hello-world.md` inside the `blog/content/post/` directory. Open this file in the editor of your choice and start writing  
   ```md
       +++
       date = "2016-07-12T22:06:43+05:30"
       draft = false
       title = "Hello world"
       
       +++

        Start writing here...
    ```
    Make sure you set __draft__ = __false__
   
4. __Test your blog before making it live.__  
   Hugo has an in-built http server that runs on your local machine. This will help you review the content locally before making it live.  
   `$ hugo server`  
   Open you browser and visit [http://localhost:1313/](http://localhost:1313/)  
   You will see a blank page. This is normal as Hugo needs a theme to render content.
   
5. __Setting up theme__  
   Hugo has a variety of themes which you can browse online at [Hugo Themes](http://themes.gohugo.io/). For tutorial purpose we will use hugo_theme_robust.  
   `$ mkdir themes`  
   `$ cd themes`  
   `$ git clone https://github.com/dim0627/hugo_theme_robust.git`  
   You might want to remove the _.git_ from the theme to avoid conflict with your git repo.  
   `$ rm hugo_theme_robust/.git`  
   Finally add the theme name to hugo config (__config.toml__)  
   ``` toml
       baseurl="https://username.github.io/"
       languageCode="en-us"
       title="My Blog"
       theme="hugo_theme_robust"
   ```

6. __Test your blog before you make it live.__  
   Follow step 4   

7. __Push your blog to Github__  
   After you have verified your work and are ready to make the content live, you need to build your website locally and push it to github. Hugo website is built by running `$ hugo` commmand without arguements. If this command is succesful you will see a `public/` directory created inside your project. We need to push the contents of this directory to our github pages repo.  
   `$ cd public`  
   `$ git init`  
   `$ git add .`  
   `$ git commit -m "Initial commit!"`  
   `$ git remote add origin git@github.com:techmaniack/techmaniack.github.io.git`  
   `$ git push origin master`  
   
   That is it! Go check your beautiful blog on __username.github.io__

