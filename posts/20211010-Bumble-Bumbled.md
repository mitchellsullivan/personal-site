The Bumble app for iOS doesn't have anti-aliasing turned on (as of 2021-10-05), which causes some really unsightly
effects to be rendered while swiping. This is likely an oversight, because, having built a card-swiping clone in React
Native, I've encountered an identical phenomenon and found no reasons (e.g., performance concerns) to leave
anti-aliasing turned off. It has been present for at least a couple of years, and I only recently submitted an issue to
Bumble support on September 23, including the method by which it could be fixed.

Where the top card meets the app's background color, its edges appear extremely jagged, and where the top card meets the
underlying card, there is artifacting in the form of white-pixel fill:

![IMG_6108-copy-2](https://mitchellsullivan.net/content/images/2021/10/IMG_6108-copy-2.png)

I saw that Tinder doesn't have this problem and that its cards have a feathered look when swiping:

![IMG_6112-1](https://mitchellsullivan.net/content/images/2021/10/IMG_6112-1.PNG)

This led me to search for the proper setting and fix my own app by adding the following key/value pair to
the `info.plist`.

```xml
<key>UIViewEdgeAntialiasing</key>
<true/>
```
