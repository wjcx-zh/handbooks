### feh: linux终端下看图片的好工具
- 普通浏览
	+ ` feh * ` 可以察看当前目录下的所有图片，以及当前子目录里的所有图片

- 播放幻灯片 (-D)
	+ ` feh -D 2 *.jpg`  对所有jpg以幻灯片的方式播放，每两秒放一张
	+ ` feh -FD 2 *.jpg` 以全屏的方式播放幻灯片
	+ ` feh -g 800x600 -D 10.5 /pics` 在一个800x600的窗口里按10.5s每张的速度，查看pics目录下的图片
	+ ` feh --cycle-once -FD 1 *.jpg ` 循环一次后即结束播放
	+ ` feh -S` 排序，可按照 name, filename, width, height, pixels,size, format 七种方式排序
		- ` feh -FD 2 -Sfilename * ` 以文件名访问排序播放幻灯片

- 缩略图功能（-t）
	+ -t 是生成缩略图 -E 是缩略图的高度 -y是缩略图宽度 -W 是拼接后的照片的宽度

	+ eg:对/pictures路径下的所有文件生成缩略图
		-	 `feh -t  -E 128 -y 128 -W 1024 /pictures`  这个功能超赞！
 
	+ 若图片较多屏幕不能全部显示，生成的图片是可以用鼠标托动的

- 生成索引 （-i）
	+ -r 递归所指定目录下所有子目录，-i 是生成索引，-F全屏
	+ eg:递归的方式对/opt/img路径下所有文件生成一个索引
		- `feh -irF  -O index.jpg /opt/img`

	+ 还可以指定字体
		- `feh -irFarial/14 -O index.jpg `.
		- 注: arial/14是表示用14point的arial字体，注意这个参数必须和前边的参数连在一起写

- Montage 蒙太奇模式（-m）
	+ `feh -m -X -y 50 -W 500 -o montage.jpg `.
