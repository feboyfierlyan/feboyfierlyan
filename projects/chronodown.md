# ChronoDown

A native macOS timekeeping app built around the pressure of running a live event.

[Full case study](https://feboyfierlyan.com/projects/chronodown) · [Back to my profile](../README.md)

![ChronoDown session list, time bank, and active countdown](../assets/chronodown.png)

## The problem

As the timekeeper at a university orientation event, I was juggling a timer, a rundown, and manual notes. I needed to see how one session affected the whole event's schedule.

## My contribution

I designed and built the macOS app, used the first version during the event, and iterated on the timer engine and workflow between event days. The published case study describes three days of development, with the completed version used on day four.

## Engineering decisions

- **Track a target end time.** Recomputing the remaining duration avoids accumulating error from repeated small decrements. Wall-clock changes and system lifecycle behavior still deserve explicit testing.
- **Make schedule changes visible.** The Time Bank records surplus from early finishes and deductions from overtime. A session can use banked time without losing sight of the event's overall pace.
- **Share timer state across views.** A common timer engine serves the dashboard, presenter display, and menu-bar view.
- **Design for the sound desk.** Keyboard controls, large countdowns, and an external-display mode support use during a live event.

## Scope and evidence

The published case study and screenshots document the product and its use at the event. This profile repository contains the showcase; source code and installation packages are not included.

**Explore:** [The event, the iterations, and the final product →](https://feboyfierlyan.com/projects/chronodown)
