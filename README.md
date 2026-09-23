# wait or go.

A mid-fidelity prototype for deciding how long to wait for a bus. Built for DECO2500/7250
(Human-Computer Interaction) at the University of Queensland.

**[Open the prototype](https://wsnxxxs.github.io/wait-or-go/)**

Most transit apps compete on making the arrival estimate more accurate. This one accepts that the
estimate will stay wrong and works on the decision instead. It shows how far the estimate has
moved, works out the last minute your backup still gets you there, and then goes quiet.

## Everything in it is simulated

The stop (High St / Toowong Village, stop 23), the route (470) and the roughly 20-minute weekday
headway are real. Every arrival time, vehicle position, cancellation and train connection is
invented for the demo. This is a design argument, not a transport service.

## It stores nothing

No network requests, no location permission, no cookies, no localStorage, no analytics. Close the
tab and nothing survives. That is deliberate: the design argues that a good outcome is the rider
closing the app, and a demo that tracked people would undercut it.

## Scenes

A walkthrough panel beside the phone steps through six moments of one afternoon, says what each one
shows and what to try. Or link straight to one.

| Link | What it shows |
|---|---|
| [`?scene=settled`](https://wsnxxxs.github.io/wait-or-go/?scene=settled) | The estimate has held steady |
| [`?scene=drifting`](https://wsnxxxs.github.io/wait-or-go/?scene=drifting) | Three revisions in nine minutes |
| [`?scene=stale`](https://wsnxxxs.github.io/wait-or-go/?scene=stale) | The feed goes quiet, and says so |
| [`?scene=crossed`](https://wsnxxxs.github.io/wait-or-go/?scene=crossed) | The bus is three minutes away and still the wrong choice |
| [`?scene=cancelled`](https://wsnxxxs.github.io/wait-or-go/?scene=cancelled) | A stated fact, kept distinct from missing data |
| [`?scene=recovered`](https://wsnxxxs.github.io/wait-or-go/?scene=recovered) | Updates return and the bus beats the line |

`goal` takes minutes since midnight (`915` = 3:15 pm) or `none`. `armed=1`, `quiet=1` and
`waiting=1` set state directly. `guide=0` hides the walkthrough panel.

## Source

`index.html` is the whole thing: one self-contained file, no build step, no dependencies.
