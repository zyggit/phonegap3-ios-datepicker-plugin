# DatePicker iOS Plugin for using PhoneGap 3.0

This is a port (incl. new features) of the iOS DatePicker plugin hosted on [https://github.com/phonegap/phonegap-plugins/tree/master/iOS/DatePicker](https://github.com/phonegap/phonegap-plugins/tree/master/iOS/DatePicker)

## Screen shot

[![screen shot](https://raw.github.com/sectore/phonegap3-ios-datepicker-plugin/master/assets/screenshot.png)](https://github.com/sectore/phonegap3-ios-datepicker-plugin)


## Installation

1) Make sure that you have [Node](http://nodejs.org/) and [Cordova CLI](https://github.com/apache/cordova-cli) or [PhoneGap's CLI](https://github.com/mwbrooks/phonegap-cli) or [Cordova Plugman](https://github.com/apache/cordova-plugman/) installed on your machine.

Also you will need Xcode v.4.2 or newer to support the feature called ["Automatic Reference Counting"](http://developer.apple.com/library/ios/#documentation/DeveloperTools/Conceptual/WhatsNewXcode/Articles/xcode_4_2.html)

2) Add a plugin to your project using [Cordova CLI](https://github.com/apache/cordova-cli):

```bash
cordova plugin add https://github.com/sectore/phonegap3-ios-datepicker-plugin
```

Or using [Phonegap CLI](https://github.com/mwbrooks/phonegap-cli):

```bash
phonegap local plugin add https://github.com/sectore/phonegap3-ios-datepicker-plugin
```

Or using [plugman CLI](https://github.com/apache/cordova-plugman#command-line-usage):

```bash
plugman --platform ios --project ./platforms/ios --plugin https://github.com/sectore/phonegap3-ios-datepicker-plugin
```


3a) Register plugin within `config.xml` of your app

```xml
<feature name="DatePicker">
    <param name="ios-package" value="DatePicker"/>
</feature>
```

3b) If you are using [PhoneGap build service](https://build.phonegap.com/) add to `config.xml`

```xml
<gap:plugin name="de.websector.datepicker" />
```

4) The `clobber` definition of the plugin is called `datePicker`. So you can reference to the plugin from anywhere in your code.

Example:

```js
// defining options
var options = {
  date: new Date(),
  mode: 'date'
};
// calling show() function with options and a result handler
datePicker.show(options, function(date){
  console.log("date result " + date);  
});
```

Check section ["Options"](#options) below to see all options.

## Options

### mode
The mode of the date picker.

Typ: `String` 

Values: `"date"` / `"time"` / `"datetime"`

Default: `'datetime'`

### date
Selected date.

Typ: `String`

Default: `new Date()`

### allowOldDates
Shows or hide dates earlier then selected date.

Typ: `Boolean`

Values: `true` / `false`

Default: `true`

### allowFutureDates
Shows or hide dates after selected date.

Typ: `Boolean`

Values: `true` / `false`

Default: `true`

### minDate (new)
Minimum date.

Typ: `Date` or empty `String`

Default: `''` (empty String)

### maxDate (new)
Maximum date.

Typ: `Date` or empty `String`

Default: `''` (empty String)

### closeButtonLabel (new)
Label of close button.

Typ: `String`

Default: `'Close'`

## Author of migration to PhoneGap 3.0
Jens Krause // [WEBSECTOR.DE](http://www.websector.de)


