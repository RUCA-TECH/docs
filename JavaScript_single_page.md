Single-page websites and web applications have become a standard over the last years. Getting the tracking of such websites and apps right is crucial to your success as you need to ensure the measured data is meaningful and correct.

## Tracking a New Page View
The challenge begins when you need to track a new page view. A single-page application is different from a usual website as there is no regular new page load and [ruca.tech](https://ruca.tech) cannot detect automatically when a new page is viewed. This means you need to let [ruca.tech](https://ruca.tech) know whenever the URL and the page title changes. You can do this using the methods setCustomUrl and setDocumentTitle like this:

```js
window.addEventListener('hashchange', function() {
        _odaq.push(['setCustomUrl', '/' + window.location.hash.substr(1)]);
        _odaq.push(['setDocumentTitle', 'My New Title']);
        _odaq.push(['trackPageView']);
});
```



## Resetting previously set custom variables
If you have set any Custom Variables in scope “page”, you need to make sure to delete these custom variables again as they would be attributed to the new page view as well otherwise:

```js
_odaq.push(['deleteCustomVariables', 'page']);
_odaq.push(['trackPageView']);
```

## Updating the referer
Depending on whether you want to track the previous page as a referrer for the new page view, you should update the referrer URL by setting it to the previous page URL:
```js
_odaq.push(['setReferrerUrl', previousPageUrl]);
_odaq.push(['trackPageView']);
```

