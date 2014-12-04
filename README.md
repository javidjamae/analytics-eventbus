analytics-eventbus
==================

Playing around with a Javascript AOP-style analytics eventbus

The idea is to decouple the triggering of an analytics event (destined for Mixpanel, KISSMetrics, etc) from the source of the data that provides attributes for the analytics event. 

For example, if I want to fire a "Button Clicked" event, I may have different modules that are used to provide the color, size, and text of the button. I might also have a module that provides information about the environment that I'm in (e.g. the referring url, browser, etc). The Button logic should just be able to fire a "Button Clicked" event onto an eventbus. The other modules can listen for those events and attach parameters to a map. Once all the listeners are done, then a main handler will fire the analytics event.
