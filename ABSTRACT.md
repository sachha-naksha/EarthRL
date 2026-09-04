# EarthRL — 250-word abstract

Cellular identity in disease and aging is maintained by epigenetic attractor states that are
stabilized by far more than transcription factors. Current dynamic gene-regulatory-network
methods — FIREFate, Dictys, CellOracle — are TF-centric, and cannot nominate the metabolic and
signaling actors (pathway kinases, metabolic enzymes, chromatin cofactors) that reshape chromatin
accessibility and, in consequence, transcriptional state. Temporal single-cell foundation models
lift this restriction: MaxToki, a decoder-only model over rank-value-encoded pseudotime
paragraphs, perturbs any gene and reports the induced pseudotime shift; it surfaced the metabolic
kinase PDK4 as the strongest rejuvenation signal in aged human skeletal muscle, corroborated in vivo
and in vitro. Such models simulate a perturbation's
consequences, but not which regulators to act on, in what order, to leave a diseased attractor.

EarthRL casts epigenetic attractor-state reversal as offline goal-conditioned reinforcement
learning on a MaxToki backbone, building on the reach-avoid decision transformer (RADT).
States are tokenized from snRNA and
snATAC profiles coupled by Fused Gromov-Wasserstein optimal transport into a per-gene chromatin
regulatory mass; actions are single and combinatorial in-silico perturbations of any gene,
rolled out by MaxToki as offline trajectories. A healthy attractor is specified
as the goal and pathological intermediates as regions to avoid, learned either reward-free via
hindsight relabeling or from a shaped reward
along a disease or aging axis; attractors are stable pseudotime windows identified by TF-target
link force and cell-state velocity. Applied to a human left-ventricle multiome atlas (DCM/HCM
cardiomyocytes and fibroblasts) and an aging skeletal-muscle atlas, EarthRL ranks non-TF
regulators whose perturbation sequences reverse epigenetic state.
