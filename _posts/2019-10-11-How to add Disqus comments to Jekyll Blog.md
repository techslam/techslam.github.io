---
title: "How to add Disqus comments to Jekyll Blog"
date: 2019-10-11 21:45:00 +0800
categories: [Jekyll]
tags: [disqus]
---

So you have set up your brand new Jekyll blog and now here looking for setting up a commenting system on it. Look no where, as this post is exactly what you been looking for.

I have read numerous articles on setting up comments on a Jekyll powered static blog, but found using Disqus as the most easiest method.

1. Sign Up for a [Disqus](https://disqus.com/) account.

2. Register your blog/site in Disqus and create a short-name.

3. Open your Jekyll site's `config.yml` and add the below code 

```
# Disqus Comments
disqus:
    # Leave shortname blank to disable comments site-wide.
    # Disable comments for any post by adding `comments: false` to that post's YAML Front Matter.
    shortname: disqus_shortname
```

Remember to change the `disqus_shortname` with your site's shortname that you created in step 2.

4. Create a file called `disqus.html` inside Jekyll's `_includes` folder and add below code in it and save.

```javascript
<div id="disqus_thread"></div>
  <script>
    var disqus_config = function () {
      this.page.url = '{{ page.url | absolute_url }}';
      this.page.identifier = '{{ page.url | absolute_url }}';
    };
    (function() {
      var d = document, s = d.createElement('script');
      s.src = 'https://{{ site.disqus.shortname }}.disqus.com/embed.js';
      s.setAttribute('data-timestamp', +new Date());
      (d.head || d.body).appendChild(s);
    })();
  </script>
  <noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>
```

5. Finally, edit the `post.html` file located inside `_layout` folder and add the following code just after the end of `</article>` tag. If you dont see the article tag, probably due to usage of some custom themes, then in that case look for 
{% raw %} ` {{ content }} ` {% endraw %} and place the code just after that -

{% raw %}
```liquid 
{% if site.disqus.shortname %}
{%   include disqus.html %}
{% endif %}
``` 
{% endraw %}

Once you have completed all the above steps, you can now commit your changes and push it to your Live site :

```shell

git add --all

git commit -m "add disqus"

git push -u origin master

```
That's all, your static Jekyll website is now powered with Disqus commenting system.
Please let me know through comments if this post was helpful to you, or if you need any help setting this up. Good Luck :)

## See Also

* [Change Jekyll Template]({{ site.baseurl }}/posts/Change-Jekyll-Template/)