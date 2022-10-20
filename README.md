# kaldi-decoder-code-reading

本仓库主要是用来分享Kaldi的decoder的代码解读，帮助入门的同学理解解码的过程。本仓库不包含代码，只有一些代码解读的pdf的分享，包括SimpleDecoder，FasterDecoder，以及Lattice的版本。

## SimpleDecoder
最基础的解码器，真的非常简单，对应的SimpleDecoder的pdf文件逐步的展开了解码过程中Token的变化，基本上逐行解析了代码和代码中处理的各种情况。

SimpleDecoder知乎链接：https://zhuanlan.zhihu.com/p/572960779

## HashList
HashList是FasterDecoder中使用的比较重要的数据结构，巧妙的用一个HashList存储Token，同时具有简单的内存管理，无需频繁的开辟空间。

HashList的知乎链接：（TODO）

## FasterDecoder
相比于SimpleDecoder，FasterDecoder的优点在于：
* 采用HashList来对Token进行存储，更加快速高效的操作Token；
* 更加聪明的剪枝策略，增加了GetCutoff函数，通过max-token和min-token，自适应变化剪枝的beam

FasterDecoder知乎链接：（TODO）

## LatticeSimpleDecoder
Lattice版本的SimpleDecoder，重点是理解以下两点：
* 搞清楚Token和ForwardLink两个数据结构和相互的关系，参考LatticeSimpleDecoder逐行解析和可视化文件中的简洁模型。只要把这个梳理清楚，理解整个过程就会很简单，不外乎就是一系列指针的操作；
* 参考Kaldi的官方介绍，理解lattice剪枝的算法（https://kaldi-asr.org/doc/lattices.html#lattices_generation）

LatticeSimpleDecoder知乎链接：（TODO）

## LatticeFasterDecoder （TODO）

## Dynamic Decoding （TODO）
