## Original Library

Please view **[Pizzicato](https://github.com/alemangui/pizzicato)** by @alemangui for documentation and further credits.

## A Web Audio Library

Pizzicato aims to simplify the way you create and manipulate sounds via the Web Audio API. Take a look at the [demo site here](https://alemangui.github.io/pizzicato/).

## Purpose of this Fork

This fork of Pizzicato adds several new features and effects while being more flexible on import to support existing audio engines (in my case, the _Scratch Audio Engine_).

This is utilized in my **[Tune Shark V3](https://sharkpools-extensions.vercel.app/?search=Tune-Shark-V3)** scratch extension.

## New Features

### Initialize Pizzicato with an existing AudioContext

```js
const myAudioContext = new AudioContext();

const PizzicatoInitializer = "...[Pizzicato Source Code]";

const Pizzicato = PizzicatoInitializer(myAudioContext);
```

### Audio Effect -- Bitcrusher

```js
const bitcrusher = new Pizzicato.Effects.Bitcrusher({
  bits: 70,
  frequency: 60000,
});

mySound.addEffect(bitcrusher);
```

### Audio Effect -- 3-Band-Equalizer

_From [this](https://github.com/alemangui/pizzicato/pull/164) Pull Request_

```js
const equalizer = new Pizzicato.Effects.ThreeBandEqualizer({
  cutoff_frequency_high: 18000,
  cutoff_frequency_low: 6000,
  low_band_gain: 1,
  mid_band_gain: 20,
  high_band_gain: 1,
});

mySound.addEffect(equalizer);
```

### Initialize Sounds using a Buffer

```js
const sound = new Pizzicato.Sound({
  source: "buffer",
  options: {
    buffer: myAudioBuffer,
    /* ... attack, release, etc. */
  },
});
```
