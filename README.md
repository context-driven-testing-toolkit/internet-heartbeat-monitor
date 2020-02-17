# internet-heartbeat-monitor

_Mac-only._

Periodically confirm that the computer can make a successful Web
request to the Internet.

Useful when running one's workstation on a network that has
hard-to-detect connectivity mishaps, such as when riding on a train.

## Synopsis

When you run `internet-heartbeat-monitor` the session looks like this,
as long as it looks like you are able to make a Web request successfully:

    $ sudo bin/internet-heartbeat-monitor
    Repeatedly pinging opendns.com
    ................

One dot will be printed each time the ability to make a Web request is
confirmed.

If it looks like you lost connectivity, you will get an `E` instead of
a dot in the console but more usefully you will get an OS-level alert
like this one:

<img src="https://i.imgur.com/3cOHWDj.png" alt="A Mac OS system message that reads: The intertube is clogged. Cannot ping opendns.com.">

## Notes for Context-Driven Testers who are building tools

This script contains a nice example of how you can make a bare-bones
test runner that prints "progess dots" just like a full xUnit test
runner would!

Also note the `osascript` command (Mac-only) which can be used to deliver
system alert messages with custom payloads --- great for any local
monitoring solution!
