There’s a new way of invoking the scroll functions in JavaScript where you can
specify how do you want the scroll to behave: smoothly, immediately, or auto (
whatever the user agent wants, I guess
).


`window.<span>scrollBy</span><span>(</span><span>{</span> top<span>:</span> <span>100</span><span>,</span> behavior<span>:</span> <span>'smooth'</span> <span>}</span><span>)</span><span>;</span>`

(note it’s *behavior*, not *behaviour*, argggh).

I read [this post][1] yesterday saying that it would be available (via 
[this tweet][2] from [@FirefoxNightly][3]) and immediately wanted to try it out
!

I made sure I had an updated copy of [Firefox Nightly][4]—you’ll need a
version from the 28th of October or later. Then I enabled the feature by going 
toabout:config and changing layout.css.scroll-behavior.enabled to true. No
restart required!

My [test][5] looks like this:

![native smooth scrolling][6]

([source code][7])

You can also use it in CSS code:


`<span>#myelement</span> <span>{</span><br>
  scroll-behavior<span>:</span> smooth<span>;</span><br><span>}</span>`

but my example doesn’t. Feel like building one yourself? :)

The reason why I’m so excited about this is that I’ve had to implement this
behaviour with plug-ins and what nots that tend to interfere with the rendering 
pipeline many, many times and it’s amazing that this is going to be native to 
the browser, as it should be smooth and posh. And also because other native 
platforms have it too and it makes the web look “not cool”. Well, not anymore!

The other cool aspect is that it degrades great—if the option is not
recognised by the engine you will just get… a normal abrupt behaviour, but it 
will still scroll.

I’m guessing that you can still use your not-so-performant plug-ins if you
really want your own scroll algorithm (maybe you want it to bounce in a 
particular way, etc). Just useinstant instead of smooth, and you should be good
to go!

*SCROLL SCROLL SCROLL SCROLL!*


[There’s a new way of invoking the scroll functions in JavaScript where you can specify how do you want the scroll to behave: smoothly, immediately, or auto (whatever the user...][8]


 [1]: https://groups.google.com/forum/#!msg/mozilla.dev.platform/tUfNZu3GpMQ/nIocFkImYSAJ
 [2]: https://twitter.com/FirefoxNightly/status/527016504798085120
 [3]: https://twitter.com/FirefoxNightly/
 [4]: http://nightly.mozilla.org/
 [5]: http://sole.github.io/test_cases/smooth_scrolling/
 [6]: img/smooth_scrolling.gif
 [7]: https://github.com/sole/test_cases/tree/gh-pages/smooth_scrolling

 [8]: http://soledadpenades.com/2014/10/29/native-smooth-scrolling-with-js/ " Native smooth scrolling with JS"