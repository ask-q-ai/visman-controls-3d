# VisMan Controls 3D

Reusable 3D control components for VisMan interactive panels — button, slider, knob, and dial.

## Components

### `button_3d`

A 3D push-button with a raised cap sitting on a cylindrical base. Clicking toggles a pressed state that visually depresses the cap.

| Binding | Type | Description |
|---------|------|-------------|
| `pressed` | boolean | When true the cap is visually depressed |
| `buttonColor` | hex string | Color of the button cap |
| `baseColor` | hex string | Color of the cylindrical base |

### `slider_3d`

A linear horizontal slider with a rail, fill track, and sliding thumb handle.

| Binding | Type | Description |
|---------|------|-------------|
| `value` | 0.0–1.0 | Controls thumb position along the rail |
| `railColor` | hex string | Color of the rail body |
| `thumbColor` | hex string | Color of the thumb and fill track |

### `knob`

A rotary knob with a body and positional indicator notch. Rotation maps the 0–1 value to a ±2.2 radian sweep.

| Binding | Type | Description |
|---------|------|-------------|
| `value` | 0.0–1.0 | Controls knob rotation |
| `knobColor` | hex string | Color of the knob body |

### `dial`

A large indicator dial with a rotating needle and backing disc. The needle sweeps from -2.0 to +2.0 radians.

| Binding | Type | Description |
|---------|------|-------------|
| `value` | 0.0–1.0 | Controls needle angle |
| `dialColor` | hex string | Color of the backing disc |
| `needleColor` | hex string | Color of the needle |

## Demo Scenes

- **`scenes/control-panel-demo.yaml`** — A panel with one of each control type (button, slider, knob, dial) with canvas labels showing live state. Each control responds to click/drag via vm state mutations.
- **`scenes/synthesizer-panel-demo.yaml`** — A synth-style panel with 3 knobs (FILTER, VOLUME, REVERB) and 2 vertical sliders (ATTACK, RELEASE) with canvas labels.

## Importing via `from`

Reference a component from another VisMan scene using the `from` syntax pointing at `components/controls-3d.yaml`.

Example (local import):

```yaml
- id: my-knob
  from:
    path: path/to/visman-controls-3d/components/controls-3d.yaml
    name: knob
  bindings:
    value: "{{ @vm.filter.value }}"
    knobColor: "#7C3AED"
```

For remote import from GitHub:

```yaml
- id: my-knob
  from:
    githubUser: ask-q-ai
    repo: visman-controls-3d
    path: components/controls-3d.yaml
    name: knob
  bindings:
    value: "{{ @vm.filter.value }}"
    knobColor: "#7C3AED"
```
