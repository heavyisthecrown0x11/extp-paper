# Zenodo deposit — EXTp (prep 2026-09-19)

Publish the paper + artifact to Zenodo to get a citable DOI (for the CV /
Studielink, October 2026). Zenodo has no age restriction, so no parental
consent step is needed. You do the upload with your own
Zenodo account (sign in with the GitHub account or ORCID).

## What to upload (one record, self-contained)

Two files into a single Zenodo record:

| File | What |
|---|---|
| `SUBMISSION_READY_NDSS2028/extp.pdf` | the paper (20 pp, author Utku Erol) |
| `EXTp_artifact_bundle.zip` | reproducibility artifact: Isabelle/HOL development (115 facts, sorry-free), measurement summaries, boot protocols + images, figures, README |

Putting the artifact **inside the Zenodo record** makes the DOI self-contained
and public. The paper's `\artifacturl` currently points at the *private* GitHub
`extp-artifact` repo, which a public reader can't open — so either (a) rely on
the bundled artifact in the Zenodo record (simplest), or (b) make the GitHub
repo public and, if you want, add its URL as a related identifier.

## Metadata (paste into the Zenodo form)

- **Upload type**: Publication → **Preprint**
- **Title**: `EXTp: A Soundness Theorem for Counterfactual Exploit Replay on Formally Verified Microkernels`
- **Authors**: `Erol, Utku` — affiliation `Independent Researcher` (add your ORCID if you have one)
- **Description** (the abstract):

  Counterfactual exploit analysis -- determining which input parameter causally
  produced an observed outcome -- is pervasive in security research, but its
  current practice is epistemically unsound. Three gaps separate "different
  outcome" from "caused by the change": non-deterministic replay noise,
  replay-machinery side-effects, and causal pathways traversing microarchitectural
  state invisible to the analyst's surface. We present EXTp, a counterfactual
  replay framework on bare-metal seL4, and the Counterfactual Soundness Theorem
  (CST) -- the first formal soundness theorem for counterfactual causal
  attribution grounded in a verified microkernel substrate. EXTp realizes three
  observable properties: Capability Separation (Pearl modularity; Clopper-Pearson
  bound <= 0.37% at N=998), Strong Observational Equivalence (replay determinism:
  score_S = 1.0000 over N=34 cross-boot trials, Clopper-Pearson one-sided 95%
  upper bound on the per-run failure rate <= 10.4%), and Measurement Interference
  (calibrated timing threshold, realized false-positive rate 0.61%-2.78%). CST
  proves their composition grounds Pearl/Halpern-Pearl causal attribution within
  enumerated epistemic bounds; CST v1.0 establishes soundness under single-VCPU
  intervention scope and bare-metal microcode-stable configurations, with
  multi-VCPU and cross-configuration extensions charted as future work. A
  synthetic analog modeled on the CrackArmor confused-deputy pattern, executed on
  bare-metal Intel Alder Lake, exercises the pipeline end-to-end and shows the
  framework correctly detecting its own A1-modulo violations.

- **Keywords**: counterfactual analysis; causal inference; Pearl causality;
  Halpern-Pearl actual causation; seL4; formal verification; Isabelle/HOL;
  microkernel; hypervisor; exploit replay; SMEP/SMAP
- **License**: **CC BY 4.0** (recommended — open and citable). Note it is
  irreversible; see the double-blind caveat below before choosing.
- **Version**: `1.0`
- **Language**: English
- **Related identifiers** (optional): if you make the GitHub artifact public,
  add `https://github.com/heavyisthecrown0x11/extp-artifact` as
  *"is supplemented by"*.

## Steps

1. Sign in at https://zenodo.org (GitHub or ORCID login).
2. **New upload** → drag in `extp.pdf` and `EXTp_artifact_bundle.zip`.
3. Fill the metadata above. Upload type = Preprint.
4. (Optional) **Reserve DOI**: Zenodo can reserve the DOI before publishing, so
   you can print it in the paper. If you want the DOI on the PDF, reserve it,
   add it to the tex, rebuild the PDF (tectonic), re-upload, then publish.
   Otherwise just publish and cite the DOI as-is.
5. **Publish** → you get `10.5281/zenodo.XXXXXXX`. That is the CV-citable DOI.

## Decisions before you publish

- **Double-blind / venue.** A public DOI'd preprint carries your name and
  pre-discloses the work. If you still intend to submit to NDSS (or another
  double-blind venue), check that venue's preprint policy first — a public
  preprint can complicate anonymous review.
- **Artifact visibility.** Bundled artifact (this zip) is the no-fuss path. Only
  make the GitHub repo public if you specifically want the live repo linked.
- **License is permanent** on Zenodo once published — pick CC BY 4.0 deliberately.

## CV citation (after publishing)

```
Utku Erol. "EXTp: A Soundness Theorem for Counterfactual Exploit Replay on
Formally Verified Microkernels." Zenodo, 2026. https://doi.org/10.5281/zenodo.XXXXXXX
```
