# Steps to Create From Scratch

Build a Blog from Scratch with Eleventy: "[Demo](https://11ty-scratch-blog.netlify.com)"

Watch > "[6 minutes to Build a Blog from Scratch.](https://www.youtube.com/watch?v=kzf9A9tkkl4)"

## Create the Site Index File

Create `index.html`
Emmet: `html:5`

## Run the Develop Server

`npx @11ty/eleventy --serve`

## Create the Posts

Create `posts/`
Create `posts/post-1.md`


## Create the `layout` Layout

Create `_includes/layout.html`
Emmet: `html:5`

## Create `posts` Directory Data File

Create `posts/posts.json`

```jsx
{
  "layout": "layout.html",
  "tags": "post"
}
```

## Display `posts` Collection on Home Page

Add to `index.html`:

```jsx
## Blog Posts

{% for post in collections.post %}
{{ post.data.title }}
{% endfor %}
```

## Create Linked List of Posts

Modify previous `for` loop:

```jsx
<ul>
{% for post in collections.post %}
<li><a href="{{ post.url }}">{{ post.data.title }}</a></li>
{% endfor %}
</ul>
```

## Create `netlify.toml`

```yaml
[build]
  # Directory (relative to root of your repo) that contains the deploy-ready
  # HTML files and assets generated by the build. If a base directory has
  # been specified, include it in the publish directory path.
  publish = "_site"

  # Default build command.
  command = "npm run build"
```

## Push to Github

Create a repo and push project to Github (_instructions outside the scope of these steps_).

## Deploy to Netlify

1. Create a [Netlify](https://netlify.com) account, use GitHub login for fastest deply
1. Select "Create from Git"
1. Link to Github and select your repo
1. If you run Eleventy locally you can drag your _site folder to drop.netlify.com to upload it without using git.
1. Netlify will recognize the values in `netlify.toml` and you can deploy! 🎉
