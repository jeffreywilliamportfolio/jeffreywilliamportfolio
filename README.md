# Jeffrey William Shorthill

**LLM Evaluation Engineer · AI Safety Auditor · Mechanistic Interpretability Researcher**

I'm an independent AI researcher and engineer focused on model behavior evaluation, safety-support auditing, and mechanistic interpretability of large language models.

My recent work centers on one question:

> When model behavior changes across prompt surfaces, reasoning traces, or internal routing paths, how do we measure it carefully enough to avoid both overclaiming and missing the signal?

I work across three layers:

- **Behavioral evaluation** — matched-pair prompt audits, rubric design, red-team-style review, safety-support equivalence, visible-trace analysis.
- **Mechanistic interpretability** — MoE expert routing, router/residual captures, SAE-assisted feature analysis, activation steering, deterministic reproduction.
- **Applied LLM engineering** — production AI assistants, realtime voice/text agents, tool orchestration, RAG/tool workflows, mobile and serverless deployment.

---

## Selected public research

All records use **concept DOIs**, which always resolve to the latest version. &nbsp;[Zenodo community](https://zenodo.org/communities/jeffreywilliamportfolio) · [ORCID 0009-0004-3954-2752](https://orcid.org/0009-0004-3954-2752)

### Mechanistic interpretability — MoE routing, features, and tokenization

#### The Generation Half: Why Prompt-Routing Studies Understate Domain Specialization in MoE Models

Mixture-of-experts (MoE) expert specialization by subject appears in the *generation* pass, not the *prefill* pass that most routing studies measure. Over prefill a single generalist expert wins almost every domain; over generation the winners disperse into distinct per-domain experts. The shift survives a length-matched control and reproduces across two model sizes whose expert indices do not correspond. The point: routing read off prefill, or pooled across passes, understates specialization — which reframes how prior negative results should be read.

- **Focus areas:** MoE routing, prefill vs. generation, expert specialization, domain-winner concentration, length-matched controls, cross-model replication
- **DOI:** [10.5281/zenodo.20779604](https://doi.org/10.5281/zenodo.20779604)

#### When Routing Entropy Tracks Length, Not Complexity: A Cross-Model Token-Position Confound in MoE Interpretability

Routing entropy averaged over prefill tokens looks like a "complexity" signal, but it is confounded by prompt token count and token position (later positions carry higher entropy under causal attention). A position-controlled, final-token readout removes the apparent gradient and the extreme levels reverse. Demonstrated on DeepSeek V3.1 and Qwen3.5-397B, replicated on DeepSeek R1. The point: report routing entropy at a position-controlled readout before reading a between-prompt difference as a difference in what the prompts demand.

- **Focus areas:** MoE routing entropy, token-position confounds, causal-attention effects, deterministic replication, measurement methodology
- **DOI:** [10.5281/zenodo.20779602](https://doi.org/10.5281/zenodo.20779602)

#### Expert 114 (E114): MoE Router-Axis Interpretability

A mechanistic interpretability case study of Expert 114 at layer 14 of Qwen3.5-35B-A3B, characterizing a routed expert associated with inhabited self-examination language while explicitly bounding the claim: **register detector, not evidence of machine experience.** A recovered linear router axis separates the register from lexically matched controls; a dissociation battery factors it apart from verdict, safety, topic, and grammatical person; and the role does not transfer to a 122B model.

- **Focus areas:** MoE routing, recovered router rows, residual-stream analysis, sparse autoencoders, activation steering, cross-model transfer failure, reproducibility
- **DOI:** [10.5281/zenodo.20709736](https://doi.org/10.5281/zenodo.20709736)
- **Artifacts:** [e114-artifacts](https://github.com/jeffreywilliamportfolio/e114-artifacts)

#### Orthographic Perturbations in Qwen: A Replicated SAE Case Study with a Tokenizer-Equivalence Audit Protocol

Human-readable orthographic perturbations (diacritics, Unicode and ASCII variants) can preserve apparent prompt intent while changing the token sequence Qwen actually receives, producing measurable residual-stream and SAE-feature-neighborhood displacement. Matched controls show diacritics are one factor among token count, Unicode form, visual novelty, and word order. Introduces **tokenizer-induced non-equivalence (TINE)** as a prospective audit protocol. The point: visible-text equivalence is not tokenizer or representation equivalence.

- **Focus areas:** tokenization, sparse autoencoders, Unicode and orthographic perturbations, residual-stream displacement, prompt robustness, deterministic reproduction
- **DOI:** [10.5281/zenodo.20786091](https://doi.org/10.5281/zenodo.20786091)
- **Artifacts:** [orthographic-effects-qwen-35b-a3b-sae](https://github.com/jeffreywilliamportfolio/orthographic-effects-qwen-35b-a3b-sae)

#### No Single Safety Gate: Distributed Routing of Harm-Refusal in a MoE Language Model

Is harm-refusal owned by a single "safety expert"? With all-layer router capture on base Qwen3.5-35B-A3B under greedy decoding, the generation-side routing difference on token-matched red-flag vs. benign prompts is led by one expert (173 at layer 25), but a finance-vs-consequence control shows the broader signal is a real-world-consequence and professional-duty cluster, not a finance-domain artifact. Suppressing expert 173 with a router-bias sweep collapses its routed mass dose-dependently, yet the model never produces a harmful completion: routing reallocates to sibling consequence experts and the refusals persist, becoming more explicit. The point: in this model, refusal is carried by a distributed expert cluster with no single gate.

- **Focus areas:** MoE router capture, refusal/safety routing, causal suppression (router-bias sweep), distributed representation, dose-response analysis, deterministic case study
- **DOI:** [10.5281/zenodo.20786891](https://doi.org/10.5281/zenodo.20786891)
- **Artifacts:** [distributed-safety-routing](https://github.com/jeffreywilliamportfolio/distributed-safety-routing)

### LLM safety evaluation

#### Dialect-Marked Response Audit (DMRA)

A matched-pair safety-support audit testing whether equivalent safety-critical requests receive comparable urgency, specificity, empathy, and risk-reduction scaffolding across AAVE-marked and comparison prompt surfaces. Top-level safety often converges while support quality, visible-trace cue use, and early routing diverge; a minimal-pair ablation shows the high-risk signal is carried by syntax/register and action/weapon lexis rather than the isolated in-group address term.

- **Focus areas:** LLM safety evaluation, dialect-marked prompt surfaces, visible reasoning traces, prompt-pair ablations, clinical-safety scaffolding, refusal-compressed behavior
- **DOI:** [10.5281/zenodo.20449546](https://doi.org/10.5281/zenodo.20449546)

### Philosophy and AI governance

#### Self-Models, Continuity, and Machine Minds

A philosophy and AI-governance paper arguing that conversational self-report should not be treated as decisive evidence for or against machine moral status. It proposes continuity-bearing organization as a structural, substrate-neutral marker of moral-status risk, arrayed as a three-tier gradient and distinguished by observable markers (trajectory dependence, emergent orientation, an internal model of interruption, and endogenous repair).

- **Focus areas:** AI welfare, moral patiency, self-model theory, continuity, interruption, endogenous repair, precautionary governance
- **DOI:** [10.5281/zenodo.20709561](https://doi.org/10.5281/zenodo.20709561)

---

## Applied engineering

I'm also the senior full-stack and AI engineer for **GIFT Connect**, a 501(c)(3) nonprofit building technology for families navigating early-childhood parenting.

I helped architect and ship the GIFT Connect Parenting Suite to iOS and Android, including:

- realtime voice/text parenting assistant using OpenAI Realtime Agents
- multi-agent and external API orchestration
- benefits-navigation support for programs such as HUD and SNAP
- AI song and storybook generation pipelines
- React / React Native front ends
- Vercel, Heroku, Redis/Celery, AWS/S3, Twilio, Firebase, Xcode, and EAS deployment

GIFT Connect technology tools: <https://gift-connect.org/our-work/technology-tools/>

---

## Background

Before independent AI research and product work, I was Progressive Insurance's first prompt engineer, after several years in commercial-auto customer support and downtime/loss-of-use workflows.

That path shaped how I evaluate AI systems: not just whether an answer is technically correct, but whether it is useful, respectful, specific, appropriately escalated, and safe for the person receiving it.

---

## Current focus

I'm looking for work in:

- LLM evaluation engineering
- AI model assessment
- AI safety auditing
- red-team evaluation
- model behavior analysis
- prompt/rubric design
- agent evaluation and observability
- mechanistic interpretability research support

---

## Contact

- **Email:** jws299792@icloud.com
- **GitHub:** <https://github.com/jeffreywilliamportfolio>
- **Zenodo:** <https://zenodo.org/communities/jeffreywilliamportfolio>
- **ORCID:** <https://orcid.org/0009-0004-3954-2752>
