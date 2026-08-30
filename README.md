# Brachistochrone Lab

An interactive, dependency-free browser experiment that races three gravity-driven paths between the same two points:

- the time-minimizing **brachistochrone** (a cycloid);
- a **straight ramp**; and
- an adjustable **custom curve**.

[Open the live demo](https://techrote.github.io/brachistochrone-lab.html)

## What you can explore

- Change the horizontal span and vertical drop.
- Compare gravity values, from low-gravity environments to stronger fields.
- Add an initial launch speed.
- Adjust the custom curve's bow.
- Slow down or speed up playback.
- Compare travel time and track length for every path.
- Repeat races automatically.

The simulation makes the brachistochrone's central lesson visible: the shortest route is not always the quickest. Its steep initial descent converts potential energy into speed earlier, allowing it to beat the straight ramp even though the track may be longer.

## Run locally

Download or clone the repository, then open `brachistochrone-lab.html` in a modern browser.

```sh
git clone https://github.com/techrote/Brachistochrone-Lab.git
cd Brachistochrone-Lab
```

No build step, local server, package manager, internet connection, or external assets are required.

## Controls

| Control | Effect |
| --- | --- |
| **Run race / Pause race** | Starts or pauses the simulation |
| **Restart** | Returns all racers to the start |
| **Restore defaults** | Resets every experiment setting |
| **Repeat race automatically** | Starts another race after the current one finishes |
| **Space** | Plays or pauses the race |
| **R** | Restarts the race |

Changing a geometry or physics setting resets the race so all three paths can be compared from the same starting conditions.

## Model

The animation treats each racer as an ideal point mass. Speed follows conservation of mechanical energy:

```text
v(y) = sqrt(v₀² + 2gy)
```

The brachistochrone is generated from the cycloid parameterization:

```text
x = a(θ − sin θ)
y = a(1 − cos θ)
```

Travel times are approximated numerically along finely sampled track segments. The model intentionally omits drag, rolling resistance, rotational inertia, and other losses, so it is an educational idealization rather than a vehicle-dynamics simulator.

## Project structure

```text
.
├── brachistochrone-lab.html  # Complete simulation: markup, styles, and JavaScript
├── README.md
└── LICENSE
```

## License

Licensed under the [GNU Affero General Public License v3.0](LICENSE).
