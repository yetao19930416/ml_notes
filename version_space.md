# 版本空间是怎么算的？

《机器学习》第 1 章的课后习题，第 1 题就是求假设空间。

我看到书中求过一次假设空间，感觉很简单的样子，就是把所有的假设列举出来，删掉一些就完了。

但是在做这个习题的时候，我才发现，自己怎么做，都做不出书上例子的结果。

于是上网搜了一下，感觉很多人都好像是给出了过程，但在重要的细节上跳过了。

直到看见[这篇文章](https://blog.csdn.net/anqijiayou/article/details/79697900)，我模拟了他给出的计算过程，才对计算版本空间有了直观的理解。

---

下面用我自己的理解，来解释这个过程。

颜色分为绿、黑、白、`*`；

根蒂分为蜷、稍、硬、`*`；

敲声分为浊、清、闷、`*`。

加上空集的存在，所以假设空间大小一共为 `4*4*4+1=65`。

具体列举时，用这样的思想：

1. 3个*，1种情况
2. 2个*，9种情况
3. 1个*，27种情况
4. 0个*，27种情况
5. 空集，1种情况

一共`1+9+27+27+1=65`种假设。

65 种假设如下：

编号|颜色|根蒂|敲声
:--:|:--:|:--:|:--:
|1	|*	|*|	*|		
|2	|青绿|	*|	*		
|3	|乌黑|	*|	*		
|4	|浅白|	*|	*		
|5	|*	|蜷缩|	*		
|6	|*	|稍蜷|	*		
|7	|*	|硬挺|	*		
|8	|*	|*	|浊响		
|9	|*	|*	|清脆		
|10	|*	|*	|沉闷		
|11	|*	|蜷缩|	浊响		
|12	|*	|稍蜷|	浊响		
|13	|*	|硬挺|	浊响		
|14	|*	|蜷缩|	清脆		
|15	|*	|稍蜷|	清脆		
|16	|*	|硬挺|	清脆		
|17	|*	|蜷缩|	沉闷		
|18	|*	|稍蜷|	沉闷		
|19	|*	|硬挺|	沉闷		
|20	|青绿|	*|	浊响		
|21	|乌黑|	*|	浊响		
|22	|浅白|	*|	浊响		
|23	|青绿	|*	 |清脆		
|24	|乌黑	|*	 |清脆		
|25	|浅白	|*	 |清脆		
|26	|青绿	|*	 |沉闷		
|27	|乌黑	|*	 |沉闷		
|28	|浅白	|*	 |沉闷		
|29	|青绿	|蜷缩 |	*		
|30	|乌黑	|蜷缩 |	*		
|31	|浅白	|蜷缩 |	*		
|32	|青绿	|稍蜷 |	*		
|33	|乌黑	|稍蜷 |	*		
|34	|浅白	|稍蜷 |	*		
|35	|青绿	|硬挺 |	*		
|36	|乌黑	|硬挺 |	*		
|37	|浅白	|硬挺 |	*		
|38	|青绿	|蜷缩 |	浊响		
|39	|青绿	|蜷缩 |	清脆		
|40	|青绿	|蜷缩 |	沉闷		
|41	|青绿	|稍蜷 |	浊响		
|42	|青绿	|稍蜷 |	清脆		
|43	|青绿	|稍蜷 |	沉闷		
|44	|青绿	|硬挺 |	浊响		
|45	|青绿	|硬挺 |	清脆		
|46	|青绿	|硬挺	|沉闷		
|47	|乌黑	|蜷缩	|浊响		
|48	|乌黑	|蜷缩	|清脆		
|49	|乌黑	|蜷缩	|沉闷		
|50	|乌黑	|稍蜷	|浊响		
|51	|乌黑	|稍蜷	|清脆		
|52	|乌黑	|稍蜷	|沉闷		
|53	|乌黑	|硬挺	|浊响		
|54	|乌黑	|硬挺	|清脆		
|55	|乌黑	|硬挺	|沉闷		
|56	|浅白	|蜷缩	|浊响		
|57	|浅白	|蜷缩	|清脆		
|58	|浅白	|蜷缩	|沉闷		
|59	|浅白	|稍蜷	|浊响		
|60	|浅白	|稍蜷	|清脆		
|61	|浅白	|稍蜷	|沉闷		
|62	|浅白	|硬挺	|浊响		
|63	|浅白	|硬挺	|清脆		
|64	|浅白	|硬挺	|沉闷		
|65	|空集	|	


训练数据集有4条。

编号|色泽|根蒂|敲声|好瓜
--|--|--|--|--
1|青绿|蜷缩|浊响|是
2|乌黑|蜷缩|浊响|是
3|青绿|硬挺|清脆|否
4|乌黑|稍蜷|沉闷|否



步骤：

**1.** 由于存在好瓜，所以删除编号65（空集）

**2.** `1 青绿 蜷缩 浊响 是`，需要删除所有与之不符的假设（编号39到64，即删除0个`*`的假设中不符的假设，编号12到19，编号21到28，编号30到37，即删除1个`*`的假设中不符的假设，删除编号2-3，编号6-7，编号9-10，即删除2个`*`的假设中不符的假设）

目前结果如下：

编号|颜色|根蒂|	敲声
---|----|----|--
|1 |*   | *	 |*
|2 |青绿 |*  |	*
|5 |*   |蜷缩|	*
|8 |*   |*	 |浊响
|11|*   |蜷缩|	浊响
|20|青绿|*	 | 浊响
|29|青绿|蜷缩|	*
|38|青绿|蜷缩|	浊响

**3.** `2 乌黑 蜷缩 浊响 是`，需要删除所有与之不符的假设（编号38，编号20、编号29、编号2）

目前结果如下：

编号|颜色|根蒂|	敲声
---|----|----|--
|1 |*   | *	 |*
|5 |*   |蜷缩|	*
|8 |*   |*	 |浊响
|11|*   |蜷缩|	浊响

**4.** `3 青绿 硬挺 清脆 否`，需要删除所有与之相符的假设（编号1）

目前结果如下：

编号|颜色|根蒂|	敲声
---|----|----|--
|5 |*   |蜷缩|	*
|8 |*   |*	 |浊响
|11|*   |蜷缩|	浊响

**5.** `4 乌黑 稍蜷 沉闷 否`，需要删除所有与之相符的假设（已经无可删除的假设）

由此即得到了书中最后的假设空间。

下面就可以按同样的步骤来做习题 1.1 了。

题目说只包含编号1和4的样例，即

训练数据集有4条。

编号|色泽|根蒂|敲声|好瓜
--|--|--|--|--
1|青绿|蜷缩|浊响|是
4|乌黑|稍蜷|沉闷|否


按步骤来执行：

**1.** 由于有好瓜，所以删除空集的假设。
**2.** 删除不符合编号1的假设。

目前结果如下：

编号| 颜色	|根蒂	|敲声
--|--|--|--
1	|*	  | *	|    *
2	|青绿  |  *|	    *
5	|*	  | 蜷缩|	    *
8	|*	  | *	|    浊响
11|	*	 |  蜷缩|	    浊响
20|	青绿	|*	 |   浊响
29|	青绿	|蜷缩	|*
38|	青绿	|蜷缩	|浊响

**3.** 删除符合编号4的假设。

目前结果如下：

编号| 颜色	|根蒂	|敲声
--|--|--|--
2	|青绿  |  *|	    *
5	|*	  | 蜷缩|	    *
8	|*	  | *	|    浊响
11|	*	 |  蜷缩|	    浊响
20|	青绿	|*	 |   浊响
29|	青绿	|蜷缩	|*
38|	青绿	|蜷缩	|浊响

因此最终的版本空间如下：

![版本空间.png](https://i.loli.net/2019/04/13/5cb201ce27101.png)