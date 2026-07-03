# ThumbStick 🕹️

**Your thumb is the joystick.** A prototype exploring rate-control scrolling on iOS.

Touch anywhere, hold for a beat, then tilt your thumb — the page scrolls at whatever pace you set. Push further to go faster. Lift to stop. Normal flick scrolling still works.

**[▶ Watch the demo](./docs/Demo.mp4)**

## How it works

No phone senses finger tilt, but when you roll your thumb, iOS can see the contact point drift and the contact patch grow (`UITouch.majorRadius`). ThumbStick turns those two signals into a joystick:

- **Dwell 0.3s** to engage (flicks never wait — they start moving, the stick starts still)
- **Tilt** past a 10pt dead zone → velocity, with a capped throw like a real joystick
- **Hold a steady pace** → cruise lock: relax your thumb, the page keeps gliding
- **Lift** → soft brake, instant-feeling stop

## Run it

1. Open `ThumbStick.xcodeproj` in Xcode
2. Set your team under Signing & Capabilities
3. Run on a **real iPhone** — the simulator fakes contact radius

## Make it yours

All the feel lives in the `Tuning` enum at the top of `ContentView.swift` — gain, curve, dead zone, cruise lock, haptics. Change a number, run, feel, repeat.

To see the gesture while tuning, uncomment `JoystickOverlay` and `HUD` in `ContentView`.

## License

MIT. Take it, remix it, ship it. If you build something with it, I'd love to see.
