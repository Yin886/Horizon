---
layout: default
title: "Horizon Summary: 2026-11-16 (EN)"
date: 2026-11-16
lang: en
---

> From 36 items, 12 important content pieces were selected

---

**Technology News**
1. [Meta FAIR and NYU Study Challenges Multimodal Vision Encoder Necessity](#item-tech-news-1) ⭐️ 9.0/10
2. [Technical Analysis of Positional Embedding Architectures in LLMs](#item-tech-news-2) ⭐️ 8.0/10
3. [Developer releases tuner tool to accelerate cudaMemcpy on NVIDIA B300 GPUs](#item-tech-news-3) ⭐️ 8.0/10
4. [Meituan Releases LongCat-2.5, a 1.6 Trillion Parameter Model Trained on Huawei Ascend](#item-tech-news-4) ⭐️ 8.0/10
5. [Security Risks Identified in Hijacked Legacy Bitly Links](#item-tech-news-5) ⭐️ 7.0/10
6. [Technical Analysis of PWM Flicker in MacBook Pro OLED Displays](#item-tech-news-6) ⭐️ 7.0/10
7. [Self-hosting map tiles with Protomaps and PMTiles](#item-tech-news-7) ⭐️ 7.0/10
8. [Huawei Cloud Releases openPangu-2.1-Pro Model](#item-tech-news-8) ⭐️ 7.0/10

**Financial News**
1. [Scrutiny of Commerce Secretary Howard Lutnick&\#x27;s Nvidia Ties](#item-finance-news-1) ⭐️ 8.0/10
2. [Nvidia Founder Jensen Huang&\#x27;s Departure Linked to Political Pressure](#item-finance-news-2) ⭐️ 8.0/10
3. [Electric Bicycle Certification Suspensions](#item-finance-news-3) ⭐️ 7.0/10
4. [U.S. Judge Allows DRAM Price-Fixing Lawsuit to Proceed](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Meta FAIR and NYU Study Challenges Multimodal Vision Encoder Necessity](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 9.0/10

A study by Meta FAIR and NYU, involving the training of over 200 multimodal LLMs, concludes that separate vision encoder pretraining is unnecessary for performance. While pretraining does not improve VQA benchmarks, the researchers found that vision-specific parameters are essential, as encoder-free models require significantly more compute to match performance. The study also demonstrates that integrating vision-only weights directly into the LLM&\#x27;s initial layers, a method termed &quot;in-fusion,&quot; performs as well as traditional separate encoders while reducing latency.

reddit · r/MachineLearning · /u/trungh98 · Nov 15, 17:38

**「Architectural Debate in Multimodal LLMs」** Current multimodal model designs vary significantly, with some architectures utilizing dedicated vision encoders, others training encoders from scratch, and some omitting them entirely. This study addresses the lack of consensus by isolating variables like pretraining and parameter placement within a controlled, compute-matched environment.

**「Implications for Model Development」** Developers can optimize multimodal model efficiency by abandoning separate encoder pretraining and adopting &quot;in-fusion&quot; techniques, which integrate vision-specific parameters directly into the LLM&\#x27;s early layers to achieve comparable VQA performance with lower time-to-first-token latency.

**Tags**: `#Multimodal LLMs`, `#Computer Vision`, `#Machine Learning Research`, `#Model Architecture`

---

<a id="item-tech-news-2"></a>
### [Technical Analysis of Positional Embedding Architectures in LLMs](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 8.0/10

This technical overview examines the mechanics and implementation of various positional embedding techniques utilized in modern transformer-based Large Language Models. It details how these embeddings provide sequence order information to models that otherwise process input tokens as unordered sets.

hackernews · vismit2000 · Nov 15, 12:14 · [Discussion](https://news.ycombinator.com/item?id=50506376)

**「Background」** Transformer architectures require positional information because the self-attention mechanism is inherently permutation-invariant, meaning it treats all tokens as a set rather than a sequence. Early models utilized learned absolute positional embeddings, but modern architectures have shifted toward relative methods like Rotary Positional Embeddings \(RoPE\) to improve scalability and sequence length handling.

**「Community Discussion」** Commenters argue that a complete understanding of positional embeddings requires grounding in group representation theory, noting that techniques like Rotary Positional Embeddings \(RoPE\) function as representations of the translation group.

<details><summary>References</summary>
<ul>
<li><a href="https://sebastianraschka.com/llms-from-scratch/ch04/10_rope/">Rotary Positional Embeddings (RoPE) | Sebastian Raschka , PhD</a></li>

</ul>
</details>

**Tags**: `#LLM`, `#Transformers`, `#Machine Learning`, `#Deep Learning`, `#Embeddings`

---

<a id="item-tech-news-3"></a>
### [Developer releases tuner tool to accelerate cudaMemcpy on NVIDIA B300 GPUs](https://www.reddit.com/r/MachineLearning/comments/1xx2n25/making_cudamemcpy_5x_faster_on_a_b300_p/) ⭐️ 8.0/10

A developer has released an open-source tuner tool that increases the throughput of pageable cudaMemcpy operations by approximately 5x on NVIDIA B300 hardware. The tool, which optimizes CPU-to-GPU data transfers, demonstrated a performance improvement from 10.2 GB/s to 51.5 GB/s when copying a 1 GB tensor in benchmark tests. The implementation is available for use via a command-line interface.

reddit · r/MachineLearning · /u/makneeee · Nov 15, 18:20

**「Background」** The cudaMemcpy function is a standard CUDA API used to transfer data between host \(CPU\) and device \(GPU\) memory. Pageable memory transfers are often slower than pinned \(page-locked\) memory transfers because the driver must perform an intermediate copy to a staging buffer before the data can be moved to the GPU.

**「Impact」** Engineers working with large-scale machine learning models or data-intensive GPU workloads can use this tool to reduce latency bottlenecks during host-to-device data transfers without requiring manual memory pinning.

**Tags**: `#CUDA`, `#GPU Computing`, `#Performance Optimization`, `#Machine Learning Infrastructure`, `#Systems Engineering`

---

<a id="item-tech-news-4"></a>
### [Meituan Releases LongCat-2.5, a 1.6 Trillion Parameter Model Trained on Huawei Ascend](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

Meituan has open-sourced the weights for LongCat-2.5, a 1.6 trillion parameter agent model designed for complex, multi-step programming tasks. The model was trained exclusively on Huawei Ascend hardware, bypassing Nvidia GPUs entirely. It features 48 billion active parameters per token, supports multimodal inputs, and is available under an MIT license.

telegram · zaihuapd · Nov 15, 11:08

**「Background」** The development of large-scale AI models in China has faced significant challenges due to export restrictions on high-end Nvidia GPUs. LongCat-2.5 represents a shift toward utilizing domestic alternatives like Huawei&\#x27;s Ascend series to achieve performance levels competitive with top-tier proprietary models.

**「Impact」** LongCat-2.5 demonstrates that high-performance, large-scale model training is viable on non-Nvidia infrastructure, providing developers with a high-capability, commercially permissive alternative for agentic workflows.

**Tags**: `#Artificial Intelligence`, `#Large Language Models`, `#Hardware`, `#Open Source`, `#AI Infrastructure`

---

<a id="item-tech-news-5"></a>
### [Security Risks Identified in Hijacked Legacy Bitly Links](https://ransomnews.com/burger-king-tweet-bitly-link-hijack-2026/) ⭐️ 7.0/10

Reports indicate that legacy Bitly links are being hijacked, allowing unauthorized actors to redirect traffic from established URLs to malicious destinations. This vulnerability stems from the long-term instability of third-party URL shortening services, where abandoned or expired accounts can be repurposed to facilitate phishing and brand impersonation. Users and organizations relying on these services face significant security risks due to the loss of control over link redirection.

hackernews · hspeiser · Nov 15, 22:11 · [Discussion](https://news.ycombinator.com/item?id=50511395)

**「URL Shortening and Link Expiration」** URL shorteners function by mapping a unique, abbreviated string to a long-form destination URL within a provider&\#x27;s database. When a user account associated with these links becomes inactive or the domain registration lapses, the previously mapped short links may become available for re-registration by third parties, allowing them to redirect traffic to arbitrary new destinations.

**「Impact」** Organizations and individuals should audit their historical digital footprints and replace legacy shortened links with permanent, self-hosted alternatives to prevent potential redirection to malicious content.

**「Community Discussion」** Commenters argue that outsourcing link management creates systemic fragility, noting that reliance on third-party services leads to broken links and security vulnerabilities when companies fail or accounts are abandoned. Some users advocate for self-hosting short links to maintain long-term control and avoid the risks associated with centralized URL shortening platforms.

<details><summary>References</summary>
<ul>
<li><a href="https://nypost.com/2026/11/15/lifestyle/corporate-social-media-hacked-in-bizarre-bitly-link-hijacking-scheme/">Corporate social media hacked in bizarre Bitly link-hijacking ...</a></li>
<li><a href="https://ransomnews.com/burger-king-tweet-bitly-link-hijack-2026/">Old Bitly links hijacked in Burger King, McDonald’s and Trump ...</a></li>
<li><a href="https://futurepositive.org/old-x-posts-from-burger-king-mcdonalds-and-donald-trump-hijacked-to-redirect-users-to-offensive-historical-links">Burger King, McDonald’s, and Trump X Posts Hijacked via ...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#web-infrastructure`, `#url-shorteners`, `#digital-security`

---

<a id="item-tech-news-6"></a>
### [Technical Analysis of PWM Flicker in MacBook Pro OLED Displays](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

Recent technical analysis of the latest MacBook Pro OLED displays highlights concerns regarding Pulse Width Modulation \(PWM\) dimming and its potential impact on user comfort. While some reports suggest a base PWM frequency of 240Hz, others argue that the tandem OLED architecture may effectively achieve higher frequencies through phase-shifted operation. These findings raise questions about display engineering choices and their physiological effects on users sensitive to screen flicker.

hackernews · MacAnorak · Nov 15, 13:15 · [Discussion](https://news.ycombinator.com/item?id=50506719)

**「Background」** Pulse Width Modulation is a common technique used to control display brightness by rapidly cycling the backlight or pixels on and off. Because OLED panels lack a constant backlight, they rely on this rapid switching, which can cause perceptible flicker for some users, potentially leading to eye strain or headaches.

**「Impact」** Users sensitive to low-frequency flicker may experience visual fatigue or discomfort when using these displays at lower brightness levels. Prospective buyers with a history of light sensitivity or neurological conditions should consider testing the device in person before purchase, as individual tolerance to PWM frequencies varies significantly.

**「Community Discussion」** Commenters are debating the actual PWM frequency of the new displays, with some suggesting that the tandem OLED design may mitigate flicker through phase-shifted operation. Others have expanded the conversation to include broader concerns regarding display technology, such as Color Rendering Index \(CRI\) and motion blur, noting that flicker sensitivity remains a poorly understood but significant accessibility issue.

**Tags**: `#Hardware`, `#Display Technology`, `#Accessibility`, `#OLED`, `#PWM`

---

<a id="item-tech-news-7"></a>
### [Self-hosting map tiles with Protomaps and PMTiles](https://bruceroettgers.eu/blog/protomaps/) ⭐️ 7.0/10

Protomaps and the PMTiles format enable developers to self-host map infrastructure, significantly reducing costs compared to proprietary mapping APIs like Mapbox or Google Maps. By utilizing a single-file archive format, developers can serve map data directly from object storage services like Cloudflare R2 without the need for a dedicated tile server. This approach allows for greater control over privacy and access while maintaining affordability for side projects and applications with high request volumes.

hackernews · bcye · Nov 15, 19:26 · [Discussion](https://news.ycombinator.com/item?id=50509837)

**「Background on Protomaps and PMTiles」** PMTiles is a single-file archive format designed to store pyramids of tiled geospatial data, such as vector basemaps derived from OpenStreetMap. By utilizing this format, developers can host map data on commodity object storage services like Amazon S3 or Cloudflare R2, eliminating the need for traditional, high-maintenance tile server backends.

**「Cost and Infrastructure Impact」** Developers can replace metered, third-party mapping APIs like Google Maps or Mapbox with Protomaps and the PMTiles format to eliminate per-request costs and vendor lock-in. By hosting map data as single-file archives on commodity object storage, organizations can achieve serverless, unmetered map delivery while maintaining full control over infrastructure and user privacy.

**「Community Discussion」** Users report that Protomaps makes previously cost-prohibitive projects feasible, though some note that high-resolution satellite imagery remains storage-intensive at higher zoom levels. Commenters also highlighted alternative projects like OpenFreeMap and the use of tools like &\#x27;gloss&\#x27; for interacting with PMTiles archives.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.protomaps.com/pmtiles/">PMTiles Concepts | Protomaps Docs</a></li>
<li><a href="https://docs.protomaps.com/">Protomaps Documentation | Protomaps Docs</a></li>
<li><a href="https://github.com/protomaps/PMTiles">GitHub - protomaps/PMTiles: Pyramids of map tiles in a single ...</a></li>
<li><a href="https://protomaps.com/about">Protomaps - The open source map in a file</a></li>
<li><a href="https://github.com/protomaps/PMTiles">GitHub - protomaps / PMTiles : Pyramids of map tiles in a single file on...</a></li>
<li><a href="https://www.antoniogioia.com/protomaps-open-source-single-file-maps">Protomaps : open source single file maps - Blog, Antonio Gioia</a></li>

</ul>
</details>

**Tags**: `#mapping`, `#geospatial`, `#web-development`, `#infrastructure`, `#open-source`

---

<a id="item-tech-news-8"></a>
### [Huawei Cloud Releases openPangu-2.1-Pro Model](https://mp.weixin.qq.com/s/8JfFmscBTDl_mPQMycD8Nw) ⭐️ 7.0/10

Huawei Cloud has launched the openPangu-2.1-Pro model, which introduces specific enhancements for Agent development and AI-assisted coding. The model is optimized for HarmonyOS ArkTS development and Ascend operator generation, with inference pricing set at 0.8 yuan per million tokens for input and 3.2 yuan per million tokens for output.

telegram · zaihuapd · Nov 15, 16:03

**「Background」** The Pangu model series serves as Huawei&\#x27;s enterprise-grade large language model architecture, designed to integrate with the company&\#x27;s proprietary Ascend hardware and software ecosystem.

**「Impact」** Developers working within the HarmonyOS and Ascend environments can now utilize specialized tools like AgentArts and CodeArts, while benefiting from significantly reduced costs for cached input tokens at 0.016 yuan per million tokens.

**Tags**: `#Huawei Cloud`, `#Large Language Models`, `#Artificial Intelligence`, `#Software Engineering`, `#HarmonyOS`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Scrutiny of Commerce Secretary Howard Lutnick&\#x27;s Nvidia Ties](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

Commerce Secretary Howard Lutnick faces ethics questions regarding his alleged resistance to export crackdowns on companies linked to Nvidia, a firm with which his former company, Cantor Fitzgerald, maintains significant business ties. While Cantor Fitzgerald reduced its reported Nvidia share holdings by nearly 50% between September 2025 and March 2026, the firm continues to arrange financing for Nvidia&\#x27;s business partners.

rss · CNBC Finance · Nov 15, 19:58

**「Background」** Lutnick, who previously led Cantor Fitzgerald, has faced reports of resisting administration efforts to restrict the export of advanced artificial intelligence chips to China amid intelligence warnings concerning Nvidia&\#x27;s leadership.

**「Impact」** The situation has created political friction within the Trump administration, with Treasury Secretary Scott Bessent publicly noting that other federal agencies had supported placing suspected smuggling entities on a restricted list for months.

**Tags**: `#Corporate Governance`, `#Geopolitics`, `#Semiconductors`, `#Regulation`, `#Ethics`

---

<a id="item-finance-news-2"></a>
### [Nvidia Founder Jensen Huang&\#x27;s Departure Linked to Political Pressure](https://www.washingtonpost.com/technology/2026/11/13/behind-jensen-huangs-spy-scandal-shadow-war-trumps-ear-china/) ⭐️ 8.0/10

Nvidia founder Jensen Huang&\#x27;s departure is reportedly the result of a coordinated campaign by political figures and industry rival Anthropic to influence U.S. chip export policy. Lawmakers are now using this shift to push for three new restrictions in the upcoming National Defense Authorization Act, including stricter AI chip export limits and mandatory anti-smuggling tracking technology.

telegram · zaihuapd · Nov 15, 08:08

**「Background」** Huang had previously leveraged personal ties to President Trump to advocate for looser export controls on chips sold to China, directly opposing Anthropic&\#x27;s lobbying efforts for stricter hardware oversight and built-in tracking mechanisms.

**「Impact」** The potential legislative changes threaten to significantly tighten the supply of high-end AI hardware to China and impose new technical requirements on global semiconductor manufacturers.

**Tags**: `#Nvidia`, `#Geopolitics`, `#Semiconductors`, `#AI Policy`, `#Export Controls`

---

<a id="item-finance-news-3"></a>
### [Electric Bicycle Certification Suspensions](https://www.peopleapp.com/column/30053564254-500007786629) ⭐️ 7.0/10

Major electric bicycle brands including Ninebot, Yadea, and Aima have had their 3C safety certifications suspended, preventing consumers from registering their vehicles. Regulators issued these suspensions after finding that manufacturers had replaced critical components or modified vehicles to bypass speed limits.

telegram · zaihuapd · Nov 15, 06:08

**「Background」** The 3C certification is a mandatory safety standard for products sold in China, and new, stricter regulations requiring a unique code for each vehicle, battery, and charger took effect on November 1, 2026.

**「Impact」** Consumers are facing significant financial disputes as retailers refuse to accept returns for non-registerable vehicles, while the industry faces uncertainty with no clear timeline for certification restoration.

**Tags**: `#Electric Bicycles`, `#Regulatory Compliance`, `#3C Certification`, `#Consumer Rights`, `#Manufacturing`

---

<a id="item-finance-news-4"></a>
### [U.S. Judge Allows DRAM Price-Fixing Lawsuit to Proceed](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

A U.S. judge denied a motion to dismiss a class-action lawsuit accusing Micron, Samsung, and SK Hynix of colluding to fix DRAM prices. The plaintiffs allege that the chipmakers coordinated to restrict supply, leading to price increases of up to 500% over a one-year period.

telegram · zaihuapd · Nov 15, 16:39

**「Background」** The lawsuit involves allegations of antitrust violations, which occur when companies illegally coordinate to limit competition and manipulate market prices.

**「Impact」** The ruling exposes Micron, Samsung, and SK Hynix to ongoing legal proceedings and potential financial liabilities related to their semiconductor pricing practices.

**Tags**: `#DRAM`, `#Antitrust`, `#Semiconductors`, `#Litigation`, `#Micron`

---