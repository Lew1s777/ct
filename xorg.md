xev		//test keymap
xmodmap -pke	//show keymap status
xmodmap -pke > [path]	//export the keymap
xmodmap [path]		//import the keymap

xrandr --output eDP --mode 1920x1080		//change resolution

generate xorg.conf
---
Xorg :0 -configure                      //

list avaliable graphics card
---
lspci -nn | grep '\[03'

#➜  ~ sudo vim /sys/class/backlight/amdgpu_bl0/brightness

xset #修改DPMS和屏保设定
xset s off				#禁用屏保清空
xset s 3600 3600			#将清空时间设置到 1 小时
xset -dpms                              #关闭 DPMS
xset s off -dpms			#禁用 DPMS 并阻止屏幕清空
xset dpms force off			#立即关闭屏幕
xset dpms force standby		        #待机界面
xset dpms force suspend		        #休眠界面
sleep 1; xset dpms force off            #shell中关闭屏幕
