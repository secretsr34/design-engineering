# Pit Wall - Race Engineer's Decision Surface

An interactive Formula 1 pit wall built as a single self-contained HTML file. It presents race strategy the way an engineer actually consumes it during a stint: state at a glance, decisions foregrounded, everything legible under time pressure.

**Live:** [sabahrahman.com/f1/pitwall.html](https://www.sabahrahman.com/f1/pitwall.html)

## Why this exists

Race engineering is a decision-making discipline: imperfect information, hard time limits, and consequences measured in tenths of a second. That is the same shape as the enterprise decision-support problems I work on professionally. This project is the fun version of that problem - and a demonstration that a decision surface can be dense without being unreadable.

## Design decisions

- **Single file, zero dependencies.** The whole surface - markup, styles, interaction logic - ships as one HTML document. It loads instantly and runs anywhere, including offline.
- **Hierarchy under pressure.** Type scale and color are tuned for glanceability: the state you need most often is the largest thing on screen, and color carries meaning (not decoration) throughout.
- **Vanilla JavaScript.** All interactivity is hand-rolled DOM work. No framework overhead for a surface this size, and the code reads top to bottom.

## Run it

Open `index.html` directly, or serve the folder:

```
python3 -m http.server 8000
```
