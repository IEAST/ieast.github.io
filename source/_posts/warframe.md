---
title: warframe linux 玩耍+本地化
date: 2020-07-21 11:19:08
tags: #game # warframe
---

waframe 本身是不支持linux的, 我们可以通过[lutris](https://lutris.net/)来下载并使用wine玩耍。

下载就先不说了 有需要在更新
本地化

因为lutris下载后的默认语言是En，然后本人英语又巨差，目前市面上也没有很好的本地化方法，故写一下咯。

Lutris下载的游戏一般会在Home目录下新建一个Games的文件夹。

于是waframe的路径就是`/home/Games/warframe/drive_c/Program Files/Warframe`

我们打开 `updater.sh `文件拉到最下方


```C
# run warframe internal updater
	"$WINE" cmd /C "$WINPATH" -silent -log:/Preprocessing.log -dx10:1 -dx11:1 -threadedworker:1 -cluster:public -language:zh -applet:/EE/Types/Framework/ContentUpdate
fi


#############################################################
# cache optimization
#############################################################
if [ "$do_cache" = true ] ; then
	echo "*********************"
	echo "Optimizing Cache."
	echo "*********************"
	"$WINE" cmd /C "$WINPATH"  -silent -log:/Preprocessing.log -dx10:1 -dx11:1 -threadedworker:1 -cluster:public -language:zh -applet:/EE/Types/Framework/CacheDefraggerAsync /Tools/CachePlan.txt
fi


#############################################################
# actually start the game
#############################################################
if [ "$start_game" = true ] ; then

	echo "*********************"
	echo "Launching Warframe."
	echo "*********************"

	"$WINE" cmd /C start /b "" "$WINPATH" -log:/Preprocessing.log -dx10:1 -dx11:1 -threadedworker:1 -cluster:public -language:zh
fi
```

直接把三个 `public -language:`后面的参数改成zh就好了。  
前提是你语言有选中文编码。
