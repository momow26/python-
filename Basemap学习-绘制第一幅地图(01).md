# Basemap学习-绘制第一幅地图(01）

---


* 创建一个最简单的世界地图

---


	# 该2行包括必要的basemap和matplotlib库
	from mpl_toolkits.basemap import Basemap	
	import matplotlib.pyplot as plt
		
	map = Basemap()
	
	map.drawcoastlines()
	
	plt.show()
	plt.savefig('momo.png')

---

1.上面的包括了2个必要的Basemap和matplotlib库。

2.该地图的创建使用了Basemap类，它有很多的选项。地图选择采用等矩形投影，中心的经纬度均为0，如果在没有采用任何的选项。

3.我们就可以画出我们想要的了，在设置好地图之后。在这种情况下，海岸的图层，已经包含在Basemap库种，我们使用drawcoastlines方法绘制地图。

4.最后，通过matplotlib方法，绘制的地图被展示和保存。本示例，plt.show()表示打开窗口来展示结果。plt.savefig()将存储地图为图片格式。

---

![世界地图](https://i.imgur.com/9bAlK70.png)

---

1.改变上面例子中地图的投影很简单，仅需要在Basemap类的构造器中增加投影参数和lat_0、 lon_0即可。

2.即是在新的投影下，绘制的地图依旧很不美观，因此，我们需要给海洋和陆地填充不同颜色，fillcontinents()和drawmapboundary()即可以实现。

---

	from mpl_toolkits.basemap import Basemap
	import matplotlib.pyplot as plt
	
	map = Basemap(projection='ortho', lat_0=0, lon_0=0)
	
	# 填充蓝色的全球
	map.drawmapboundary(fill_color='aqua')
	# 填充陆地颜色
	map.fillcontinents(color='coral', lake_color='aqua')
	map.drawcoastlines()
	plt.show()
	plt.savefig('momo1.png')

---

![海陆世界地图](https://i.imgur.com/9YQuDIP.png)
	
---


	