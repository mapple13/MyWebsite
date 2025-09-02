---
title: "How to build a personal website (1)"
authors:
- Hyeseon Shin
url: others/how-to-build-web-1.html
date: "2024-02-04"
doi: ""

abstract: This is a posting on how to set up a personal website using Hugo and Visual Studio Code.
# summary: ...

tags:
# - Trade data
# - data collection
featured: false
draft: true
---

<hr>

Building a personal website is one of the things to do for PhD students, especially when preparing for the job market. In this post, I share some guidance on building a customized personal website using [Hugo](https://hugoblox.com/) and Visual Studio Code, based on my own experience creating the site you see here.

There are plenty of other guides on building a personal website. I was personally inspired by Prof. Alex Hollingsworth’s [posting](https://hollina.github.io/make-a-job-market-website.html), which I found both helpful and motivating. The instructions were based on R and the Wowchemy theme, but the same functions can now be done by **Hugo Blox** and **Visual Studio Code**. This post outlines key steps for building a personal website with Hugo and also serves as my own reference.

#### Why using Hugo 
The pros of using Hugo are that almost everything can be customized within the website—such as fonts, colors, and designs—without going too deep into web programming. It can also be relatively cheap. Using Hugo itself is free unless you choose a paid theme, and you only need to purchase your own domain. Domains are not too costly (around $10–20 per year) unless you are looking for something very common and popular.

However, it can take a bit more time compared to using Google Sites. For this reason, I recommend making your personal website roughly a year before you are on job market (you might want to make some changes to the original template as you update your website), so that you can become familiar with working in Hugo and not feel too pressed for time. If you are in a hurry, using Google Sites could be a better option.


#### Step1. Get your template in Github. 
Go to [Hugo](https://hugoblox.com/templates/) and choose one of the free templates available. 
I’m using the [Academic CV](https://hugoblox.com/templates/details/academic-cv/) template, which supports most of the features PhD students and researchers need.
Click “Edit” to start. If you don’t have a GitHub account yet, you will need to create one.
This will copy the website template to your GitHub account.
Give your repository a name by entering it in the “Repository name” field, then click “Create repository.”

#### Step2. Download some softwares. 
I’m writing this post for Windows users. If you’re using a Mac, you’ll need to find the appropriate version for your system. For that, check out the [Hugo installation guidance](https://gohugo.io/installation/). 
Some of the following installations may not be strictly needed, but are considered useful when working with Hugo.
* Download and install [Visual Studio Code](https://code.visualstudio.com/). 
* Download and install [GIT](https://git-scm.com/downloads) 
* Downlaod and install [Go](https://go.dev/doc/install)
* Install **Dart Sass**: open Windows PowerShell in your computer and type     
<div class="highlight">
  <pre><code class="language-bash">npm install -g sass</code></pre>
</div> 

* Install **Scoop**: open Windows PowerShell in your computer and type   
<div class="highlight">
<pre><code class="language-bash">Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
</code></pre>
</div> 

* Install **Hugo extended**: open Windows PowerShell in your computer and type     
<div class="highlight">
  <pre><code class="language-bash">scoop install git go hugo-extended nodejs</code></pre>
</div> 


#### Step3. Setup Visual Studio Code 
After installing Visual Studio Code, open it and click the **Extensions** tab on the left sidebar. Search for "Github Pull Requests" and install. 

Next, open the **Source Control** tab on the left sidebar.
Click "Clone Repository", then paste your GitHub repository URL.
Choose the local folder where you want to store your website files. Once you click, the files will begin downloading.


#### Step4. Customize your website. 
Now you have your website template stored on your local computer. You can customize the webiste to make your own. There are so many things that can be customized, so let me cover it in another [posting](/others/how-to-build-web-2.html).

For now, let's just check the current template. 
Go to the menu bar on top, and find **Terminal** and click **New terminal**. 
Now you see the terminal box below where you can type your codes. 
In the terminal, type:
<div class="highlight">
<pre><code class="language-bash">hugo server
</code></pre>
</div> 

You now see messages like <```Web Server is available at http://localhost:1313/```> in your terminal. Clicking the address will open your website in your web browser, allowing you to preview how it will appear once published.
Sometimes, your changes are not immediately reflected. Then run the following command in the terminal:
<div class="highlight">
<pre><code class="language-bash">hugo server --ignoreCache
</code></pre>
</div> 



#### Step5. Make your website alive!
You can purchase your own domain. I purchased mine here: [Namecheap](https://www.namecheap.com/), as recommended by Hugo. 
After you purchase, change your ```baseurl``` under ```config\_default\hugo.yaml```. 

Once that’s done, you can publish your website and make it live. In the terminal, run:
<div class="highlight">
<pre><code class="language-bash">git init
git add .
git commit -m "fix codes (whatever note you want here)"
git push origin
</code></pre>
</div> 

It can take 24-48 hours to work, so wait a bit. 




#### Other useful links:
[Hugo blox - getting started](https://bootstrap.hugoblox.com/getting-started/) <br>
[Dsquintana blog - A non-technical guide on making a personal academic website for free](https://www.dsquintana.blog/create-an-academic-website-free-easy-2020/)

<!-- 

#### Others
Here are other tutorials by [Dsquintana](https://www.dsquintana.blog/free-website-in-r-easy/). 


<br>
 -->
