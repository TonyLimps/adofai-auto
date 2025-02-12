这是一个adofai自动打谱程序

说明：
程序有两个版本，main.py和UI.py，两个都可以用，main.py没有UI,UI.py加了UI,但是我感觉加了UI程序有点不稳，推荐使用main.py
如果使用main.py，同目录下必须有settings.txt，里面有一个字典，三个项:
{"key":string,"muliter":float,"mouse":float}
key这一项是程序输入的按键和启动程序的按键，比如当key这一项为"m"时，在游戏内按下m启动程序，程序会在游戏中输入m键
由于电脑性能等种种原因，程序的休眠时间总会有误差，不可能完全等于理论时间
所以字典有muliter和mouse这两项，用于微调休眠时间
muliter这一项是理论等待时间的倍率，默认为0.995
程序有鼠标微调功能，鼠标在屏幕左侧时休眠时间会减少，越往左减少越多，在屏幕右侧时休眠时间会增加，越往右增加越多
可以简单的理解为，误击量计的箭头会偏向鼠标指针的方向
所以需要一个鼠标灵敏度参数，也就是mouse项来调整鼠标微调的力度，默认为0.0000008
具体的休眠时间计算公式如下：
实际休眠时间 = (理论休眠时间*muliter)+(鼠标指针x坐标-屏幕长度/2)*mouse
默认的参数是我调校过后的，可以根据自己的情况调整，别改太多
调整方法:
如果误击量计总是往左偏，可以将muliter稍微改大一点，向右偏同理
如果鼠标微调的作用不明显，可以调大mouse，如果鼠标影响太大可以改小
读取文件容易报错
遇到问题请积极反馈作者TonyLimps(qq 2415294202)

main.py使用方法：
打开程序，出现"按任意键继续..."后按任意键就可以导入想打的adofai文件
打开冰与火之舞，第一个轨道要按下指定按键(settings.txt里的key项)帮助程序定位
程序起步有点不稳，多试几次
然后程序会开始自动打谱

UI.py使用方法:
使用UI.py不需要settings.txt，程序内有三个输入框对应了字典的三项
先点击屏幕左上角的“导入文件”，导入想打的adofai文件
在"输入按键:"后的输入框里输入想让程序在游戏中输入的按键
休眠时间倍率和鼠标灵敏度对应了settings.txt里的muliter和mouse，可以微调
点击左下角的"开始"
打开冰与火之舞，第一个轨道要按下指定按键(输入框里的按键)帮助程序定位
程序起步有点不稳，多试几次
然后程序会开始自动打谱

如果不想打了，可以把鼠标移动到屏幕左上角，这样可以触发pydirectinput的安全保护，停止程序
