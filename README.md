# BluetoothRocks! Matrix

Draw on a LED pixel display using WebBluetooth

Forked from [https://github.com/BluetoothRocks/Matrix](https://github.com/BluetoothRocks/Matrix), so please go read his README as well.

Forked because I want to add more functions, which plays around with the Timebox. I have only added new Timebox features and methods.

## Changing to a static color (all pixels)

1. Connect to the Timebox
2. Open up the console and call this: `BluetoothMatrix.color(r, g, b)` (replace r, g, and b with 0-255 values)

## Switch between multiple colors rapidly

1. Connect to the Timebox
2. Open up the console

The function you're going to hit, is called `rapid()` which takes a couple of parameters:

```
interval
```

The wait in milliseconds between each color change.

I recommend 100 or above, because it makes the "animation" more fluid.

**Example:** `100`

```
count
```

The amount of times it should repeat the color changes.

Set this to anything you want, basically. The higher the number, the more fun you have (beware that you shouldn't show this to people with epilepsy over long periods of time)

**Example:** `5`

```
chunkCount
```

The amount of chunks that gets sent to the Timebox each color change.

The need for this is really simple: For some reason, the Timebox simply bugs out if it receives a lot a lot of bytes, as described in [my issue](https://github.com/BluetoothRocks/Matrix/issues/1). Therefore we need to send it in multiple chunks.

I recommend 2 chunks for the fastest update, but you can increase it to make fun patterns.

**Example:** `2`

```
colors
```

A 2D array of RGB color codes (0-255).

**Example:** `[[255, 0, 0], [0, 255, 0], [0, 0, 255]]` (change from red -> green -> blue)
