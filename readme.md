# TimerEvent

### The TimerEvent package encapsulates the native System.Timers.Timer and the EventManager library together into a event-driven user friendly object.
### You can specify a delay in millisecond and a number of repeat or make it a endless loop
### You can then add event listeners to it to get the needed callbacks 

## Sources
[https://github.com/kevincastejon/cs-timer-event](https://github.com/kevincastejon/cs-timer-event)

## Nuget package
[https://www.nuget.org/packages/TimerEvent/](https://www.nuget.org/packages/TimerEvent/)

## Documentation
[https://github.com/kevincastejon/cs-timer-event/tree/master/Documentation/html](https://github.com/kevincastejon/cs-event-manager/tree/master/Documentation/html)

## Basic usage:

```
// Instantiates a timer that will fire 3 times every 1000 ms
Timer t = new Timer(1000, 3);
// Adds listeners to it
t.AddEventListener<TimerEvent>(TimerEvent.Names.TIMER, TimerHandler);
t.AddEventListener<TimerEvent>(TimerEvent.Names.TIMER_COMPLETE, TimerHandler);
// Starts the timer
t.Start();

private void TimerHandler(TimerEvent e)
{
Timer t = e.Target as Timer;
Console.WriteLine(e.Name+" Repeat Count:"+t.RepeatCount+"/"+t.Repeat+"  Delay:"+t.Delay+"ms  Running:"+t.Running);
}

```