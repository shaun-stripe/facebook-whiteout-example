The latest Facebook app for android will white-out pages when `window.open`
is called.  No tab is opened, and the page is still left running and invisible.
The returned window object for the tab is also blank:

```js
var tab = window.open("http://example.com", "_blank");
tab.location.href // => "about:blank"
tab.closed // => false
```

To try, start a local server like this:

```
$ python -m SimpleHTTPServer 8000
$ ngrok http 8000
```

Then post a private message on your facebook wall containing your ngrok link
to try the page and reproduce the issue.  The page will white-out and you
will see an alert containing the html of the invisible page:

1. click | 2. whiteout | 3. alert
---|---|---
![button](screen-button.png) | ![white](screen-white.png) | ![alert](screen-alert.png)
