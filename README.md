# silent-dxt-js

This is a clone of [Robin Appelman's dxt.js](https://www.npmjs.com/package/dxt-js), except with the following line manually removed from the built `squish.js` file.

```js
process["on"]("uncaughtException",(function(ex){if(!(ex instanceof ExitStatus)){throw ex}}));
```

This line is problematic because it will catch all uncaught exceptions and blame them on squish.js, resulting in the entire minified squish.js library being output to the console every time your project has an unhandled exception, which looks like this:

![Screenshot of Cluttered Console](https://github.com/frankkulak/silent-dxt-js/blob/main/assets/console-error.png?raw=true)

I take no credit whatsoever for dxt.js or squish.js - this package just gets rid of a minor issue that has been bugging me for ages.
