---
layout: post
title:  "Welcome to Jekyll!"
date:   2014-12-16 15:22:35
categories: jekyll update
---

# How to manage your music in Mac OS

> iTune是系统自带的不错的音乐播放器，但其功能的好处更多地在于1）与iCloud融合，歌曲可以自动上传，并同步到同一Apple账号中 
2）拥有‘播客’订阅功能
3）与Apple其它设备无缝连接

但缺点其实也很明显，管理功能其实并不强大。例如，歌曲自动识别&信息标签自动更新等工作，都无法在iTune中完成。这里，我先简单的记录我目前对歌曲标签自动填充更新的软件调查做一个总结。

1）TidyMyMusic，有收费版
2）MusicBrainz Picard，它背后是一个开源的音乐识别库（提供了接口，但需要用户不断贡献知识，如wiki百科一样）。但这个软件在中国社区中并不通用，因此似乎很多中文歌曲识别不太好。不过这个软件最好地方在于开源和免费
3）mp3Rage，收费软件
4）mp3TagMac，免费软件，有收费版本。
5）至于音乐识别，最出名的是SoundHound以及Shazam。强烈推荐后者，在MacOS和iOS上都有，而且表现不错。至于国内的各种播放器，估计对中文歌曲支持最好，只是我不感冒而已，为了一个功能，而装一个庞大的软件，不值得。据说，Shazam对中文支持要比SoundHound好。中国有个音乐雷达，估计也不错，可惜我不太信任。

# APPINN

在[这篇APPINN介绍](http://www.appinn.com/music-files-tagger/)中，提到了六个比较好的音乐识别工具。其中QMP（Quintessential Media Player）播放器是一个不错的选择，我曾今在windows下使用，能够自动批量识别并修改id3tag。其后台是依赖于一个叫[Gracenote](http://www.gracenote.com/)的识别器，而且数据库还是不错的。貌似Winamp可以支持这个插件。

而[MusicBrainz Picard](http://picard.musicbrainz.org/)的数据库没Gracenote强大，但是依赖于注册用户的不断完善，有些类似music的wikipedia一样，因此日后的发展路程来说，可能这个数据库更好一些。既开源，且能支持plugin。

小众曾介绍过 [Mp3tag](http://www.mp3tag.de/en/) 豆瓣标签数据源插件，Mp3tag 是一款非常强大并且简单易用的本地 MP3 音乐的 ID3 信息修改软件，其可以通过网络来获取 MP3 的 ID3 标签数据，而对中文 ID3 信息支持不是很好。Mp3tag 豆瓣标签数据源插件 将豆瓣数据引入 Mp3tag，很好的得到了中文 ID3 信息。