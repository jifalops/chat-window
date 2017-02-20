# \<chat-window\>

A simple and flexible chat window for listing messages.

## API and Demo
https://jifalops.github.io/chat-window

## Features
* Single or multi line input.
* Send-on-enter option, default is on for single-line and off for multi-line input.
* Slots for header, footer, and a custom input field.
* Styling hooks for full styling flexibility
* Automatically scrolls to bottom when a new message arrives (can be disabled).
* Auto-updating message timestamps using Moment.js that
  * Show every 5 minutes if less than one hour old,
  * Show every hour if less than a day old,
  * Show every four hours if a less than a week old,
  * Otherwise show once per day.
