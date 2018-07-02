# ruca.tech Tracking SDK For desktop and Mobile Web



## Minimal Integration

```js
<!-- ruca.tech integration -->
    <script type="text/javascript">
      var _odaq = _odaq || [];
      _odaq.push(['setSiteId', 'YOUR SITE ID']);
 _odaq.push(['trackPageView']);
        (function() {
          var oda = document.createElement('script');
          oda.type = 'text/javascript';
          oda.async = true;
          oda.defer = true;
          oda.src = 'https://cdn.ruca.tech/rta.js';
          var s = document.getElementsByTagName('script')[0];s.parentNode.insertBefore(oda, s);
        })();
    </script>

    <noscript>
      <div style="display:inline;">
        <img height="1" width="1" alt="" src="//fp.ruca.tech/pixel.gif?accountId=YOUR SITE ID&amp;js=no" style="border-style:none;" />
    </div>

    </noscript>
<!-- End of ruca.tech integration code -->
```

***
***
***





### Tracking For Single Page WebApps
In this example we show how everything works together assuming you want to track a new page whenever a hash changes:

```js
window.addEventListener('hashchange', function() {
    _odaq.push(['setSiteId', 'YOUR SITE ID']);
    _odaq.push(['trackPageView']);

});
```
***
***
***


### Event Tracking for Analytics
Tracking Events is a very useful way to measure interactions your users make with your website content, which are not directly page views or downloads. Typically events are used to track clicks on elements in your pages such as menu, widgets, Flash elements, AJAX actions, or even actions within games or media content.

An Event has four components.:


|  Field Name                | Value Type           | Required | Description  |
| -------------        |:-------------: | ---------:   |---------:   |
| eventCategory   | string        | yes |Typically the object that was interacted with (e.g. 'Video')|
| eventAction   | string        | yes |The type of interaction (e.g. 'play')|
| eventLabel   | string        | yes |Useful for categorizing events (e.g. 'Fall Campaign')|
| eventValue   | integer        | no |A numeric value associated with the event (e.g. 42)|

The following command sends an event to ruca.tech Analytics indicating that the fall campaign promotional video was played:

### Javascript trackEvent()
```js
_odaq.push(['trackEvent', 'Videos', 'Play', 'Fall Campaign']);
```


The following command sends an event to ruca.tech Analytics indicating that the Farm Birds promotional game was downloaded and played and player got score of 2045:

### Javascript trackEvent()
```js
_odaq.push(['trackEvent', 'Game', 'Download and Play', 'Farm Birds',2045]);
```



