# iwer

## 2.3.0

### Minor Changes

- Add agent-ready programmatic control APIs for extension-hosted and local-tool
  automation: runtime method metadata, `connectTransport`, world/object queries,
  hand pose updates, and more reliable session status reporting.
- Expand action recording and playback with programmatic accessors, JSON export,
  seeking, frame stepping, duration/current-time reporting, looping, playback
  rate control, and optional select/squeeze event dispatch.
- Export Meta controller configs and config types, add a generic
  trigger/squeeze/thumbstick controller config, and wire haptics through the
  emulated gamepad surface.
- Add runtime lifecycle and compatibility controls including
  `XRDevice.uninstallRuntime()`, native WebXR detection/forced install,
  WebGL1 `makeXRCompatible`, and configurable user-agent override support.

### Patch Changes

- Fix session lifecycle behavior so `XRSession.end()` is idempotent and post-end
  frame/render-state behavior is closer to the WebXR spec.
- Preserve legitimate zero-valued render-state fields, including
  `inlineVerticalFieldOfView`.
- Tighten WebXR spec fidelity for transforms, depth information, hit testing,
  and event-handler getter round trips.
- Improve remote-control robustness with request timeouts, atomic transform
  validation, non-mutating dispatch params, accurate gamepad update counts, and
  complete force-release cleanup for buttons, thumbsticks, and hand pinch.
- Fix action-player edge cases for single-frame recordings, end-of-recording
  reads, and invalid gamepad data.
- Reduce per-frame allocations across spaces, frames, sessions, views, gamepads,
  action replay, and depth buffers.
- Improve package hygiene with pnpm monorepo support, clean builds, and
  `sideEffects: false` metadata.
