# Github-Url
With an URL display a markdown file stored on Github.

## Quick start

1. Create a Meteor app
2. Remove demo files
3. Create client/contributions directories

```bash
$ meteor create bretzel
$ cd bretzel
$ rm bretzel.*
$ mkdir -p client/contributions
$ touch client/contributions/contributions.html
$ touch client/contributions/contributions.js
$ touch client/contributions/contributions.css
```
In *contributions.html*
```html
<Template name="contribution">
  <article class="contribution">
    {{#markdown}}{{contribution}}{{/markdown}}
  </article>
</Template>

In *contributions.js*
```javascript
Template.contribution.helpers({
  contribution: function () {
    return Session.get('github-url');
  }
});
```

In *contributions.css*
```css
.contribution {
  margin: 0px auto;
  width: 800px;
  display: block;
  padding: 3rem 0px 10rem;
  letter-spacing: 0.01rem;
  color: rgba(0,0,0,0.7);
}

.contribution h1 {
  font-size: 3.25rem;
  line-height: 3.5rem;
  margin-top: 3.5rem;
  margin-bottom: 1.75rem;
}

.contribution h2 {
  font-size: 1.9375rem;
  line-height: 1.75rem;
  margin-top: 3.5rem;
  margin-bottom: 1.75rem;
}

.contribution p,
.contribution ul,
.contribution ol,
.contribution pre,
.contribution table,
.contribution blockquote {
  margin-top: 1.75rem;
  margin-bottom: 1.75rem;
  font-size: 19px;
  line-height: 1.473684211em;
}

.contribution a {
  transition: all 200ms linear 0s;
  border-bottom: 1px solid #DCB107;
  color: #333;
  text-decoration: none;
}

.contribution a:hover,
.contribution a:focus {
  border-bottom: 1px solid #927504;
  background: #f9d236;
}
```

And test it!

```bash
$ meteor
$ open http://localhost:3000/daktary/daktary/README.md
```
## Navigation

You can add some smart links

```html
<template name="contribution_nav">
  <ul>
    <li>
      <a href="{{editor_link}}" target="blank">Editor</a>
    </li>
    <li>
      <a href="{{repo_link}}" target="blank">Repo</a>
    </li>
  </ul>
</template>
```
## Contact

> stephane.langlois@scopyleft.fr
> http://scopyleft.fr

