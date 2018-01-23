---

layout: article
title: (中文) Introducing conformal field theory

---
[conformal field theory](https://en.wikipedia.org/wiki/Conformal_field_theory) (中文又稱作保角場論)是一種近代在高能物理和數學各方面都有重要應用的理論，本文主要是想對這樣的理論做一個粗淺的介紹(盡量用中文)，更多lecture note 關於 conformal field theory 可以在 [arxiv](https://arxiv.org/) 找到。若有任何錯誤或想討論可以告知。
> A conformal field theory (CFT) is a quantum field theory that is invariant under conformal transformations. In two dimensions, there is an infinite-dimensional algebra of local conformal transformations, and conformal field theories can sometimes be exactly solved or classified. Conformal field theory has important applications[1] to condensed matter physics, statistical mechanics, and string theory. Statistical and condensed matter systems are indeed often conformally invariant at their thermodynamic or quantum critical points.

由此可見，CFT一個具有保角對稱的量子場論，這個不同於一般的Loretz場論和標準粒子模型(like [QED](https://en.wikipedia.org/wiki/Quantum_electrodynamics))，這有什麼好處呢?首先就是因為對稱性加強了，所以有更多的計算是可以算的，cft裡的state可以被分類成兩種，一種叫做primary operator，一種叫做descendent operator，primary operator決定了descendent operator，所以在cft裡面，所有的field content就是它具有那些primary operator。以下文章只focus在三維以上的保角場論。

### Correlation Function
首先要知道場論的目地就是要算correlation function，在一般場論裡面correlation function牽涉到scattering amplitude，這當然很正常，因為一個物理理論，最重要的就是把你能觀察的東西跟理論能夠計算的東西作連結，然後做實驗觀察它，所以一般的場論裡面，首先寫下有哪些field(比方電子，光子，一些夸克等等)再寫下一些interaction，然後開始計算它的correlation function利用費曼圖，需要把所有可能的費曼圖加起來，中間會遇到一些問題(renormalization:重整化)，但原理上就是如此，所以計算上是非常繁瑣的，需要用到大量特殊函數和高維空間的積分等等等。<br>
但保角場論就不一樣啦，由上述的statement，我們知道，只需要計算primary operator的correlation function 即可，而且不用利用費曼圖的技巧，也沒有重整化的問題，correlation function of two point 和 three point 都可以完全被保角對稱fixed住，這當然就非常強，和一般場論明顯不同，重點在於，當我們打算使用在四點的correlation function時候，會發現它沒辦法固定住，似乎我們只能做到這裡?其實不然。
我們可用保角變換來確定兩點函數<br>
$$<\mathcal{O}_1\left(x_1\right)\mathcal{O}_2\left(x_2\right)>=\left\{
\begin{array}{cc}
	\frac{d}{\left|x_1-x_2\right|{}^{\Delta _1+\Delta _2}} & \Delta _1=\Delta _2 \\
	0 & \Delta _1\neq \Delta _2
\end{array}
\right\}.$$ 

同理<br>
$$<\mathcal{O}_1\left(x_1\right)\mathcal{O}_2\left(x_2\right)\mathcal{O}_3\left(x_3\right)> =\frac{\lambda _{123}}{\left|x_1-x_2\right|{}^a\left|x_2-x_3\right|{}^b\left|x_1-x_3\right|{}^c}.$$ <br>
Following similar steps, one can show that
$$a=\frac{\left(\Delta _1+\Delta _2-\Delta _3\right)}{2},b=\frac{\left(\Delta _3+\Delta _2-\Delta _1\right)}{2},c=\frac{\left(\Delta _1+\Delta _3-\Delta _2\right)}{2}.$$

### OPE
OPE是一個神奇的物件，如果我們假定OPE是正確的，那麼我們就有了很妙的東西
$$O_1(X_1)O_2(X_2)=\Sigma C_{12J}O_J(X_3)$$

### Conformal Bootstrap
Conformal Bootstrap 可以視為conformal field theory的心臟，我不知道bootstrap要怎麼翻譯，不過也不重要，重要的是Conformal Bootstrap是用來解保角場論，一開始先假定你的CFT的spectrum，有哪些 primary fields，決定它的scaling dimension和representation，然後開始Conformal Bootstrap來檢測是否滿足crossing symmetry，所以我們可以講，一個well defined的CFT 就是自洽的OPE和a set of primary fields.一定承認了這個定義，那這個場論原則上就被全部解出，因為更高點Correlation Function都可以被OPE簡化成四點的，這樣就完整的解出這個場論。


### 一些目前研究的狀況和前景


