---
title: "How to build a personal website (2)"
authors:
- Hyeseon Shin
url: others/how-to-build-web-2.html
date: "2024-02-04"
doi: ""

abstract: This posting introduces some customization options, especially for researchers. 
# summary: ...

tags:
# - Trade data
# - data collection
featured: false
draft: true
---

<hr>

In this post, I share some customization options for Hugo websites. There are, of course, many other great possibilities not listed here, and I’m also happy to learn more. If you have additional suggestions or notice any errors in this post, please feel free to email me.

#### 1. Changing basic information from the template
I will continue the posting assuming that you've chosen the Hugo [Academic CV](https://hugoblox.com/templates/details/academic-cv/) template. Using a template means that your website is built on some existing formatting, including the way your landing page look like, colors and fonts used, and so on. Some of the options can be easily changed within the template, while some are harder to change. 

As a first step, you can customize easy-to-fix stuffs. 

1-1. **TITLE and URL** | Go to `contig/_default/hugo.yaml`. Change `title` and `baseurl` of the website, 

1-2. **MENU**  |  Go to `config/_default/menus.yaml`. Here, you can control the top menu. The following is an example of your menu. You can define each menu item’s name and add a URL to it. 
- A URL such as `'#about'` or `'#contact'` will link to a section on your landing page whose `id` is set to `about` or `contact`.  
- A URL such as `'uploads/resume.pdf'` will link directly to a PDF file stored in the `static/uploads/` folder, where `static` is at the same level as `content`.  
- A URL like `/MyResearch` will link to a separate page whose content is stored in `content/MyResearch/_index.md`.  

<div class="highlight">
<pre><code class="language-bash">main:
  - name: Home
    url: '#about'
    weight: 10
  - name: CV
    url: 'uploads/resume.pdf'
    weight: 20
  - name: Research
    url: '/MyResearch'
    weight: 30
  - name: Contact
    url: '#contact'
    weight: 40
</code></pre>
</div>

1-3. **COLOR**  |  Go to `config/_default/params.yaml`. 
The default option is set as below. The `mode` has three options: `light`, `dark`, or `system`. 
The color option includes `blue`, `cyan`, `green`, `indigo`, `purple`, `red`, `rose`, `sky`, `teal`, and `zinc`. These are basic options you can easily choose from within the template. However, if you want to use your own colors, you can customize your color theme. See the [Hugo-Color Themes](https://docs.hugoblox.com/getting-started/customize/#appearance) for details.
<div class="highlight">
<pre><code class="language-bash">appearance:
  mode: light
  color: blue
</code></pre>
</div>




#### 2. Customizing the color theme

#### 3. Customizing the landing page using own Blocks

#### 4. How to make folding texts for abstracts
Folding text is useful for hiding research paper abstracts, allowing readers to expand and read them when they want to. Go to the `layouts/shortcodes/` folder and create a file named `detail-tag.html`. If the `layouts/shortcodes/` folders do not exist, create them manually. Make sure the `layouts` folder is at the same level as the `content` folder.

<div class="highlight">
<pre><code class="language-bash">&lt;details style="text-align: justify;"&gt;
  &lt;summary style="text-align: justify;"&gt;{{ (.Get 0) | markdownify }}&lt;/summary&gt;
  &lt;div style="text-align: justify;"&gt;
    {{ .Inner | markdownify }}
  &lt;/div&gt;
&lt;/details&gt;
</code></pre>
</div>

Now you can use this detail-tag function when writing in your `index.md` file like this (oh, I added the option to make the font size smaller):
<div class="highlight">
<pre><code class="language-bash">&lt;span style="font-size: smaller;"&gt;
{{&lt; detail-tag "Abstract" &gt;}}
Here comes the abstract.
{{&lt; /detail-tag &gt;}}
&lt;/span&gt;
</code></pre>
</div>

And this is the outcome.
<span style="font-size: smaller;">
{{< detail-tag "Abstract" >}}
Here comes the abstract.
{{< /detail-tag >}}
</span>

