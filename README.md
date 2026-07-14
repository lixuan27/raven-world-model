# RAVEN — Re-basing a Video Prior into Representation Space

A presentation site for the BranchState-J / RAVEN project.

**Thesis.** A web-scale video diffusion prior (Wan2.2-TI2V-5B) can be *re-based* out of its native
pixel-VAE latent space into a frozen-DINOv3 representation-autoencoder latent space — and it carries
its dynamics knowledge with it. The result is a single world model that both **generates** video and
**predicts** the semantic future without drifting.

The single new mechanism is **latent re-basing**: swap the input/output projections, keep the 30
pretrained transformer blocks (≥90% of parameters), add a frame-causal mask and per-frame noise
levels (diffusion forcing).

**Decisive result (measured).** Identical codec, data, seed and latent statistics; the only variable
is the transformer initialization. Transplanted vs. from-scratch: −22% converged flow loss,
+19.3% autoregressive rollout accuracy, +20.5% drift resistance at the final horizon.
Reported honestly: physical-plausibility (IntPhys2) sits at chance for both arms — the prior transfers
dynamics, not physics.

Open `index.html`, or view the deployed deck on GitHub Pages. Arrow keys navigate; several slides are
interactive (click the pipeline stages, the phases, the risk cards, and the re-basing toggle).
