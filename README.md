# Agentic AI for endoscopic surgery: demo videos

Gary Ying, AUTOLab. Real-to-sim twins built in RoboSimStudio by coding agents, path traced on one RTX 4090 (2026-10-26), plus the earlier CPU-only demo (2026-10-20).

## RoboSimStudio twins (2026-10-26)

**Interactive slider comparison (drag to reveal real vs twin, synced):** https://yinggarykairui.github.io/agentic-surgery-demo/rss/compare.html

**Combined reel, 2 min 52 s, 1080p:** [rss/rss_reel.mp4](rss/rss_reel.mp4)

Each twin was built from the reference clip alone by a coding agent (GPT-6 Astra via Codex, or Claude Opus 5.5 via Claude Code) using RoboSimStudio's real-to-sim workflow: scene, materials, camera, physics and the instrument routine. The three bench tasks load the da Vinci PSM (public dVRK model) as the robot and move objects only through jaw contact.

| Twin | Sim only (1080p30) | Real beside sim | Built by |
|---|---|---|---|
| da Vinci PSM, three pieces from ketchup into the foam frame, second arm assisting | [sim/auto7.mp4](rss/sim/auto7.mp4) | [side/auto7.mp4](rss/side/auto7.mp4) | GPT-6 Astra |
| da Vinci PSM, cheese cube off a meat slice (soft body) | [sim/hsm.mp4](rss/sim/hsm.mp4) | [side/hsm.mp4](rss/side/hsm.mp4) | GPT-6 Astra |
| da Vinci PSM, suture thread wrapped around the other shaft on the knot pad (rope) | [sim/knot.mp4](rss/sim/knot.mp4) | [side/knot.mp4](rss/side/knot.mp4) | GPT-6 Astra |
| Biportal endoscopic thoracic decompression, no robot | [sim/biportal_astra.mp4](rss/sim/biportal_astra.mp4) | [side/biportal_astra.mp4](rss/side/biportal_astra.mp4) | GPT-6 Astra |
| Biportal endoscopic thoracic decompression, no robot | [sim/biportal_opus.mp4](rss/sim/biportal_opus.mp4) | [side/biportal_opus.mp4](rss/side/biportal_opus.mp4) | Claude Opus 5.5 |

In the side-by-side clips the real footage is phase-aligned to the twin: each phase of the real clip (approach, grasp, carry, place) is time-scaled to the matching phase of the twin, so the beats line up. `rss/aligned_real/` holds those aligned real clips on their own. Review verdict: the cheese cube twin is correct and clean; the ketchup twin does the three transfers but not the snip step; the knot twin never ties a knot in either agent's build: Astra wraps with a disclosed grasp latch, Opus 5.5 (same prompt, independent build, toggle on the page) wraps two-handed without a latch but reaches only 0.8 turns and zero crossings after 41 attempts; the cheese twin's first take had swapped the PSM for a Cartesian carriage stand-in (caught in review; kept as a toggle on the comparison page) and the imported dVRK PSM model looks approximate; on the surgery case the Opus twin reads slightly better than the Astra twin. The surgery twins simulate deformable tissue and rigid bone with instrument contact; they do not cut, bleed or simulate fluid.

## Earlier CPU demo (2026-10-20)

[agentic_demo.mp4](agentic_demo.mp4), 170 s: frontier-model agents exploring public PitVis footage with look/zoom tools, and steering an instrument to a target in NVIDIA Newton and RoboSimStudio on CPU (flat shading, no path tracing).

All footage here is public PitVis data, public mock demonstrations, or simulation. The Biportal reference footage is shown only in the side-by-side panels for comparison.
