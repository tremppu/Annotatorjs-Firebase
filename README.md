## Annotatorjs-Firebase
Based on Annotatorjs - http://annotatorjs.org/

## Installation & Usage

First off all create an Google account. <br/>
Signup to https://firebase.google.com/ <br/>
Get your id and auth-token

> You'll need jquery and css first. 
> Add this inside the head tag
```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.4/jquery.min.js"></script>
<link rel="stylesheet" href="YOUR-PATH/annotator.min.css">
```
> Next add this inside the body tag
```html
<script src="YOUR-PATH/annotator-full.min.js"></script>

<script>
let firebase = "project-id-here"
let key = "secret-here"
let currentHost = (window.location.host).split('.').join("-")
let path = (window.location.pathname).split('/').join("-")
$('body').annotator()
  .annotator('addPlugin', 'Store', {
    // The endpoint of the store on your server.
    prefix: 'https://'+firebase+'.firebaseio.com/annotations/' + currentHost +'/'+ path,
    urls: {
      create: '/:id.json?auth=' + key,
      update: '/:id.json?auth=' + key,
      destroy: '/:id.json?auth=' + key,
      search: '.json?auth=' + key
    },
    loadFromSearch: {}
  });
</script>
```

## Credits
Based on Annotatorjs - http://annotatorjs.org/

## License
MIT
