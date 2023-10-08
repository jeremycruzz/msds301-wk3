### MSDS 431 - Assignment 3

##### Links to Live Website

- https://jeremycruzz.github.io/msds301-wk3/
- https://jeremycruz.dev/

##### Running this site locally

- `git clone --recurse-submodules git@github.com:jeremycruzz/msds301-wk3.git` Clone WITH SUBMODULES
- `hugo server -D --buildFuture` 


##### Notes

When modifying this repo, make sure to not change any of the files within the `/themes/<whatever-theme>/` folder. It will make your submodule dirty if you do. If you need to make adjustments to any of the files, copy the file and make edits outside of the themes folder in the matching directory.


<details>
<summary>Example</summary>
<br>

I wanted to use an actual logo instead of generating a logo based on this font. I also was running into issues since the template was meant to be a single page application. I copied the following file into `./layouts/partial/header.html` to override this layout.

```html
// ./themes/layouts/partial/header.html
<header class="header fixed-top rad-animation-group" id="header">
  <div class="container rad-fade-in">
    <nav class="navbar navbar-expand-lg navbar-light p-0">
      <a class="navbar-brand" href="{{ .Site.BaseURL | absURL }}">
        <span>{{ .Site.Params.logo.text1 }}</span>
        <span>{{ .Site.Params.logo.text2 }}</span>
        <!-- <img
          class="img-responsive"
          src="img/logo-dark.png"
          srcset="img/logo-dark.png 1x, img/logo-dark@2x.png 2x"
          alt="Header Logo"
        /> -->
      </a>
      ...
```

then made the adjustments I needed.

```html
<header class="header fixed-top rad-animation-group" id="header">
  <div class="container rad-fade-in">
    <nav class="navbar navbar-expand-lg navbar-light p-0">
      <a class="navbar-brand" href="{{ .Site.BaseURL | absURL }}">
        <img
          class="img-responsive"
          src="{{ $.Site.BaseURL }}img/general/jclogo.png"
          srcset="{{ $.Site.BaseURL }}img/general/jclogo.png 1x, {{ $.Site.BaseURL }}img/general/jclogo.png 2x"
          alt="Header Logo"
        />
      </a>
```

</details>

Overall I had fun with this assignment. I always thought about having a personal website so this was the perfect opportunity to make it. I really like the layout but since it was a single page app I added the blog to get familiar with the content section which I ran into issues explained in this [entry](https://jeremycruz.dev/blog/#entry-day-2). While I prefer to write my web applications in react, its cool that Go has a version of their own razor pages like C#. 