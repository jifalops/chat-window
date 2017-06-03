[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/jifalops/chat-window)

# chat-window
The easiest way to have a chat.

## Installation

```
bower install --save chat-window
```

## Usage
* Pass it a list of messages and it will display them with live relative timestamps
using [from-now](https://www.webcomponents.org/element/jifalops/from-now).
* Listen for the `send` event to handle sending messages.

## Demo
Mouse-over messages to see the absolute timestamp.
<!--
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="chat-window.html">
    <style is="custom-style">
      chat-window {
        font-size: small;
        --chat-messages-height: 12em;
        --chat-messages-scroller: {
          border: 1px inset #eee;
        }
        --paper-input-container-input: {
          margin: 0 2px;
        };
        --chat-message-text: {
          background-color: #f0f0f0;
          padding: 6px 8px;
          margin: 4px 0;
          border-radius: 6px;
        };    
      }
    </style>          
    <script>
      var now = Date.now();
      var messages = [
        { author: 'you', text: 'dummy msg 1', created: now - (60*1000) },
        { author: 'me', text: 'dummy msg 2', created: now - (3*60*1000) },
        { author: 'you', text: 'dummy msg 3', created: now - (10*60*1000) },
        { author: 'you', text: 'dummy msg 4', created: now - (60*60*1000) },
        { author: 'me', text: 'dummy msg 5', created: now - (1.2*60*60*1000) },
        { author: 'me', text: 'dummy msg 6', created: now - (1.5*60*60*1000) },
        { author: 'you', text: 'dummy msg 7', created: now - (11.5*60*60*1000) },
        { author: 'me', text: 'dummy msg 8', created: now - (12*60*60*1000) },
        { author: 'you', text: 'dummy msg 9', created: now - (13*60*60*1000) },
        { author: 'me', text: 'dummy msg 10', created: now - (1.5*24*60*60*1000) },
        { author: 'you', text: 'dummy msg 11', created: now - (1.6*24*60*60*1000) },
        { author: 'me', text: 'dummy msg 12', created: now - (4*24*60*60*1000) },
        { author: 'me', text: 'dummy msg 13', created: now - (4.5*24*60*60*1000) },
        { author: 'you', text: 'dummy msg 14', created: now - (14*24*60*60*1000) },
        { author: 'me', text: 'dummy msg 15', created: now - (14.5*24*60*60*1000) },
      ].reverse();
    </script>
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->

```html
<chat-window
  id="chat"
  author="me"
  single-line>
</chat-window>
<script>
  var chat = document.getElementById('chat');  
  var author;
  chat.messages = messages;
  chat.addEventListener('send', function(e) {
    author = author == 'me' ? 'you' : 'me'; // For demo
    chat.push('messages',{
      author: author,
      text: e.detail,
      created: Date.now()
    });
    chat.inputText = '';
  });  
</script>
```

Full demo:
[webcomponents.org](https://www.webcomponents.org/element/jifalops/chat-window/demo/demo/index.html)
| [github](https://jifalops.github.io/chat-window/components/chat-window/demo/).

API: [webcomponents.org](https://www.webcomponents.org/element/jifalops/chat-window/chat-window)
| [github](https://jifalops.github.io/chat-window).

## Features
* Single or multi line input.
* Send-on-enter option, default is on for single-line and off for multi-line input.
* Slots for a header, footer, and a custom input field.
* Styling hooks for full styling flexibility
* Automatically scrolls to bottom when a new message arrives (can be disabled).
* Absolute timestamps can be shown via configurable date format.
* Auto-updating message timestamps using Moment.js that
  * Show every 5 minutes if less than one hour old,
  * Show every hour if less than a day old,
  * Show every four hours if a less than a week old,
  * Otherwise show once per day.

TODO
* Allow `author: msg` format instead of alignment based format.
* Use material guidelines for showing relative vs absolute timestamps as well as their format.

## Contributing

1. Fork it on Github.
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## License

[MIT](https://opensource.org/licenses/MIT)
