---
layout: default
title: "Horizon Summary: 2026-06-15 (EN)"
date: 2026-06-15
lang: en
---

> From 27 items, 13 important content pieces were selected

---

1. [Pyodide 314.0: Publish WASM wheels to PyPI directly](#item-1) ⭐️ 9.0/10
2. [Rio's 'Homegrown' LLM Revealed as Weighted Merge of Two Existing Models](#item-2) ⭐️ 8.0/10
3. [Formal Methods and AI Code Verification](#item-3) ⭐️ 8.0/10
4. [AI won't replace software engineers, essay argues](#item-4) ⭐️ 8.0/10
5. [The Verifier Tax: Safety-Success Tradeoffs in LLM Agents](#item-5) ⭐️ 8.0/10
6. [Adobe RMSDK Blamed for Kobo ePub Issues](#item-6) ⭐️ 7.0/10
7. [Kage: Turn any website into a single binary for offline viewing](#item-7) ⭐️ 7.0/10
8. [Trace: Offline Mac meeting transcripts with mid-call flagging](#item-8) ⭐️ 7.0/10
9. [Caddy Compatibility for zeroserve: 3x Throughput, 70% Lower Latency, But No ACME](#item-9) ⭐️ 7.0/10
10. [Mapping SQLite result columns to source table.column with AI](#item-10) ⭐️ 7.0/10
11. [Open-source knowledge graph pipeline boosts LLM multi-hop reasoning](#item-11) ⭐️ 7.0/10
12. [PaddleOCR v3-v6 Implemented in C++ with ncnn for Lightweight Deployment](#item-12) ⭐️ 7.0/10
13. [Ask HN: Share Your Current Projects (June 2026)](#item-13) ⭐️ 6.0/10

---

<a id="item-1"></a>
## [Pyodide 314.0: Publish WASM wheels to PyPI directly](https://simonwillison.net/2026/Jun/13/publishing-wasm-wheels/#atom-everything) ⭐️ 9.0/10

Pyodide 314.0 allows Python package maintainers to publish WebAssembly (WASM) wheels directly to PyPI, enabling browser-based Python packages to be installed via micropip without requiring Pyodide maintainers to host them. This reduces the maintenance burden on Pyodide core developers and removes a major bottleneck for the Python-in-the-browser ecosystem, as any package maintainer can now distribute WASM wheels just like native wheels. The feature is enabled by PEP 783, which defines the PyEmscripten platform tag. Support was added to PyPI via warehouse PR #19804, and tools like cibuildwheel can now build WASM wheels automatically.

rss · Simon Willison · Jun 13, 23:55

**Background**: Pyodide is a port of CPython to WebAssembly/Emscripten, allowing Python to run in the browser. Previously, Pyodide maintainers had to build and host over 300 packages manually. PEP 783 standardizes an Emscripten platform tag for Python wheels, enabling direct PyPI distribution of WASM-compiled packages.

<details><summary>References</summary>
<ul>
<li><a href="https://pyodide.org/en/stable/project/about.html">What is Pyodide ? — Version 0.29.4</a></li>
<li><a href="https://discuss.python.org/t/pep-783-emscripten-packaging/86862">PEP 783: Emscripten Packaging - Python Discussions</a></li>
<li><a href="https://pydantic.dev/articles/emscripten-wheels-pydantic">Building Emscripten wheels for Pyodide and PyPI (PEP 783)</a></li>

</ul>
</details>

**Tags**: `#Pyodide`, `#WASM`, `#PyPI`, `#Python`, `#WebAssembly`

---

<a id="item-2"></a>
## [Rio's 'Homegrown' LLM Revealed as Weighted Merge of Two Existing Models](https://github.com/nex-agi/Nex-N2/issues/4) ⭐️ 8.0/10

A community investigation found that Rio-3.5-Open-397B, released by the municipality of Rio de Janeiro, is a weighted average of approximately 60% Nex-N2 Pro and 40% Qwen3.5-397B-A17B, not a novel fine-tune as claimed. This incident highlights serious transparency issues in open-source LLM releases, where model merging is misrepresented as original training, eroding trust in the community and raising ethical concerns about proper attribution. The analysis showed that every weight tensor in the Rio model matches a 0.6/0.4 blend of Nex and Qwen across all 60 layers, with thousands of standard deviations consistency, ruling out a regular fine-tune.

hackernews · unrvl22 · Jun 14, 15:37 · [Discussion](https://news.ycombinator.com/item?id=48528371)

**Background**: Model merging combines the parameters of multiple neural networks into a single model without additional training, offering a computationally efficient way to improve performance. Weighted average merging is a simple method where each weight tensor is a linear combination of corresponding tensors from source models. This technique is distinct from fine-tuning, which updates weights through further training on new data.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2603.09938">[2603.09938] Model Merging in the Era of Large Language Models: Methods, Applications, and Future Directions</a></li>
<li><a href="https://arxiv.org/abs/2408.07666">[2408.07666] Model Merging in LLMs, MLLMs, and Beyond: Methods, Theories, Applications and Opportunities</a></li>

</ul>
</details>

**Discussion**: Commenters expressed concern over transparency and attribution, with one saying 'someone is profiting off of their work without proper attribution.' Another commenter speculated that the official model might have intended distillation that wasn't uploaded. One asked for explanation of model merging techniques.

**Tags**: `#LLM`, `#model merging`, `#transparency`, `#open-source`, `#AI ethics`

---

<a id="item-3"></a>
## [Formal Methods and AI Code Verification](https://blog.janestreet.com/formal-methods-at-jane-street-index/?from_theconsensus=1) ⭐️ 8.0/10

Jane Street explores how formal methods and expressive type systems can address verification challenges, especially for AI-generated code, highlighting a shift toward verification as a human value. As AI generates more code, formal methods become crucial for ensuring correctness, potentially reshaping the role of programmers from writing code to verifying it. The post discusses using highly expressive types in Scala 3 for compile-time proofs, preventing agentic test sprawl and low-quality modes like 'noun accretion'.

hackernews · eatonphil · Jun 14, 12:35 · [Discussion](https://news.ycombinator.com/item?id=48526633)

**Background**: Formal methods are mathematically rigorous techniques for specifying and verifying software. Type systems are a syntactic method for automatically checking program behavior. The combination can catch errors early and complement testing.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Formal_methods">Formal methods - Wikipedia</a></li>
<li><a href="https://web.mit.edu/16.35/www/lecturenotes/FormalMethods.pdf">PDF Introducing Formal Methods - MIT</a></li>
<li><a href="https://softwareengineering.stackexchange.com/questions/333643/what-is-a-type-system">programming languages - What is a type system?</a></li>

</ul>
</details>

**Discussion**: Comments reflect a mix of historical experience with formal methods (e.g., Boyer-Moore prover) and current skepticism about formal specs being like writing tests differently. Some see a shift toward verification as a human role in the AI era.

**Tags**: `#formal methods`, `#programming languages`, `#type systems`, `#verification`, `#AI`

---

<a id="item-4"></a>
## [AI won't replace software engineers, essay argues](https://simonwillison.net/2026/Jun/14/why-ai-hasnt-replaced-software-engineers/#atom-everything) ⭐️ 8.0/10

Arvind Narayanan and Sayash Kapoor published an essay arguing that AI is unlikely to cause mass layoffs in software engineering, citing data from New York's WARN Act that showed not a single company attributed layoffs to AI in its first year. This essay challenges the prevailing narrative that AI will automate software engineering jobs, offering evidence-based reassurance to developers and influencing the broader debate on AI's impact on white-collar professions. The essay identifies three real bottlenecks in software engineering that resist automation: deciding what to build, verifying and being accountable for deliverables, and deep human understanding of the codebase, business, and environment.

rss · Simon Willison · Jun 14, 23:54

**Background**: Recent advances in AI, particularly large language models, have sparked fears that software engineers might be replaced. However, this essay argues that writing code is only a small part of the job, and the core value comes from human judgment and contextual understanding.

**Tags**: `#AI`, `#software engineering`, `#job displacement`, `#technology impact`, `#labor economics`

---

<a id="item-5"></a>
## [The Verifier Tax: Safety-Success Tradeoffs in LLM Agents](https://www.reddit.com/r/MachineLearning/comments/1u58mkq/the_verifier_tax_horizondependent_safetysuccess/) ⭐️ 8.0/10

A new paper introduces the Verifier Tax, a horizon-dependent tradeoff between safety and task success in tool-using LLM agents, and proposes a two-tier verification architecture. Evaluations on Tau-bench show that verification reduces unsafe successes but also lowers task completion as task horizon increases. This finding is crucial for deploying safe LLM agents, as it quantifies the cost of safety enforcement and guides practitioners on when verification becomes counterproductive. It also raises important questions about how to report unsafe successes in agent evaluations. The two-tier architecture first applies deterministic policy and tool checks, then an LLM-based verifier for contextual safety cases. The Verifier Tax effect becomes significant at interaction horizons of 15-30 turns, where safety enforcement dominates and reduces success rates.

reddit · r/MachineLearning · /u/AccomplishedLeg1508 · Jun 14, 02:09

**Background**: Tool-using LLM agents perform tasks by calling external APIs and tools, but may violate safety policies. Runtime verification intercepts and blocks unsafe actions before execution. The Verifier Tax captures the persistent reduction in task success rate caused by such verification, especially over longer task horizons.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2603.19328">[2603.19328] The Verifier Tax: Horizon Dependent Safety Success ...</a></li>
<li><a href="https://dl.acm.org/doi/full/10.1145/3786335.3813160">The Verifier Tax: Horizon Dependent Safety--Success Tradeoffs in Tool ...</a></li>
<li><a href="https://www.caisconf.org/program/2026/papers/the-verifier-tax-horizon-dependent-safety-success-tradeoffs-in-tool-using-llm-ag/">The Verifier Tax: Horizon Dependent Safety-Success Tradeoffs in Tool ...</a></li>

</ul>
</details>

**Tags**: `#LLM agents`, `#safety verification`, `#tool use`, `#ACM CAIS`

---

<a id="item-6"></a>
## [Adobe RMSDK Blamed for Kobo ePub Issues](https://andreklein.net/your-epub-is-fine-kobo-disagrees-blame-adobe/) ⭐️ 7.0/10

A blog post argues that ePubs failing on Kobo devices are not inherently broken but suffer from bugs in Adobe's RMSDK, the rendering engine used by Kobo for standard ePubs. The discussion underscores the ongoing compatibility issues in the e-book ecosystem, where reliance on Adobe's proprietary RMSDK creates a bottleneck for authors and readers. Kobo devices support a newer rendering engine when files are named .kepub.epub, and tools like kepubify can convert ePubs to this format. Additionally, Adobe has transferred maintenance of RMSDK to Wipro as of July 2025.

hackernews · sohkamyung · Jun 14, 22:54 · [Discussion](https://news.ycombinator.com/item?id=48533848)

**Background**: The Adobe Reader Mobile SDK (RMSDK) is a software development kit used by many e-book readers, including Kobo, to render ePub files. It supports Adobe Digital Editions DRM and has been criticized for bugs and lack of updates. The ePub format is an open standard maintained by the W3C, but its rendering depends on the implementation.

<details><summary>References</summary>
<ul>
<li><a href="https://www.adobe.com/uk/solutions/ebook/rmsdk.html">Solutions - Ebook - Content server - Adobe</a></li>
<li><a href="https://kb.datalogics.com/article/adobe-ebook-platform-transition-and-adobe-id-sign-in-changes-acs-and-rmsdk-in-2026-and-beyond-177.html">Adobe eBook Platform Transition and Adobe ID Sign-In Changes -- ACS and ...</a></li>

</ul>
</details>

**Discussion**: Commenters express frustration with Adobe's lack of support and QA, with one noting that RMSDK is inaccessible to independent developers. Others suggest workarounds like using .kepub.epub or accepting the need to target older devices.

**Tags**: `#ePub`, `#Kobo`, `#Adobe`, `#e-books`, `#format compatibility`

---

<a id="item-7"></a>
## [Kage: Turn any website into a single binary for offline viewing](https://github.com/tamnd/kage) ⭐️ 7.0/10

Kage, a new command-line tool, captures complete websites into a single executable binary using headless Chrome, allowing offline viewing without any dependencies. This simplifies offline access to web content, particularly useful for areas without internet or for archiving, and stands out by bundling a server directly into the output binary. Kage supports two output formats: a single HTML file and a standalone binary that includes the tool itself; the binary format requires running a server process to view the site, which some users noted as a limitation.

hackernews · tamnd · Jun 14, 17:25 · [Discussion](https://news.ycombinator.com/item?id=48529990)

**Background**: Web archiving tools preserve online content for offline use, often saving pages as HTML or specialized formats like WARC. Kage's approach is unique because it creates a self-contained executable that includes both the website data and a simple HTTP server, enabling offline viewing on any machine without pre-installed tools.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/tamnd/kage">GitHub - tamnd/kage: Shadow any website for offline viewing , with the...</a></li>
<li><a href="https://cybermediacreations.com/show-hn-kage-shadow-any-website-to-a-single-binary-for-offline-viewing/">Show HN: Kage – Shadow any website to a single binary for offline ...</a></li>
<li><a href="https://guides.lib.umich.edu/c.php?g=1466381&p=11014669">Web Archiving Tools - Archiving Websites and Data - Research Guides at University of Michigan Library</a></li>

</ul>
</details>

**Discussion**: The Hacker News community showed interest, discussing use cases like offline company wikis. Some compared Kage to SingleFile, which packs everything into a single HTML file, while others desired a version that doesn't require a separate server process.

**Tags**: `#offline`, `#web archiving`, `#static site`, `#tool`, `#hackernews`

---

<a id="item-8"></a>
## [Trace: Offline Mac meeting transcripts with mid-call flagging](https://traceapp.info/) ⭐️ 7.0/10

Trace is a new Mac app that records and transcribes meetings entirely offline, activated by a global shortcut, and allows users to flag key moments during a call with inline notes. This addresses a common pain point of forgetting to start transcription apps, by providing a frictionless, shortcut-driven experience that works offline, preserving privacy. Its mid-call flagging feature is novel and integrates well with post-meeting AI summarization workflows. Trace uses macOS microphone and system recording APIs to capture both sides of a conversation as separate tracks and runs on-device diarization for speaker identification. It is sandboxed, never uploads audio or transcripts, and requires a one-time 500MB model download from Hugging Face.

hackernews · AG342 · Jun 13, 20:41 · [Discussion](https://news.ycombinator.com/item?id=48521236)

**Background**: Transcription apps often run in the cloud, raising privacy concerns, and many require manual setup before each call. Trace uses OpenAI's Whisper model, a robust automatic speech recognition system, entirely on-device for offline use.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Whisper_(speech_recognition_system)">Whisper (speech recognition system) - Wikipedia</a></li>
<li><a href="https://github.com/openai/whisper">GitHub - openai/whisper: Robust Speech Recognition via Large-Scale Weak Supervision · GitHub</a></li>
<li><a href="https://openai.com/index/whisper/">Introducing Whisper | OpenAI</a></li>

</ul>
</details>

**Discussion**: Community comments are generally positive, with users appreciating the offline focus and shortcut activation. Some raised concerns about two-party consent legality, auto microphone switching, and crash recovery, while others expressed a desire for non-App Store purchase options.

**Tags**: `#productivity`, `#transcription`, `#macOS`, `#privacy`, `#meetings`

---

<a id="item-9"></a>
## [Caddy Compatibility for zeroserve: 3x Throughput, 70% Lower Latency, But No ACME](https://su3.io/posts/zeroserve-caddy-compat) ⭐️ 7.0/10

Zeroserve announced Caddy compatibility, claiming 3x throughput and 70% lower latency compared to Caddy. However, the implementation lacks ACME support, which is a critical feature for automatic TLS certificate management. This performance claim challenges existing web servers like nginx, but the missing ACME support limits its practical use for production deployments that require automated certificate renewal. It also highlights the ongoing debate between io_uring-based servers and traditional approaches. The performance gains are attributed to zeroserve's use of io_uring for asynchronous I/O and eBPF for scriptability. According to its user manual, zeroserve serves static websites from a tarball and supports hot reload and eBPF scripts, but it does not implement the full Caddy ecosystem including plugins and ACME.

hackernews · losfair · Jun 14, 13:43 · [Discussion](https://news.ycombinator.com/item?id=48527145)

**Background**: zeroserve is a high-performance, zero-config HTTPS server written in Rust, leveraging io_uring and eBPF. io_uring is a Linux kernel interface for efficient asynchronous I/O, reducing overhead compared to traditional syscalls. ACME is the protocol used by Let's Encrypt to automate TLS certificate issuance and renewal, essential for modern web servers.

<details><summary>References</summary>
<ul>
<li><a href="https://su3.io/posts/introducing-zeroserve">zeroserve: a zero-config web server you can script with eBPF</a></li>
<li><a href="https://github.com/losfair/zeroserve/blob/main/docs/user_manual.md">zeroserve/docs/user_manual.md at main · losfair/zeroserve</a></li>
<li><a href="https://en.wikipedia.org/wiki/ACME_protocol">ACME protocol</a></li>

</ul>
</details>

**Discussion**: Commenters expressed skepticism: one noted 'Caddy compatible minus everything that matters, like ACME and plugins,' while another called missing ACME a 'dealbreaker.' A user also raised security concerns about io_uring for web servers, comparing it to libuv.

**Tags**: `#performance`, `#web-server`, `#rust`, `#iouring`, `#caddy`

---

<a id="item-10"></a>
## [Mapping SQLite result columns to source table.column with AI](https://simonwillison.net/2026/Jun/13/sqlite-column-provenance/#atom-everything) ⭐️ 7.0/10

Simon Willison used Claude Code (Opus 4.8) to programmatically identify the source table and column for each result column in arbitrary SQL queries, exploring methods such as APSW, ctypes, and EXPLAIN parsing. This work could enable Datasette to render query results with column provenance information, enriching data exploration. It also demonstrates a practical use of large language models for solving database introspection problems. Claude Code found three promising approaches: using the APSW library, using Python's ctypes to call SQLite's internal sqlite3_column_table_name() C function, and cleverly interrogating EXPLAIN output. None of these methods are yet integrated into Datasette.

rss · Simon Willison · Jun 13, 23:05

**Background**: SQL column provenance tracks which table and column each result column originates from. SQLite has an internal C function for this but does not expose it in Python. Claude Code is Anthropic's AI coding assistant. Datasette is a tool for exploring and publishing SQLite databases.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Claude_Code">Claude Code</a></li>

</ul>
</details>

**Tags**: `#SQL`, `#Datasette`, `#column provenance`, `#LLM`, `#Claude`

---

<a id="item-11"></a>
## [Open-source knowledge graph pipeline boosts LLM multi-hop reasoning](https://www.reddit.com/r/MachineLearning/comments/1u5yyyl/i_built_an_opensource_knowledge_graph_pipeline/) ⭐️ 7.0/10

A developer released an open-source full-stack pipeline called GraphRAG-Studio that constructs knowledge graphs from raw text, detects communities, and uses hybrid retrieval combining dense vectors, BM25, and graph traversal to improve LLM multi-hop reasoning. This pipeline directly addresses the 'lost in the middle' problem in standard vector retrieval, enabling LLMs to answer complex multi-hop queries that require connecting information across multiple text chunks. It provides a practical, open-source tool that could improve accuracy in question answering, document analysis, and other tasks involving large text corpora. The pipeline uses spaCy for named entity recognition, NetworkX for building co-occurrence graphs, and greedy modularity for community detection. It performs hybrid retrieval by simultaneously querying a dense vector index, a BM25 sparse index, and traversing the knowledge graph for neighboring entity chunks, then fuses results using Reciprocal Rank Fusion and re-ranks with a cross-encoder.

reddit · r/MachineLearning · /u/Future_Caregiver_643 · Jun 14, 22:38

**Background**: Multi-hop reasoning in LLMs requires connecting facts from different parts of a document, which standard vector search often fails due to the 'lost in the middle' problem—LLMs tend to ignore information in the middle of a long context. Hybrid retrieval combines dense (semantic) and sparse (keyword) methods, while knowledge graph traversal adds explicit relationships between entities to bridge gaps between disconnected text chunks. Community detection partitions the graph into thematic clusters for global summaries, reducing hub node bias.

<details><summary>References</summary>
<ul>
<li><a href="https://medium.com/@abheshith7/mastering-the-lost-in-the-middle-problem-in-rag-e08482780b0f">Mastering the Lost in the Middle Problem in RAG | Medium</a></li>
<li><a href="https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.community.modularity_max.greedy_modularity_communities.html">greedy_modularity_communities — NetworkX 3.6.1 documentation</a></li>
<li><a href="https://medium.com/@1528371521zx/bm25-in-hybrid-rag-1d0dd48309d8">BM 25 in Hybrid RAG. Original | Xin’s Reading Room | March | Medium</a></li>

</ul>
</details>

**Tags**: `#knowledge graph`, `#hybrid retrieval`, `#open-source`, `#LLM reasoning`, `#community detection`

---

<a id="item-12"></a>
## [PaddleOCR v3-v6 Implemented in C++ with ncnn for Lightweight Deployment](https://www.reddit.com/r/MachineLearning/comments/1u4hy2x/paddleocr_v3v4v5v6_implemented_in_c_with_ncnn_p/) ⭐️ 7.0/10

A developer has released an open-source C++ implementation of PaddleOCR that supports PP-OCR models from v3 to v6, using Tencent's ncnn framework for inference instead of the official Paddle C++ runtime. This project simplifies OCR deployment for developers who need a lightweight, dependency-free solution, making it easier to run PaddleOCR on mobile, embedded, or edge devices where the official runtime is too heavy. The implementation uses ncnn, a high-performance neural network inference framework with no third-party dependencies, and supports GPU acceleration via Vulkan. It covers the latest PaddleOCR v6 model series, building on earlier versions v3-v5.

reddit · r/MachineLearning · /u/Knok0932 · Jun 13, 05:06

**Background**: PaddleOCR is an OCR toolkit developed by Baidu that offers a series of lightweight models called PP-OCR. The official C++ inference runtime is complex and has many dependencies, making deployment challenging. ncnn, developed by Tencent, is a lightweight inference framework optimized for mobile and edge devices, known for its speed and minimal dependencies.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/Tencent/ncnn">GitHub - Tencent/ncnn: ncnn is a high-performance neural network ...</a></li>
<li><a href="https://github.com/PaddlePaddle/PaddleOCR">GitHub - PaddlePaddle/PaddleOCR: Turn any PDF or image document into structured data for your AI. A powerful, lightweight OCR toolkit that bridges the gap between images/PDFs and LLMs. Supports 100+ languages. · GitHub</a></li>

</ul>
</details>

**Tags**: `#OCR`, `#C++`, `#ncnn`, `#PaddleOCR`, `#model deployment`

---

<a id="item-13"></a>
## [Ask HN: Share Your Current Projects (June 2026)](https://news.ycombinator.com/item?id=48528779) ⭐️ 6.0/10

Hacker News users shared their ongoing projects, including an end-to-end encrypted secure enclave router, a city builder game, a browser-based security toolkit, and an open-source location scraper. This monthly thread highlights the diversity and creativity of the Hacker News community, showcasing projects that range from practical security tools to engaging games and open data initiatives. TrustedRouter.com uses Secure Enclaves for end-to-end encryption; Microlandia has sold nearly 10,000 copies; the security toolkit consolidates DNS, WHOIS, and other domain data into one report; AllThePlaces has about 4,700 scrapers extracting 40+ million points of interest.

hackernews · david927 · Jun 14, 16:05

**Background**: Secure enclaves are hardware-isolated execution environments that protect data even from the host system, often used for confidential computing. Open-source scrapers like AllThePlaces gather public location data for use in mapping projects like OpenStreetMap.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.marlin.org/oyster/core-concepts/secure-networking">Secure Networking | Welcome to the Marlin docs!</a></li>
<li><a href="https://evervault.com/blog/built-enclaves-routing-traffic-with-Consul">How we built Enclaves : Routing Traffic with Consul — Blog — Evervault</a></li>

</ul>
</details>

**Discussion**: Commenters showed enthusiasm for the shared projects, with some offering constructive feedback. The thread had high engagement, reflecting the community's interest in practical tools and indie game development.

**Tags**: `#community`, `#projects`, `#hackernews`, `#software`, `#discussion`

---