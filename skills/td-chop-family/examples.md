# CHOP Examples

## LFO Driver
`lfoCHOP → mathCHOP (range) → nullCHOP`
Target expr: `op('null_lfo')[0]`

## Audio Reactive
`audiodevinCHOP → audiospectrumCHOP → mathCHOP → nullCHOP`

## Smooth Random
`noiseCHOP → filterCHOP → nullCHOP`

## Selective Downstream Cooking
`[source] → nullCHOP (cooktype=selective)` — suppresses downstream recooking when the selected checks detect no change; upstream nodes still cook when their inputs change, even without downstream demand

## 4D Noise Rotation (Installation-Safe Animation)
lfoCHOP with 2 channels (sin, cos), phase expr `me.chanIndex * 0.25`, very low freq (0.005 Hz).
Drives `tz`/`tw` on noise operators — cyclical, never overflows.

## Timer-Driven Sequence
`tableDAT (segment definitions) → timerCHOP (segdat=table, deferpars=true)`
Callbacks fire per segment. See `reference.md` for timerCHOP details.
