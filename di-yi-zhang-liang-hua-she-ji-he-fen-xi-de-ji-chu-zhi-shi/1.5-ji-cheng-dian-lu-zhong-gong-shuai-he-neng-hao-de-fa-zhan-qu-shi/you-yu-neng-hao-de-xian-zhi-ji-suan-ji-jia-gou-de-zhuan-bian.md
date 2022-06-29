# 由于能耗的限制，计算机架构的转变

随着晶体管改进速度的减慢，计算机设计师必须从其他地方寻找改进的能源效率。事实上，考虑到能源预算，今天很容易设计出具有如此多晶体管的微处理器，以至于它们无法同时开启。这种现象被称为 "暗硅"，即由于热限制，芯片的大部分在任何时候都不能被使用（"暗"）。这一观察促使建筑师们重新审视处理器设计的基本原理，以寻求更高的能源成本性能。

图1.13列出了现代计算机构件的能量成本和面积成本，显示了令人惊讶的大比率。例如，32位浮点加法的能耗是8位整数加法的30倍。面积差异甚至更大，为60倍。然而，最大的差异是在内存方面；32位DRAM访问所需的能量是8位加法的2万倍。一个小型的SRAM比DRAM的能量效率高125倍，这表明谨慎使用缓存和内存缓冲器的重要性。

![图 1.13 Comparison of the energy and die area of arithmetic operations and energy cost of accesses to SRAM and DRAM.
\[Azizi\]\[Dally\]. Area is for TSMC 45 nm technology node.](../../.gitbook/assets/NeatReader-1656054748201.png)

每个任务能量最小化的新设计原则与图1.13中的相对能量和面积成本相结合，激发了计算机体系结构的新方向，我们将在[第七章](../../di-qi-zhang-ling-yu-te-ding-jia-gou-dsa.md)介绍。特定领域的处理器通过减少宽泛的浮点运算和部署特殊用途的存储器以减少对DRAM的访问来节省能量。它们利用这些节省的能量来提供比传统处理器多10-100个（更窄的）整数运算单元。虽然这种处理器只执行有限的任务，但它们执行这些任务的速度明显比通用处理器快，而且更节能。

就像医院里有普通医生和医疗专家一样，在这个能源意识的世界里，计算机很可能是可以执行任何任务的通用内核和能极好地完成少数事情甚至更便宜的特殊用途内核的组合。