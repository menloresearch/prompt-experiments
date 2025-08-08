State of AI – Week of 1 – 7 August 2025  

Executive Summary  
1. OpenAI released GPT-5, a unified two-tier model (fast default + on-demand “thinking” mode) that cuts hallucinations 45 – 80 % versus GPT-4o and sets new SOTA on AIME-25, SWE-bench-Verified, MMMU, GPQA and HealthBench [OpenAI, 7 Aug 25].  
2. OpenAI also shipped its first genuinely open-weight LLMs since 2019: GPT-OSS-120B and GPT-OSS-20B (Apache-2.0, MoE architecture, single-GPU runnable) [TechCrunch, 5 Aug 25].  
3. Anthropic’s Claude Opus 4.1 landed (5 Aug), delivering small but real gains in coding (+2 pp SWE-bench), 64 k “extended thinking”, and better safety (98.8 % refusal on policy-violating prompts) at no price change [Medium, 6 Aug 25].  
4. Google rolled out Gemini 2.5 “Deep Think” to AI Ultra subscribers (1 Aug). It uses parallel exploration + RL to reach Bronze IMO-25 performance in minutes and SOTA on LiveCodeBench v6 [Google Blog, 1 Aug 25].  
5. xAI’s Grok 4 (July) still tops the new ARC-AGI2 reasoning benchmark (15.9 % vs GPT-5’s 9.9 %) and Musk confirmed Grok 5 training on a 3-M-H100-equivalent cluster for release by year-end [NextBigFuture, 7 Aug 25].  
6. Research trendlines this week emphasize scalable Mixture-of-Experts (MoBE compression, A3D-MoE 3-D chip-integration) and production-grade Retrieval-Augmented Generation (BEE-RAG, Graph-RAG) to curb hallucinations and cost [arXiv 2508.05257, 2508.04663; arXiv 2508.05100].  

Evidence-based Analysis  
GPT-5 architecture & performance  
• Two-level routing automatically invokes a larger “GPT-5 thinking” sub-model when complexity warrants, reducing average tokens while boosting accuracy (50-80 % fewer output tokens vs o3 at equal or better quality) [OpenAI].  
• Benchmarks: 94.6 % AIME-25, 74.9 % SWE-bench-Verified, 88 % Aider Polyglot coding; 46.2 % HealthBench-Hard; 84.2 % MMMU multimodal; 88.4 % GPQA with GPT-5 pro.  
• Safety: safe-completion training replaces pure refusal, lowering deceptive responses to 2.1 % (vs 4.8 % for o3) and cutting factual errors ~6× on LongFact/FActScore [OpenAI].  

Open-weight GPT-OSS models  
• 120 B-parameter MoE activates 5.1 B experts per token, fits on a single H100; 20 B fits on a laptop. Apache 2.0 license enables commercial deployment [TechCrunch].  
• Codeforces w/ tools: 2622 (120B) beats DeepSeek-R1; HLE: 19 %. Hallucinate more than o-series (49–53 % PersonQA) but expand open-source ecosystem.  

Gemini 2.5 Deep Think  
• Parallel “idea lattices” + extended inference time increase reasoning depth; Bronze IMO-25 in house eval; SOTA on LiveCodeBench V6 without tools; stronger refusals but higher benign refusal rate [Google Blog].  
• Available as toggle in Gemini app; API preview upcoming.  

Claude Opus 4.1  
• Incremental update: +2 pp SWE-bench, +4.1 pp Terminal-Bench, +1.3 pp GPQA Diamond, context 200 k/32 k; up to 64 k “thinking” tokens.  
• Safety compliance up to ASL-3: 98.76 % harmful-refusal, 0.08 % benign over-refusal.  
• Same pricing ($15 / $75 per M tokens), batch and cache discounts up to 90 % [Medium].  

xAI Grok 4 status  
• Maintains lead on ARC-AGI2; Musk signals Grok 5 before 2026 with 3 M H100 “equivalent” training budget— a compute jump aligning with 10× parameter increase trajectory.  

Research & Architecture Highlights  
• MoBE (arXiv 2508.05257) compresses MoE LLMs 4 × with <1 % loss, easing on-device inference.  
• A3D-MoE (semiengineering 5 Aug) shows 3-D heterogeneous chiplets to remove memory wall for sparse-expert routing.  
• BEE-RAG (arXiv 2508.05100) dynamically balances entropy between retrieved context and model prior, reducing hallucinations 28  %.  
• Graph-RAG & production-RAG guides (Medium, TowardsAI) stress knowledge-graph retrieval and pipeline hardening as enterprises move PoCs to prod.  

Actionable Recommendations  
For Enterprises  
1. Begin GPT-5 piloting in knowledge-work flows; early tests show ~20 % time savings and 45 % error reduction. Budget for higher usage tiers or deploy GPT-5 mini fallback to control cost.  
2. Use Claude Opus 4.1 for large-scale refactoring and agentic tasks that need extended context (>32 k). Leverage batch API to halve tokens-cost.  
3. Adopt Gemini Deep Think selectively for R&D teams tackling math, algorithm design or multi-step creative ideation. Monitor higher benign refusal impact on user satisfaction.  
4. Evaluate GPT-OSS-120B/20B as on-prem or edge models where data-sovereignty or cost are critical. Expect higher hallucination; pair with RAG pipelines.  
5. Track Grok 4/5 if Twitter/X data or real-time trend analysis is core to business; benchmark when Grok 5 arrives.  

For Developers & MLOps  
1. Test MoBE or similar compression on internal MoE experiments to slash inference VRAM before year-end hardware refresh.  
2. Add BEE-RAG-style entropy controls or Graph-RAG into retrieval layer to cut hallucinations without scaling up model size.  
3. Use GPT-5’s safer completions as template to retrain smaller in-house models, reducing over-refusal while staying policy-compliant.  

For Policymakers & Risk Leads  
1. Review GPT-5’s “High capability” designation in bio/chem domains; consider mirroring multi-layer safeguards (always-on classifiers, red-team hours) in forthcoming frontier-model governance rules.  
2. Monitor open-weight proliferation (GPT-OSS) and ensure export-control frameworks keep pace with models runnable on commodity GPUs.  

Sources  
• OpenAI – “Introducing GPT-5” (7 Aug 25) https://openai.com/index/introducing-gpt-5/  
• TechCrunch – “OpenAI launches two ‘open’ AI reasoning models” (5 Aug 25) https://techcrunch.com/2025/08/05/openai-launches-two-open-ai-reasoning-models/  
• Google Blog – “Gemini 2.5: Deep Think is now rolling out” (1 Aug 25) https://blog.google/products/gemini/gemini-2-5-deep-think/  
• Medium – Cogni Down Under “Claude Opus 4.1 Definitive Guide” (6 Aug 25) https://medium.com/@cognidownunder/anthropic-claude-opus-4-1-the-definitive-guide-bf1c6f0de736  
• NextBigFuture – “XAI Grok 4 Still Ahead on ARC-AGI2” (7 Aug 25) https://www.nextbigfuture.com/2025/08/xai-grok-4-still-ahead-on-arc-agi2-benchmark-versus-gpt5.html  
• arXiv 2508.05257 – “MoBE: Mixture-of-Basis-Experts for Compressing MoE-based LLMs”  
• arXiv 2508.05100 – “BEE-RAG: Balanced Entropy Engineering for Retrieval-Augmented Generation”  
• Semiconductor Engineering – “Technical Paper Roundup 5 Aug 25” (A3D-MoE)