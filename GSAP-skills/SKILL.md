# GSAP Animation Implementation

**Target:** `[page.tsx]`

## General

- Use GSAP with `@gsap/react` to implement page animations.
- Free to apply or adjust styles as needed to support animations.
- Preserve the existing visual design and layout unless changes are necessary for animation.
- Consider both desktop and mobile UI/UX.
- Properly scope GSAP animations and clean up `ScrollTrigger` instances on unmount.
- Respect `prefers-reduced-motion`; avoid scroll pinning or heavy animations when enabled.
- Avoid layout shifts, unexpected horizontal overflow, and scroll jumps.
