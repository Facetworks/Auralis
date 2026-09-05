# Auralis

**A living field of light, rendered in real time on your GPU — right in the browser.** WebGPU when your browser has it, a WebGL2 fallback when it doesn't, so it runs almost anywhere. No server, no dependencies, no build step.

**→ Live: https://auralis.signalizeai.org**

## What it is

An interactive aurora: domain-warped fractal noise (FBM) mapped through cosine palettes, animated every frame on the GPU. Move your cursor and the current bends and energizes around it.

- **WebGPU-first**, with a graceful **WebGL2 fallback** (the same shader, ported) — the label shows which one you got
- Runs entirely on the *visitor's* GPU, so it costs nothing to host at any scale
- Four palettes (Aurora, Ember, Ice, Bloom), Calm / Storm turbulence, pause, and a live fps readout
- One self-contained HTML file: no dependencies, no build

## How it works

- A full-screen triangle drives a fragment shader.
- The shader layers value-noise **FBM**, warps the domain twice for the flowing look, and colors the result with an Inigo Quilez **cosine palette**.
- The cursor feeds a uniform that adds local energy and bends the flow.
- The **WGSL** (WebGPU) and **GLSL** (WebGL2) shaders are kept in sync so both paths look identical.

## Run locally

Open `public/index.html` in a browser, or serve the folder:

```bash
npx serve public
```

## License

MIT
