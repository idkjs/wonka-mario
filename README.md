# Wonka Mario

An example of a Mario game screen using [Phil Plückthun's](https://github.com/kitten) [Wonka](https://github.com/kitten/wonka) to manage user input and game state. Adapted from [Michael Ficarra's](https://github.com/michaelficarra) example [here](https://github.com/michaelficarra/purescript-demo-mario).

Play a live demo [here](https://bkonkle.github.io/wonka-mario/)!

## How does it work?

The main game loop is handled by a simple utility, [`foldp`](src/WonkaUtils.re#L8). In the [Main.re](src/Main.re) module, the `fromAnimationFrame` Wonka event source emits an event for each available frame. On each frame, the inputs (left, right, and jump) are sampled and fed through the `gameLogic` function with the current character state, which combines a number of operations to evolve the game state on each animation frame tick.

This gives us an efficient, type-safe way to manage state and events over time.
