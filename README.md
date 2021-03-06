Zicores Trading Post Notifier
=============================

Current release R13: http://notifier.zicore.de/dl/r13/ZicoresTradingPostNotifier.zip

I've finally managed it to structurize my project and made it open source.

To download the latest release visit the trading post notifiers website: [notifier.zicore.de](http://notifier.zicore.de).


Features
========
* Notifications
* Multiple rules for every item
* Current transactions (buying/selling/bought/sold)
* Transaction notifications
* Item search
* Recipe view
* Watchlist
* Item-name filter
* Prices
* Volumes
* Margin
* Gem/Gold exchange calculator
* Gem price notifications
* GW2Spidy.com Dataprovider
* Trading Post Dataprovider
* Timeout notifications


Dataprovider
============

* GW2Spidy.com as Dataprovider

This requests data from gw2spidy developed by Drakie. 
While using this dataprovider, there is no way to track what you're doing.
However the amount of requests is limited, there is no access to transactions and some features only work with the official trading post dataprovider.

* The official Trading Post as Dataprovider

The official Trading Post runs as a website in the Guild Wars 2 client. By knowing that, it's quite easy to replicate the requests and get the data.
To request data, a session key is required, which is requested by the Guild Wars 2 client.
This application scans the memory of Guild Wars 2 to obtain this session key and caches it.
It will use the gathered session key, as long as it's valid. So in best case the memory of GW2 is read only once a few days.
This dataprovider unlocks all features of this application.

* Custom dataprovider

Since my project is open source now, everyone could easily implement their own dataprovider, given the api remains similar.

View Technology
===============

I had a lot troubles with WinForms, to fit things, how i would like to see them.
So i decided to step up and switched to WPF MVVM, and you see what cames out.
I tried to stick to MVVM as far as possible, but it's not possible in every situation.
For example: Saving the column order and column width is a pain. 
You find the ColumnHelper in every code-behind file (if there is a list) to take care of this problem.
So atleast the code remains readable there.

Another Platforms
=================

The data api is mostly view independent. So it's possible to adapt it to mono and develop a gui for mac/linux.
But i'm not the one who will do this.

Charts
======

I like charts, everybody likes charts and you probably already found code hinting to implement charts.
However there are only a few open charting libraries for WPF/Silverlight and i tried then to implement DynamicDataDisplay (D3D).
This library is barely documented,so i didn't make alot progress.

GW2DB
=====

The notifier takes use of gw2db's recipe and item data for the recipe view.

GW2Spidy
========

All items are linking to gw2spidy.com to view the corresponding chart.
(Thank you drakie)
