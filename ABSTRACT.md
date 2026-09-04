# EarthRL — 250-word abstract

Cellular identity in disease and aging is maintained by epigenetic attractor states that are
stabilized by far more than transcription factors. Dynamic gene-regulatory-network methods —
FIREFate, Dictys, CellOracle — can perturb only TFs, so the metabolic and signaling actors
(pathway kinases, metabolic enzymes) that reshape chromatin accessibility
and, in consequence, transcriptional state during heart disease and aging remain invisible to
in-silico screening. EarthRL asks the complementary question: perturb every non-TF gene and test
whether an epigenetic attractor state changes.

We separate the environment from the agent. The environment is MaxToki, a decoder-only LLM
pretrained on ~175 million rank-value-encoded single-cell trajectories, used solely to roll out
post-perturbation trajectories; its zero-shot PDK4 prediction in aged
skeletal muscle, validated in vivo and in vitro, shows it already captures metabolic
control of cell age. Attractor states are defined from a sequence-directed GRN — TF binding
inferred from motif-scanned snATAC peaks, coupled to snRNA cells by Fused Gromov-Wasserstein
optimal transport — so TF influence on chromatin is built into the state,
not the action space; attractors are stable pseudotime windows identified by
TF-target link force and cell-state velocity. The agent is an offline goal-conditioned RL
policy, after the reach-avoid decision transformer, taking a healthy attractor as goal
and pathological intermediates as avoid regions, trained either reward-free via hindsight
relabeling or with a shaped reward along a disease or aging axis. Applied to a human
left-ventricle multiome atlas (DCM/HCM cardiomyocytes and fibroblasts) and an aging
skeletal-muscle atlas, EarthRL prioritizes non-TF regulators whose perturbation sequences shift
epigenetic attractor states and cell fate.
