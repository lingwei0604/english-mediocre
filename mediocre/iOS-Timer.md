Timer
------
A timer that fires after a ceration time interval has elapsed, sending a specified messge to a target object.

Overview

Timers work in conjunction with run loops,Run loops maintain strong references to their timers, so you don't have to maintian your own strong reference to a timer after you have added it to a run loop.

A timer is not a real-time mechanism, if a timer's firing time occurs during a long run loop callout or while the run loop is in mode that isn't monitoring the timer,the timer doesn't fire until teh next time the run loop checks the timer,Therefore, the actual time at which a timer fires can be significantly later,See also Timer Tolerance.


Comparing Repeating and Nonrepeating Timers
You specify whether a timer is repeating or nonrepeating at creation time,A nonrepeating timer fires once and then invalidates itself automatically,thereby preventing the timer from firing again,By contrast, a repeating timer fires and then reschedules itself on same same run loop, A repeating timer always shceduels itself based on the scheduled firing time, as opposed to the actual firing time,For example, if a tiemr si scheduled to fire at a particular time and every 5 seconds after that,the scheduled firing time will always fall on original 5-second time intervals,even if the actual firing time gets delayed,if the firing time is delayed so far that it passes one or more of the scheduled firing times, the timer is fired only once for that time period; the timer is then rescheduled,after firing,for the next scheduled firing time in the future.


























