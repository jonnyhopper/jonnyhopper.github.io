+++
title = "building a blog"
author = "jonny hopper"
featured = "building-a-blog.jpg"
featuredalt = ""
featuredpath = "date"
date = "2017-01-01T22:23:53Z"
linktitle = ""
description = "great learnings!"
categories = ["blog","learning"]
type = "post"

+++

The first thing I needed to learn when I decided to start a blog about all the things I need to learn was how to start a blog. Apparently you need a nice looking image at the top of the post! I took this one in the Under-5's play area in the Science Museum in London (Don't panic, I was with my kid).

<!--more-->

So first off, I remembered reading a tweet somewhere talking about [Hugo](gohugo.io) as a decent alternative to using Wordpress - or anything else - for a blog. I think it was [Don Williamson](www.twitter.com/donzanoid), by the way. I thought "Don's a smart dude and I remember trying to use Wordpress that one time, so what can go wrong?"

(Spoiler: It actually went pretty well. Well enough that this blog is being served by Hugo and I didn't drown my laptop in tears trying to make it work.)

### then i typed 'hugo blog tutorial' into google

So I went on Google and typed "hugo blog tutorial", and the post from [Nic Raboy](https://www.thepolyglotdeveloper.com/2016/03/use-hugo-create-awesome-static-websites-blogs/) looked good. Check it out! It's a no-frills start-em-up with the pros and cons of the platform, and the (approximately 3) things you need to do to get it running. It's kind of not as simple as Wordpress or Blogspot because you have to type stuff, but like I said, it's like 3 things.

Nic mentions there aren't many good themes for Hugo, but he likes [Future Imperfect](http://themes.gohugo.io/future-imperfect/). 
So I'm using that, with a couple of modifications. I wasn't super keen on the default Sans Serif font for the body content so I changed it to [Merryweather](https://fonts.google.com/specimen/Merriweather). And I thought it would be nice to have post previews on the front page rather than the whole thing (for now, at the time of writing, this may change etc), so I monkeyed around with some of the template guts. Hugo uses HTML snippets with a bunch of custom keywords to generate its pages. I created a new snippet called ```layout/posts/content-preview.html``` which is super lame and looks like this:

```
<article class="post">
    {{ .Render "header" }}

    {{ .Render "featured" }}
    <div id="content">
        {{ .Summary }}
        {{ if .Truncated }}
        <p>
        <div class="read-more-link">
            <a href="{{ .RelPermalink }}">Read More…</a>
        </div>
        {{ end }}
    </div>
    <footer>
        {{ .Render "footer-category" }}
    </footer>
</article>
{{ .Render "prev-next" }}
```

Which basically shows the top bit. The ```.Summary``` keyword is the important bit, and you have to remember to add ```<!--more-->``` into your post, otherwise it just chooses the first 70 words and mullers the formatting.

Summary: It's a bit cack but I guess it works? 

### then i realised i needed to host it somewhere

Again, I randomly read that using Github pages is a good idea! So that is what I'm doing. 







