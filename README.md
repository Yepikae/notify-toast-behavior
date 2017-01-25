# NotifyToastBehavior

This [Polymer behavior](https://www.polymer-project.org/1.0/docs/devguide/behaviors) aims to simplify sending notification messages to a user of any Polymer web application.

### How to use

Retrieve the component with bower.

    bower install -s https://github.com/Yepikae/notify-toast-behavior.git

Import in your project.

    <link rel="import" href="./bower_components/notify-toast-behavior/notify-toast-behavior.html">

Create a [paper-toast](https://elements.polymer-project.org/elements/paper-toast) in your component. The id of the paper-toast MUST be `__notify_toast__` and the duration MUST be `0`.

    <paper-toast class="fit-bottom" id="__notify_toast__" duration=0> </paper-toast>

Add `NotifyToastBehavior` to the behaviors of your component

    behaviors: [NotifyToastBehavior],

Call `notifyToast` whenever you need to send a message to the user.

    this.notifyToast("This is a <i>success</i> log just for <b>you</b>.", {
      timeout: 10000,
      type: 'Success'
    });

### Functions

#### notifyToast(text, options)

Create and displays a notification in the `paper-toast#__notify_toast__`.

#### Parameters
 * text {String, Required} The main message to display. Can contain HTML content, such as links.
 * options {Object, Optional} The different options of the notification.
  + color {String, Optional} The main color of the notification. Must be in hex format. Default: <span style="color:#2196F3">#2196F3</span>.
  + timeout {Number, Optional} The timeout of the notification display, in milliseconds. Setting to `-1` means infinite display. Default: 3000.
  + type {String, Optional} The type of notification. 'Warning' 'Error' & 'Success' are predefined values that set the respective colors as main color: <span style="color:#FF9800">#FF9800</span>, <span style="color:#F44336">#F44336</span> & <span style="color:#8BC34A">#8BC34A</span>.
