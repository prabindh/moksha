moksha
======

HTML5 Demonstrator for Data Visualisation

All files required for Moksha are provided in the moksha folder. This can be run in any HTML5 compliant browser. There are Webkit specific CSS commands to hide scrollbars, without this the screen will show scrollbars in other browsers.

Dependencies:

Obtain the kernel, rootfs with SGX drivers from below link:

https://gforge.ti.com/gf/download/docmanfileversion/303/6367/16Jan-2013.tar.gz

Install Qt5.0.1 from below link:

https://gforge.ti.com/gf/download/docmanfileversion/308/6426/qt5.0.1_install.tar.gz

Download the moksha files from this git repository into any folder in this rootfs

Run the below on the Uboot command line (Note: Network is needed for this demo as all data is obtained from remote servers):

setenv bootargs 'console=ttyO0,115200n8 root=/dev/mmcblk0p2 mem=128M rootwait ip=dhcp'
setenv bootcmd 'mmc rescan; fatload mmc 0 0x82000000 uImage; bootm 0x82000000'
boot

Use username as "root", password empty

Once logged in, type below on serial console

export QT_QPA_PLATFORM=eglfs
/etc/init.d/335x-demo
echo performance > /sys/devices/system/cpu/cpu0/cpufreq/scaling_governor


./snowshoe_fullscreen file:///<current_path>/moksha/moksha.html

Video snapshot of the Moksha framework running on AM335x EVM is available at,

http://www.youtube.com/watch?v=nztgCone4jI


----
Note: The reference frameworks in the Moksha demo are only used as reference to show the capability of different HTML5 engines, running on AM335x. There is no guarantee on suitability or assurance of capability of these engines.


-prabindh, Mar 2013

