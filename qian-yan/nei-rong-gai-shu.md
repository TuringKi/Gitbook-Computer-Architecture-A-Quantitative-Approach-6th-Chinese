# 内容概述

[第一章](../di-yi-zhang-liang-hua-she-ji-he-fen-xi-de-ji-chu-zhi-shi/)包括能效、静态功率、动态功率、集成电路成本、可靠性和可用性的公式。(这些公式也可以在封面内页找到。)我们希望这些主题可以贯穿本书的其他部分。除了计算机设计和性能测量的经典定量原则外，本书还展示了通用微处理器性能改进的缓慢过程，这也是特定领域架构（DSA）的一个灵感来源。

我们的观点是，与1990年相比，今天的指令集结构所起的作用较小，因此我们将这一材料移到了[附录A](../fu-luazhi-ling-ji-she-ji-yuan-ze.md)。它现在使用RISC-V架构。(为了快速回顾，RISC-V ISA的摘要可以在封面内页找到)。对于ISA的爱好者来说，[附录K](../fu-lukzhi-ling-ji-jia-gou-de-hui-gu.md)为这个版本进行了修订，涵盖了8种RISC架构（5种用于桌面和服务器，3种用于嵌入式）、80×86、DEC VAX和IBM 360/370。

然后，我们在[第二章](../di-er-zhang-nei-cun-ceng-ci-jie-gou-she-ji.md)中转入内存的层次结构，因为很容易将成本-性能-功耗原则应用到这个问题中，而且内存是其余章节的关键资源。和过去的版本一样，[附录B](../fu-lubnei-cun-ceng-ci-jie-gou-de-hui-gu/)包含了对高速缓存原理的介绍性回顾，可以在你需要的时候使用。[第二章](../di-er-zhang-nei-cun-ceng-ci-jie-gou-she-ji.md)讨论了缓存的10个高级优化技术。本章也将介绍虚拟机，它在保护、软件管理和硬件管理方面具有优势，并在云计算中发挥着重要作用。除了涵盖SRAM和DRAM技术外，该章还包括关于闪存和使用堆叠式芯片封装来扩展内存层次的资料介绍。PIAT的例子是用于PMD的ARM Cortex A8和用于服务器的Intel Core i7。

[第三章](../di-san-zhang-zhi-ling-ji-bing-hang-ji-qi-ying-yong.md)涉及高性能处理器中指令级并行的使用，包括超标量执行、分支预测（包括新的标记混合预测器）、推测、动态调度和同步多线程。如前所述，[附录C](../fu-lucliu-shui-xian-chu-ji-he-zhong-ji-gai-nian.md)是对流水线的回顾，以防你需要它。[第三章](../di-san-zhang-zhi-ling-ji-bing-hang-ji-qi-ying-yong.md)还探讨了ILP的局限性。和[第二章](../di-er-zhang-nei-cun-ceng-ci-jie-gou-she-ji.md)一样，PIAT的例子还是ARM Cortex A8和Intel Core i7。虽然第三版包含了大量关于Itanium和VLIW的内容，但这些材料现在在附录H中，表明我们认为这种架构没有达到早期的要求。

游戏和视频处理等多媒体应用的重要性日益增加，这也提高了能够利用数据级并行性的架构的重要性。特别是，人们对使用图形处理单元（GPU）进行计算的兴趣越来越大，但很少有架构师了解GPU的真正工作原理。我们决定写一个新的章节，在很大程度上是为了揭开这种新式计算机架构的面纱。[第四章](../di-si-zhang-shi-liang-simd-he-gpu-jia-gou-zhong-de-shu-ju-ji-bing-hang-xing.md)首先介绍了矢量架构，作为解释多媒体SIMD指令集扩展和GPU的基础。(本章介绍了Roofline性能模型，然后用它来比较英特尔酷睿i7和NVIDIA GTX 280和GTX 480 GPU。本章还介绍了用于PMD的Tegra 2 GPU。

[第五章](../di-wu-zhang-xian-cheng-ji-bing-hang.md)介绍了多核处理器。它探讨了对称和分布式内存架构，研究了组织原则（organizational principles）和性能。本章的主要补充内容包括对多核组织的更多比较，包括多核多级缓存的组织、多核一致性方案和片上多核互连。接下来是同步和内存一致性模型方面的话题。例子是Intel Core i7。对互连网络更深入感兴趣的读者应阅读[附录F](../fu-lufduo-ji-hu-lian.md)，对更大规模的多核处理器和科学计算感兴趣的读者应阅读[附录I](../fu-luida-gui-mo-duo-chu-li-qi-he-ke-xue-ji-suan-de-ying-yong.md)。

[第6章](../di-liu-zhang-da-gui-mo-shu-ju-zhong-xin-ji-ji-suan-ji-de-bing-hang-xing-qing-qiu-ji-bing-hang-rlp-he.md)介绍了数据仓库级计算机（Warehouse-Scale Computers, WSCs）。它在谷歌和亚马逊网络服务的工程师的帮助下进行了广泛的修订。本章整合了很少有架构师知道的关于WSCs的设计、成本和性能的细节。它从流行的MapReduce编程模型开始，然后描述了WSCs的架构和物理实现，包括成本。成本使我们能够解释云计算的出现，据此，在云中使用WSCs进行计算可能比在本地数据中心计算更便宜。PIAT的例子是对谷歌WSC的描述，其中包括本书中首次发布的信息。

新的[第七章](../di-qi-zhang-ling-yu-te-ding-jia-gou-dsa.md)激发了对特定领域架构（DSA）的需求。它在四个DSA实例的基础上得出了DSA的指导原则。每个DSA都对应于已经部署在商业环境中的芯片。我们还解释了为什么在通用微处理器的单线程性能停滞不前的情况下，我们期望通过DSA实现计算机架构的复兴。

[附录A](../fu-luazhi-ling-ji-she-ji-yuan-ze.md)涵盖了ISA的原理，包括RISC-V，[附录K](../fu-lukzhi-ling-ji-jia-gou-de-hui-gu.md)描述了64位版本的RISC V、ARM、MIPS、Power和SPARC及其多媒体扩展。它还包括一些经典架构（80x86、VAX和IBM 360/370）和流行的嵌入式指令集（Thumb-2、microMIPS和RISCV C）。[附录H](../fu-lu-hvliw-he-epic-de-ying-jian-he-ruan-jian.md)是相关的，因为它涵盖了VLIW ISA的架构和编译器。

如前所述，[附录B](../fu-lubnei-cun-ceng-ci-jie-gou-de-hui-gu/)和[附录C](../fu-lucliu-shui-xian-chu-ji-he-zhong-ji-gai-nian.md)是关于基本缓存和流水线概念的教程。对缓存比较陌生的读者应该在[第二章](../di-er-zhang-nei-cun-ceng-ci-jie-gou-she-ji.md)之前阅读[附录B](../fu-lubnei-cun-ceng-ci-jie-gou-de-hui-gu/)，而对流水线比较陌生的读者应该在第三章之前阅读[附录C](../fu-lucliu-shui-xian-chu-ji-he-zhong-ji-gai-nian.md)。

[附录D](../fu-ludcun-chu-xi-tong.md)，"存储系统"，扩充了如下内容：对可靠性和可用性的讨论，对RAID进行了指导性介绍，对RAID 6方案进行了描述，并对真实系统的故障统计数据进行了罕见的介绍。它继续提供了对排队理论和I/O性能基准的介绍。我们评估了一个真实集群的成本、性能和可靠性：互联网档案馆（Internet Archive）。“把它放在一起”的例子是NetApp FAS6000档案机。

Thomas M. Conte 撰写的[附录E](../fu-lueqian-ru-shi-xi-tong.md)，将嵌入式相关的材料整合到一个地方。

关于多机互联的[附录F](../fu-lufduo-ji-hu-lian.md)，由Timothy M. Pinkston和José Duato修订。[附录G](../fu-lugshen-ru-xiang-liang-chu-li-qi.md)，最初由Krste Asanović撰写，包括对矢量处理器的描述。我们认为这两个附录是我们所知道的关于每个主题的一些最好的材料。

[附录H](../fu-lu-hvliw-he-epic-de-ying-jian-he-ruan-jian.md)介绍了VLIW和EPIC，即Itanium的架构。

[附录I](../fu-luida-gui-mo-duo-chu-li-qi-he-ke-xue-ji-suan-de-ying-yong.md)描述了并行处理的应用和更大规模的、共享内存多处理的一致性协议。[附录J](../fu-lujji-suan-ji-suan-shu-arithmetic-xiang-guan.md)，由David Goldberg撰写，描述了计算机算术。

Abhishek Bhattacharjee撰写的[附录L](../fu-luldi-zhi-fan-yi-address-translation-de-gao-ji-gai-nian.md)是新的，讨论了内存管理的高级技术，重点是对虚拟机的支持和对超大地址空间的地址转换设计。随着云计算处理器的增长，这些架构上的改进正变得越来越重要。

[附录M](../fu-lumli-shi-guan-dian-he-can-kao-wen-xian.md)将每一章的 "历史观点和参考文献 "收集到一个附录中。它试图对每一章中的想法给予适当的肯定，并对围绕这些发明的历史有所了解。我们喜欢把这看作是介绍计算机设计的戏剧。它还提供了计算机体系结构的学生可能想要追求的参考资料。如果你有时间，我们建议阅读这些章节中提到的该领域的一些经典论文。直接从创作者那里听到这些想法，既愉快又有教育意义。"历史透视 "是以前版本中最受欢迎的部分之一。



