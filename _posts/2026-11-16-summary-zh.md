---
layout: default
title: "Horizon Summary: 2026-11-16 (ZH)"
date: 2026-11-16
lang: zh
---

> 从 36 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [Meta FAIR 与 NYU 研究：多模态大模型中视觉编码器预训练并非必要](#item-tech-news-1) ⭐️ 9.0/10
2. [现代大语言模型中位置编码技术的深度解析](#item-tech-news-2) ⭐️ 8.0/10
3. [使用调优工具将 B300 上的 cudaMemcpy 速度提升 5 倍](#item-tech-news-3) ⭐️ 8.0/10
4. [美团开源 LongCat-2.5 模型，全程使用华为升腾芯片训练](#item-tech-news-4) ⭐️ 8.0/10
5. [旧版 Bitly 链接遭劫持引发安全风险](#item-tech-news-5) ⭐️ 7.0/10
6. [MacBook Pro OLED 显示屏的 PWM 调光技术及其视觉影响](#item-tech-news-6) ⭐️ 7.0/10
7. [Protomaps 与 PMTiles：降低地图瓦片自托管成本的方案](#item-tech-news-7) ⭐️ 7.0/10
8. [华为云发布开源盘古模型 openPangu-2.1-Pro](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [商务部长卢特尼克因其家族企业与英伟达的关联面临审查](#item-finance-news-1) ⭐️ 8.0/10
2. [英伟达创始人黄仁勋离职背后的政治与行业博弈](#item-finance-news-2) ⭐️ 8.0/10
3. [部分电动自行车因认证暂停无法上牌](#item-finance-news-3) ⭐️ 7.0/10
4. [美法官驳回美光、三星及 SK 海力士 DRAM 价格操纵案撤诉动议](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Meta FAIR 与 NYU 研究：多模态大模型中视觉编码器预训练并非必要](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 9.0/10

Meta FAIR 与 NYU 通过对 200 多个从零训练的多模态大模型进行受控实验，发现视觉编码器的预训练并非提升性能的必要条件，其效果与从零训练的编码器相当。研究指出，虽然预训练可选，但模型必须保留视觉专用参数以维持性能，且将视觉处理模块直接融合进大模型前 8 层（In-fusion）的方案在性能上优于传统独立编码器，同时能降低 13% 的首字生成时间。

reddit · r/MachineLearning · /u/trungh98 · 11月15日 17:38

**「背景」** 当前多模态大模型架构在视觉编码器的使用上存在显著分歧，部分模型选择移除编码器，部分则坚持使用预训练或从零训练的编码器。由于现有模型在数据规模和计算资源上的差异，此前业界难以确定视觉编码器预训练及特定架构设计的实际贡献。

**「影响」** 模型开发者可以放弃昂贵的视觉编码器预训练步骤，转而采用将视觉专用参数直接融合进大模型前层架构的方案，这不仅能节省计算资源，还能在保持视觉问答（VQA）性能的同时提升推理速度。

**标签**: `#Multimodal LLMs`, `#Computer Vision`, `#Machine Learning Research`, `#Model Architecture`

---

<a id="item-tech-news-2"></a>
### [现代大语言模型中位置编码技术的深度解析](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 8.0/10

本文深入探讨了现代大语言模型中多种位置编码技术的实现机制与底层逻辑。文章详细分析了这些技术如何将序列位置信息整合进 Transformer 架构，为开发者和研究人员提供了关于模型如何处理输入顺序的系统性技术参考。

hackernews · vismit2000 · 11月15日 12:14 · [社区讨论](https://news.ycombinator.com/item?id=50506376)

**「背景」** Transformer 架构本身不具备处理序列顺序的能力，因此必须通过位置编码（Positional Embeddings）将序列中词元的相对或绝对位置信息注入模型。早期模型多采用可学习的绝对位置编码，而现代 LLM 已普遍转向旋转位置编码（RoPE），后者通过将位置信息融入注意力机制，在处理长序列时表现出更好的扩展性。

**「社区讨论」** 评论者指出，仅理解实现细节不足以完全掌握位置编码，必须从群表示论的数学视角进行分析。例如，旋转位置编码（RoPE）被视为平移群的表示，这种理论框架对于理解如何参数化及实现可微的位置编码至关重要。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-positional-embeddings">Understanding Positional Embeddings in Modern LLMs</a></li>
<li><a href="https://sebastianraschka.com/llms-from-scratch/ch04/10_rope/">Rotary Positional Embeddings (RoPE) | Sebastian Raschka , PhD</a></li>

</ul>
</details>

**标签**: `#LLM`, `#Transformers`, `#Machine Learning`, `#Deep Learning`, `#Embeddings`

---

<a id="item-tech-news-3"></a>
### [使用调优工具将 B300 上的 cudaMemcpy 速度提升 5 倍](https://www.reddit.com/r/MachineLearning/comments/1xx2n25/making_cudamemcpy_5x_faster_on_a_b300_p/) ⭐️ 8.0/10

开发者发布了一款名为 cmt 的调优工具，旨在优化 CUDA 中的分页内存（pageable）传输性能。在 NVIDIA B300 硬件上，该工具通过对传输过程进行调优，将 1GB 张量的 CPU 到 GPU 传输吞吐量从 10.2 GB/s 提升至 51.5 GB/s，实现了约 5 倍的性能增长。

reddit · r/MachineLearning · /u/makneeee · 11月15日 18:20

**「背景」** cudaMemcpy 是 CUDA 中用于在主机（CPU）和设备（GPU）之间传输数据的核心函数。当使用分页内存进行传输时，系统通常会受到内存复制开销和驱动程序调度策略的限制，导致传输速度低于固定内存（pinned memory）的理论上限。

**「影响」** 对于依赖大规模数据处理的机器学习工作流，该工具能够显著降低 CPU 到 GPU 的数据传输延迟，从而减少数据加载瓶颈并提高整体训练或推理效率。

**标签**: `#CUDA`, `#GPU Computing`, `#Performance Optimization`, `#Machine Learning Infrastructure`, `#Systems Engineering`

---

<a id="item-tech-news-4"></a>
### [美团开源 LongCat-2.5 模型，全程使用华为升腾芯片训练](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

美团 LongCat 团队正式开源了 LongCat-2.5 模型，该模型拥有 1.6 万亿参数，且在训练过程中完全未使用英伟达 GPU，而是全程依赖华为升腾加速卡。该模型支持文本、图像和视频输入，每个 token 激活约 480 亿参数，并以 MIT 许可证发布以支持商用。在 Terminal Bench v2.1 编程基准测试中，该模型取得了 88.4 分的成绩，表现接近 Claude Opus 5 的 89.1 分。

telegram · zaihuapd · 11月15日 11:08

**「背景」** 在当前全球高端 AI 芯片供应受限的背景下，中国科技企业正积极探索基于国产硬件（如华为升腾系列）的大规模模型训练路径。LongCat-2.5 的发布展示了国产算力集群在处理超大规模参数模型训练任务上的可行性。

**「影响」** LongCat-2.5 的开源为开发者提供了一个高性能的替代方案，证明了在不依赖英伟达 GPU 的情况下，通过国产算力同样可以训练出具备复杂编程与多模态处理能力的智能体模型。

**标签**: `#Artificial Intelligence`, `#Large Language Models`, `#Hardware`, `#Open Source`, `#AI Infrastructure`

---

<a id="item-tech-news-5"></a>
### [旧版 Bitly 链接遭劫持引发安全风险](https://ransomnews.com/burger-king-tweet-bitly-link-hijack-2026/) ⭐️ 7.0/10

近期有报告指出，部分旧版 Bitly 缩短链接正被恶意劫持，导致用户被重定向至非预期页面。这一现象暴露了第三方 URL 缩短服务在长期维护和所有权变更过程中存在的安全隐患，可能被用于钓鱼攻击或品牌冒充。

hackernews · hspeiser · 11月15日 22:11 · [社区讨论](https://news.ycombinator.com/item?id=50511395)

**「背景」** URL 短链接服务通过将长网址映射为简短的重定向链接来节省字符空间，但这种机制依赖于服务商对域名和映射记录的长期维护。当原始账户过期或域名所有权失效时，若短链接服务商允许他人重新注册或接管这些失效的短链接，攻击者即可通过修改重定向目标来劫持原本指向合法内容的链接。

**「影响」** 依赖第三方缩短服务的企业和个人面临链接失效或被劫持的风险，建议用户在关键业务中避免使用外部缩短服务，或改用可控的自定义短链接方案以确保重定向的安全性。

**「社区讨论」** 社区用户普遍认为将链接缩短外包给第三方存在长期稳定性风险，并指出当服务商倒闭或账户失效时，链接将面临永久性损坏。部分用户建议通过自建短链接服务来规避此类基础设施脆弱性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://nypost.com/2026/11/15/lifestyle/corporate-social-media-hacked-in-bizarre-bitly-link-hijacking-scheme/">Corporate social media hacked in bizarre Bitly link-hijacking ...</a></li>
<li><a href="https://ransomnews.com/burger-king-tweet-bitly-link-hijack-2026/">Old Bitly links hijacked in Burger King, McDonald’s and Trump ...</a></li>
<li><a href="https://futurepositive.org/old-x-posts-from-burger-king-mcdonalds-and-donald-trump-hijacked-to-redirect-users-to-offensive-historical-links">Burger King, McDonald’s, and Trump X Posts Hijacked via ...</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#web-infrastructure`, `#url-shorteners`, `#digital-security`

---

<a id="item-tech-news-6"></a>
### [MacBook Pro OLED 显示屏的 PWM 调光技术及其视觉影响](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

现代 MacBook Pro 采用的 OLED 显示屏利用脉冲宽度调制（PWM）技术进行亮度调节，引发了关于用户视觉舒适度与健康影响的讨论。技术分析指出，该显示屏的 PWM 频率特性可能导致部分敏感用户出现视觉疲劳或不适。目前关于其实际调光频率的测量结果存在争议，部分观察认为其采用了多层串联 OLED 结构以实现相位偏移，从而提升了视觉上的有效刷新率。

hackernews · MacAnorak · 11月15日 13:15 · [社区讨论](https://news.ycombinator.com/item?id=50506719)

**「背景」** 脉冲宽度调制（PWM）是一种通过快速开关光源来调节显示屏亮度的技术，其频率过低时可能被部分用户感知为闪烁。随着显示技术从 LCD 过渡到 OLED，PWM 调光已成为移动设备显示屏设计中的常见方案，但也因其潜在的视觉健康影响而受到关注。

**「影响」** 对于对闪烁敏感的用户，低频率 PWM 调光可能导致头痛、眼疲劳或注意力难以集中。建议对此类症状敏感的用户在购买前进行实机测试，或关注显示屏在不同亮度等级下的调光行为。

**「社区讨论」** 社区成员对 MacBook Pro OLED 显示屏的实际 PWM 频率存在分歧，有观点认为其通过多层 OLED 异相驱动实现了更高的有效频率。此外，用户讨论了闪烁敏感性与显色指数（CRI）及运动模糊等其他显示因素的关联，并呼吁对 PWM 敏感度进行更深入的科学研究。

**标签**: `#Hardware`, `#Display Technology`, `#Accessibility`, `#OLED`, `#PWM`

---

<a id="item-tech-news-7"></a>
### [Protomaps 与 PMTiles：降低地图瓦片自托管成本的方案](https://bruceroettgers.eu/blog/protomaps/) ⭐️ 7.0/10

Protomaps 结合 PMTiles 格式为开发者提供了一种低成本、易于部署的地图瓦片自托管方案，有效替代了昂贵的商业地图 API。该技术通过将地图数据存储为单一文件并利用对象存储服务（如 Cloudflare R2）进行分发，显著降低了基础设施的维护难度与运营成本。

hackernews · bcye · 11月15日 19:26 · [社区讨论](https://news.ycombinator.com/item?id=50509837)

**「背景」** PMTiles 是一种用于存储金字塔结构瓦片数据的单文件存档格式，允许开发者将地图数据托管在 S3 等通用对象存储服务上，从而实现无需专用瓦片服务器的“无服务器”地图应用。该技术基于 OpenStreetMap 数据集，旨在替代昂贵的第三方地图 API，降低地理空间数据的托管成本与维护复杂度。

**「成本与架构影响」** 开发者通过采用 Protomaps 和 PMTiles 格式，可将地图基础设施从按量计费的第三方 API（如 Google Maps 或 Mapbox）迁移至廉价的通用对象存储（如 Cloudflare R2 或 AWS S3），从而实现零维护的服务器端无感部署。这种架构消除了 API 调用限制与密钥管理需求，使开发者能够以极低的存储和带宽成本实现大规模地图数据的自托管，特别适用于对隐私有要求或预算有限的个人与商业项目。

**「社区讨论」** 开发者普遍认为 Protomaps 使得个人项目和小型应用能够负担得起地图渲染功能，并指出该方案在隐私保护和访问控制方面具有优势。同时，社区成员也讨论了 OpenFreeMap 等替代方案，并提醒高分辨率卫星影像在存储和带宽成本上仍存在显著挑战。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.protomaps.com/pmtiles/">PMTiles Concepts | Protomaps Docs</a></li>
<li><a href="https://docs.protomaps.com/">Protomaps Documentation | Protomaps Docs</a></li>
<li><a href="https://github.com/protomaps/PMTiles">GitHub - protomaps/PMTiles: Pyramids of map tiles in a single ...</a></li>
<li><a href="https://protomaps.com/about">Protomaps - The open source map in a file</a></li>
<li><a href="https://github.com/protomaps/PMTiles">GitHub - protomaps / PMTiles : Pyramids of map tiles in a single file on...</a></li>
<li><a href="https://www.antoniogioia.com/protomaps-open-source-single-file-maps">Protomaps : open source single file maps - Blog, Antonio Gioia</a></li>

</ul>
</details>

**标签**: `#mapping`, `#geospatial`, `#web-development`, `#infrastructure`, `#open-source`

---

<a id="item-tech-news-8"></a>
### [华为云发布开源盘古模型 openPangu-2.1-Pro](https://mp.weixin.qq.com/s/8JfFmscBTDl_mPQMycD8Nw) ⭐️ 7.0/10

华为云于 11 月 15 日正式上线开源盘古模型 openPangu-2.1-Pro，重点提升了 Agent 开发、鸿蒙 ArkTS 编码及升腾算子生成能力。该模型已接入华为云的 AgentArts、CodeArts 和 OfficeAce 等产品，并公布了明确的推理定价，其中推理输入价格为 0.8 元/百万 tokens，输出价格为 3.2 元/百万 tokens。

telegram · zaihuapd · 11月15日 16:03

**「背景」** 盘古模型是华为云推出的企业级大模型系列，旨在通过模型即服务（MaaS）平台为开发者提供特定领域的 AI 能力支持。此次更新进一步强化了其在华为自有生态系统中的集成度。

**「影响」** 使用鸿蒙 ArkTS 进行开发的工程师及依赖升腾算力平台的开发者，现在可以利用该模型优化代码生成效率，并根据公开的推理定价更精准地评估项目成本。

**标签**: `#Huawei Cloud`, `#Large Language Models`, `#Artificial Intelligence`, `#Software Engineering`, `#HarmonyOS`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [商务部长卢特尼克因其家族企业与英伟达的关联面临审查](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

美国商务部长霍华德·卢特尼克（Howard Lutnick）因其家族企业 Cantor Fitzgerald 与英伟达（Nvidia）的密切商业往来，以及被指在情报部门警告英伟达涉嫌违规向中国出口芯片期间阻挠制裁而面临审查。尽管 Cantor Fitzgerald 在 2025 年 9 月至 2026 年 3 月期间将其持有的英伟达股票数量削减了近 50%，但该机构仍与英伟达及其合作伙伴保持着数十亿美元的融资业务往来。

rss · CNBC Finance · 11月15日 19:58

**「背景」** 卢特尼克在 2025 年 2 月出任商务部长前曾执掌 Cantor Fitzgerald，目前该机构由其子管理。此前有报道称，美国政府内部曾多次讨论将涉嫌协助芯片走私的关联公司列入限制名单，但卢特尼克被指对此持抵制态度。

**「影响」** 此次争议引发了外界对政府高官在处理涉及国家安全出口管制与个人家族商业利益之间潜在利益冲突的担忧。

**标签**: `#Corporate Governance`, `#Geopolitics`, `#Semiconductors`, `#Regulation`, `#Ethics`

---

<a id="item-finance-news-2"></a>
### [英伟达创始人黄仁勋离职背后的政治与行业博弈](https://www.washingtonpost.com/technology/2026/11/13/behind-jensen-huangs-spy-scandal-shadow-war-trumps-ear-china/) ⭐️ 8.0/10

据《华盛顿邮报》报道，英伟达创始人黄仁勋的离职被指是一场由政界人士与竞争对手策划的“猎杀”行动，旨在推动更严格的对华芯片出口限制。随着黄仁勋离职，美国众议院相关委员会正计划将包括限制高端 AI 芯片出口及强制内置防走私追踪技术在内的三项严厉条款，纳入年底的国防法案中。

telegram · zaihuapd · 11月15日 08:08

**「背景信息」** 黄仁勋此前曾利用与特朗普的私交游说放宽对华芯片出口，并公开反对在芯片中植入追踪功能，这与主张严格限制对华出口并要求芯片内置“固件级锁”的竞争对手 Anthropic 存在直接利益冲突。

**「潜在影响」** 若相关国防法案条款通过，全球半导体行业将面临更严苛的出口管制，且芯片制造商可能被迫在产品中加入追踪技术，这将直接改变 AI 硬件的合规标准与市场准入规则。

**标签**: `#Nvidia`, `#Geopolitics`, `#Semiconductors`, `#AI Policy`, `#Export Controls`

---

<a id="item-finance-news-3"></a>
### [部分电动自行车因认证暂停无法上牌](https://www.peopleapp.com/column/30053564254-500007786629) ⭐️ 7.0/10

因九号、雅迪、爱玛等多个品牌的电动自行车 3C 认证证书被暂停，导致消费者在多地无法办理车辆登记。目前各品牌方尚未给出认证恢复的具体时间表。

telegram · zaihuapd · 11月15日 06:08

**「背景」** 国家市场监管总局此前检查发现部分企业存在更换关键部件或预留解限速空间等违规行为，随后认证机构暂停了相关证书，且 11 月 1 日起实施的新规进一步收紧了对车辆合规性的监管。

**「影响」** 已购买相关品牌车辆的消费者面临无法上牌的困境，且在要求退货时常因车辆已被激活而遭遇门店拒绝，引发了广泛的消费纠纷。

**标签**: `#Electric Bicycles`, `#Regulatory Compliance`, `#3C Certification`, `#Consumer Rights`, `#Manufacturing`

---

<a id="item-finance-news-4"></a>
### [美法官驳回美光、三星及 SK 海力士 DRAM 价格操纵案撤诉动议](https://www.tomshardware.com/tech-industry/big-tech/judge-denies-motion-to-dismiss-dram-price-fixing-lawsuit-against-micron-samsung-and-sk-hynix-says-chipmakers-acted-like-hawks-flying-in-formation-finds-evidence-of-dram-collusion-plausible-after-500-percent-price-surge) ⭐️ 7.0/10

美国法官驳回了美光、三星和 SK 海力士要求撤销 DRAM 价格操纵集体诉讼的动议，案件将继续审理。原告指控这三家芯片制造商通过限制供应，导致 DRAM 价格在一年内上涨了高达 500%。

telegram · zaihuapd · 11月15日 16:39

**「背景」** DRAM 是计算机中常用的动态随机存取存储器，此次诉讼由 17 名个人及小企业发起，指控上述厂商通过同步行为操纵市场价格。

**「影响」** 该裁决意味着全球主要存储芯片厂商将面临法律诉讼，可能导致其面临巨额赔偿或监管处罚，并对半导体行业的定价机制产生深远影响。

**标签**: `#DRAM`, `#Antitrust`, `#Semiconductors`, `#Litigation`, `#Micron`

---