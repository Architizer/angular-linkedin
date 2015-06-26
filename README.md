# angular-linkedin
> AngularJS module that wraps the LinkedIn SDK


#### Installation

Install the module with bower:

```
$ bower install angular-linkedin
```


#### Usage

Configure the service using `LinkedInProvider`. The options are identical to those
used to configure the [LinkedIn SDK](https://developer.linkedin.com/docs/js-sdk),
with the exception that `onLoad` accepts a function or array of functions.

The `LinkedIn` service is just a wrapper for the SDK. See the
[documentation](https://developer.linkedin.com/docs/js-sdk) for more details.


```js
var app = angular.module('MyApp', ['linkedin']);

app.config(['LinkedInProvider', function(LinkedInProvider) {

  LinkedInProvider.init({
    apiKey: 'YOUR_API_KEY',
    onLoad: function (sdk) {},
    authorize: true,
    lang: 'en_US'
  });
}]);

app.controller('MyController', ['LinkedIn', function (LinkedIn) {

    LinkedIn.User.authorize(function (response) {

      // Logic
    });
}]);
```
