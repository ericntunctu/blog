---

layout: article
title: (中文) Introducing conformal field theory

---
[conformal field theory](https://en.wikipedia.org/wiki/Conformal_field_theory) (中文又稱作保角場論)是一種近代在高能物理和數學各方面都有重要應用的理論，本文主要是想對這樣的理論做一個粗淺的介紹(盡量用中文)，更多lecture note 關於 conformal field theory 可以在 [arxiv](https://arxiv.org/) 找到。若有任何錯誤或想討論可以告知。
> A conformal field theory (CFT) is a quantum field theory that is invariant under conformal transformations. In two dimensions, there is an infinite-dimensional algebra of local conformal transformations, and conformal field theories can sometimes be exactly solved or classified. Conformal field theory has important applications[1] to condensed matter physics, statistical mechanics, and string theory. Statistical and condensed matter systems are indeed often conformally invariant at their thermodynamic or quantum critical points.

由此可見，CFT一個具有保角對稱的量子場論，這個不同於一般的Loretz場論和標準粒子模型(like [QED](https://en.wikipedia.org/wiki/Quantum_electrodynamics))，這有什麼好處呢?首先就是因為對稱性加強了，所以有更多的計算是可以算的，cft裡的state可以被分類成兩種，一種叫做primary operator，一種叫做descendent operator，primary operator決定了descendent operator，所以在cft裡面，所有的field content就是它具有那些primary operator。以下文章只focus在三維以上的保角場論(因為二為時候的conformal group 是 infinite generator 的 virasoro algebra)。

### Correlation Function
首先要知道場論的目地就是要算correlation function，在一般場論裡面correlation function牽涉到scattering amplitude，這當然很正常，因為一個物理理論，最重要的就是把你能觀察的東西跟理論能夠計算的東西作連結，然後做實驗觀察它，所以一般的場論裡面，首先寫下有哪些field(比方電子，光子，一些夸克等等)再寫下一些interaction，然後開始計算它的correlation function利用費曼圖，需要把所有可能的費曼圖加起來，中間會遇到一些問題(renormalization:重整化)，但原理上就是如此，所以計算上是非常繁瑣的，需要用到大量特殊函數和高維空間的積分等等等。<br>
但保角場論就不一樣啦，由上述的statement，我們知道，只需要計算primary operator的correlation function 即可，而且不用利用費曼圖的技巧，也沒有重整化的問題，correlation function of two point 和 three point 都可以完全被保角對稱fixed住，這當然就非常強，和一般場論明顯不同
我們可用保角變換來確定兩點純量的函數，計算來自 [
Lectures on Conformal Field Theory](https://arxiv.org/abs/1511.04074):
<br>$$<\mathcal{O}_1\left(x_1\right)\mathcal{O}_2\left(x_2\right)>=\left\{
\begin{array}{cc}
	\frac{d}{\left|x_1-x_2\right|{}^{\Delta _1+\Delta _2}} & \Delta _1=\Delta _2 \\
	0 & \Delta _1\neq \Delta _2
\end{array}
\right\}.$$<br>
同理三點純量函數也可以fix住
<br>$$<\mathcal{O}_1\left(x_1\right)\mathcal{O}_2\left(x_2\right)\mathcal{O}_3\left(x_3\right)> =\frac{\lambda _{123}}{\left|x_1-x_2\right|{}^a\left|x_2-x_3\right|{}^b\left|x_1-x_3\right|{}^c}.$$ <br>
Following similar steps, one can show that
$$a=\frac{\left(\Delta _1+\Delta _2-\Delta _3\right)}{2},b=\frac{\left(\Delta _3+\Delta _2-\Delta _1\right)}{2},c=\frac{\left(\Delta _1+\Delta _3-\Delta _2\right)}{2}.$$<br>
重點在於，當我們打算使用在四點的correlation function時候，會發現它沒辦法固定住:
<br>$$<\mathcal{O}_1\left(x_1\right)\mathcal{O}_2\left(x_2\right)\mathcal{O}_3\left(x_3\right)\mathcal{O}_4\left(x_4\right)> =\left(\frac{x_{24}}{x_{14}}\right)^{\Delta _{12}}\left(\frac{x_{14}}{x_{13}}\right)^{\Delta _{12}}\frac{g(u,v)}{x_{12}^{\Delta _1+\Delta _2}x_{34}^{\Delta _3+\Delta _4}}.$$ <br>
此時 $$u=\left(\frac{x_{12}x_{34}}{x_{13}x_{24}}\right)^2,v=\left(\frac{x_{12}x_{34}}{x_{23}x_{14}}\right)^2.$$，$$(u, v)$$ 叫做 conformal cross ratio, 對於具有spin的情況我們需要更有效率的做法，叫做[embedding formalism](https://arxiv.org/abs/1107.3554) 在這裡不多說惹.


### OPE
OPE是一個神奇的物件，如果我們假定OPE是正確的，那麼我們就有了很妙的東西，簡單的說ope 就是當你把兩個field成在一起時候可以把它展開成其他field:<br>
$$
\mathcal{O}_1\left(x_1\right)\mathcal{O}_2\left(x_2\right)=\sum _{\mathcal{O}} \lambda _{12\mathcal{O}}C_{\mathcal{O}}\left(x_{12},\partial _y\right)\mathcal{O}(y)|_{y=0} $$ <br>


### Scalar And Spinning Conformal Blocks
Conformal Blocks 是cft的重點物件之一，後面的conformal bootstrap都要依賴他，計算conformal block 主要是運用以下方法 [Conformal Partial Waves: Further Mathematical Results](https://arxiv.org/abs/1108.6194) using the Casimir differential equation: 使用 OPE expasion, g(u, v) 可以被分解為conformal blocks: <br>$$ 
\left(\sum _{i=4} M_{iAB}\right)<\mathcal{O}_1\left(P_1\right)\mathcal{O}_2\left(P_2\right)\mathcal{O}_3\left(P_3\right)\mathcal{O}_4\left(P_4\right)>=0
$$<br>
$$
\frac{1}{2}M_{AB}M^{AB}\mathcal{O}_i\left(P_i\right)=c_{\Delta ,l}\mathcal{O}_i\left(P_i\right).
$$<br>
$$
c_{\Delta ,l}=\Delta (\Delta -d)+l(l+d-2).
$$<br>
We get
<br>$$
\left(\frac{1}{2}\left(M_{1AB}+M_{2AB}\right){}^2-c_{\Delta ,l}\right)W_{\mathcal{O}_{\Delta, J}}\left(P_i\right)=0.
$$<br>
Dolan and Osborn 計算了 closed form expressions for the conformal blocks of
an arbitrary spin-l primary in d = 2, 4. 奇數維度情況則沒有closed form, 只有積分表達式.




### Conformal Bootstrap
Conformal Bootstrap 可以視為conformal field theory的心臟，我不知道bootstrap要怎麼翻譯，不過也不重要，重要的是Conformal Bootstrap是用來解保角場論，一開始先假定你的CFT的spectrum，有哪些 primary fields，決定它的scaling dimension和representation，然後開始Conformal Bootstrap來檢測是否滿足crossing symmetry，所以我們可以講，一個well defined的CFT 就是自洽的OPE和a set of primary fields.一定承認了這個定義，那這個場論原則上就被全部解出，因為更高點Correlation Function都可以被OPE簡化成四點的，這樣就完整的解出這個場論。 <br>
<img src="/image/cft.png" height="100px;"> <br>

![speaker](/images/cft.png)




### 一些目前研究的狀況和前景
CFT復甦大概是在2008年開始:計算 3d ising model 的臨界點所導出來的，然後大家開始做了4維的Conformal Bootstrap，不只限於4個scalar，也有人在研究三維的fermion和增加了超對稱的cft.<br>
另一個方向是來自1995 Juan Maldacena 的 conjecture called [AdS/CFT correspondence](https://en.wikipedia.org/wiki/AdS/CFT_correspondence)
可以藉由計算Witten Diagram(類似於費曼圖在AdS空間中)來得到對應的CFT的部分資訊。這些類似文章在arxiv都有很多介紹惹。


