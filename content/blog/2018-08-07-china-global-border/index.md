---
title: 中国及邻国国界问题解决方案
date: 2018-08-07
categories:
    - GMT技巧
authors:
    - 王亮 刘珠妹
slug: china-global-border
---

开放的国界数据一般都是由外国机构提供的。外国人时常恶意地将中国以下领土从中国分裂出去或者划给其他国家：

1. 台澎金马
2. 钓鱼岛、赤尾屿等
3. 南海诸岛
4. 阿克赛钦
5. 藏南
6. 其他与印度及属国不丹交界的部分领土
7. 吉尔吉斯斯坦和俄国已归还给中国的领土
8. ...

为此，我们已经为大家提供了正确的中国国界。但是如果要同时画邻国的国界，则会因为要使用开放数据画因外国边界而和我们的数据发生冲突。
现在我们搜集到了中国即领区的各国国界数据。这让我们能同时正确画中国和邻国国界称为可能。

下载两个数据的交界线数据：

下载正确的中国及领区的各国国界数据：

下载全球国界数据：https://data.biogeo.ucdavis.edu/data/gadm3.6/gadm36_levels_shp.zip

对全球国界数据进行处理：

````bash
unzip gadm36_levels_shp.zip -d gadm36_levels
ogr2ogr -f GMT -nln gadm36_0 gadm36_0 gadm36_0.shp # 之后只需要文件 gadm36_0.gmt
````

绘图代码：

{{< include-code "Chinaglobal.sh" bash >}}

绘图结果如下，其中蓝色边界来自DCW数据，红色边界来自社区数据。

{{< figure src="/blog/china-border-issues/CN-border.png" title="中国国界对比图" >}}

从上图中可以看出，阿克赛钦地区、藏南地区边界均存在明显差异，其他地方也存在微小差异。

在涉及到这些区域时应格外注意。需要提供的是，社区提供的国界数据并不能保证完全
正确，若用户也更为权威的国界数据，欢迎共享。

## 参考

- [“问题地图”清查工作指南](http://www.iap.cas.cn/xwzx/tzgg/201709/P020170911372769133133.pdf)