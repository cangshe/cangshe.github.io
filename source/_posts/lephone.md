---
title: 关于adb删除手机中内置软件的方法（无root）
date: 2018-09-01 11:42:36
tags: adb
cover: http://cdn.nenu.site/qfl.jpg
---

前些天到货了一个老年机，乐丰v5，安卓6.0系统，因为造型和系统的组合太过奇特，准备买来收藏。cpu估计是mt67xx系列，屏幕分辨率极低，所以打王者还是不成问题的。因为内置桌面操作逻辑感人，附加360全套绑架软件，我心心念念的想要搞定他们，起初是想通过root后直接删除，应该是机型太冷门，所有方法全部失败。于是想起了万能的adb。

它长这样（清除毒瘤之后）：

![](http://cdn.nenu.site/IMG_0059.JPG)

## 具体步骤：

1.连接成功后输入`adb shell`调用安卓指令

2.用`pm list packages | grep ""` 列出所有包名，我的如下：

```
package:com.android.fmradio
package:com.android.providers.telephony
package:com.qiku.logsystem
package:com.mediatek.camera
package:com.android.providers.calendar
package:com.android.providers.media
package:com.tencent.tmgp.sgame
package:com.mediatek.fwk.plugin
package:com.mobiletools.systemhelper
package:com.android.wallpapercropper
package:com.mediatek.schpwronoff
package:com.iflytek.inputmethod.hardk
package:com.android.documentsui
package:com.android.externalstorage
package:com.mediatek.ygps
package:com.android.htmlviewer
package:com.iflytek.speechcloud
package:com.android.quicksearchbox
package:com.android.mms.service
package:com.dx.agent2
package:com.android.providers.downloads
package:com.mediatek.engineermode
package:com.qihoo.browser
package:com.shyz.toutiao
package:com.mediatek.omacp
package:com.android.providers.applications
package:com.android.soundrecorder
package:com.android.defcontainer
package:com.android.providers.downloads.ui
package:com.android.pacprocessor
package:com.tencent.mm
package:cn.etouch.ecalendar.cpa
package:com.android.certinstaller
package:com.android.carrierconfig
package:android
package:com.qiku.advertisement
package:com.android.mms
package:com.android.stk
package:com.android.backupconfirm
package:com.qiku.android.register
package:com.mediatek.security
package:com.android.statementservice
package:com.mediatek.providers.drm
package:com.android.providers.settings
package:com.mediatek.miravision.ui
package:com.android.sharedstoragebackup
package:com.mediatek.batterywarning
package:com.android.printspooler
package:com.mediatek.datatransfer
package:com.android.dreams.basic
package:com.qihoo360.mobilesafe
package:com.android.webview
package:com.android.inputdevices
package:com.mediatek
package:com.qiku.android.launcher2
package:com.example
package:com.android.musicfx
package:com.lephone.nurse
package:com.android.onetimeinitializer
package:com.qiku.android.cloudsync
package:com.mediatek.nlpservice
package:com.android.server.telecom
package:com.android.keychain
package:com.android.dialer
package:com.android.gallery3d
package:com.android.calllogbackup
package:com.android.packageinstaller
package:com.android.cleanprocesstool
package:com.android.remotecore
package:com.svox.pico
package:com.android.proxyhandler
package:com.qiku.configcenter
package:com.vanzo.sos
package:com.android.managedprovisioning
package:com.mediatek.calendarimporter
package:com.mediatek.atci.service
package:com.android.dreams.phototable
package:com.android.remotecare.qiku
package:com.mediatek.thermalmanager
package:com.baidu.BaiduMap
package:com.tianqiwhite
package:com.qiku.android.setupwizard
package:com.mediatek.factorymode
package:com.android.wallpaper.livepicker
package:com.qihoo.appstore
package:com.baidu.map.location
package:com.android.settings
package:com.qiku.speech
package:com.android.calculator2
package:com.mediatek.lbs.em2.ui
package:com.unicom.zworeader.ui
package:com.qiku.android.configcenter
package:com.android.wallpaper
package:com.android.vpndialogs
package:com.android.email
package:com.android.phone
package:com.android.shell
package:com.qiku.android.xtime
package:com.android.providers.userdictionary
package:com.qiku.android.ota
package:com.qiku.android.filebrowser
package:com.android.location.fused
package:com.android.systemui
package:com.android.exchange
package:com.android.bluetoothmidiservice
package:com.mediatek.mtklogger
package:com.android.bluetooth
package:com.android.providers.contacts
package:com.android.captiveportallogin
package:com.vz.commoninfo
```

3.像那种qihoo，qiku，calendar什么的明显是桌面，360和中华万年历，流氓软件，如果想删除的更细一些，可以下载[包名查看](https://www.coolapk.com/apk/com.xcn.baoming)对应删除，删除命令是`pm uninstall -k –- user 0 com.xxx.xxx`