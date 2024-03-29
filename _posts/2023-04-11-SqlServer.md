---
title: SqlServer
author: Hubert
date: 2023-04-11
category: SQL
layout: post
---

### 1.时间标准

> 世界上常用的时间标准主要有以下几种：
>
> 1. UTC (协调世界时)：UTC是基于原子钟和地球自转测量而得出的一种时间标准。UTC是一种以秒为单位的时间标准，与格林威治标准时间(GMT) 相同。UTC被广泛用于科学、航空、导航等领域，是国际上通用的时间标准。UTC 的优点是准确性高，但缺点是由于地球自转的不规则性，UTC 与实际太阳时有时会存在误差。
> 2. GMT (格林威治标准时间)：GMT 是以伦敦的格林威治皇家天文台的本地时间作为参考标准的时间标准。GMT 被广泛用于航海、天文等领域，但在其他领域的使用相对较少。GMT 的优点是简单易懂，但缺点是由于地球自转的不规则性，GMT 与实际太阳时有时会存在误差。  
> 3. TAI (国际原子时)：TAI 是一种基于多个原子钟的平均值来确定的时间标准。TAI 的优点是准确性极高，但缺点是由于地球自转的不规则性，TAI 与实际太阳时有时会存在误差。  
> 4. GPS 时间：GPS 时间是由全球卫星导航系统 (GPS) 发送的时间信号确定的时间标准。  
GPS 时间的优点是准确性高，而且在定位、导航等领域具有重要的应用价值，但缺点是由于地球自转的不规则性，GPS 时间与实际太阳时有时会存在误差。  
> 5. 原子钟时间：原子钟时间是基于原子振荡的精密时钟所确定的时间标准。原子钟时间的优点是准确性高，但缺点是需要昂贵的设备和复杂的技术来确保精度。  
> 6. 时间戳（Timestamp）是指一个能够表示某个特定时间的数字，通常是一个整数或浮点数。时间戳通常以某个固定的日期和时间为起点，比如 1970 年 1 月 1 日 00:00:00 UTC，然后用秒数表示当前时间和起点时间之间的时间差。  
> 7. Unix 时间戳 是一个广泛使用的时间戳，它是指从 1970 年 1 月 1 日 00:00:00 UTC 到当前时间的秒数。例如，2023 年 4 月 11 日 10:30:00 UTC 的 Unix 时间戳为 1700297800。  
时间戳常用于记录时间、计算时间差等场景。由于时间戳是一个纯数字，因此在计算机中存储和传输时非常方便。同时，时间戳也是跨平台的，可以在不同的操作系统和编程语言之间共享。

### 2.SQL GMT-Time

~~~ sql
-- 为表添加字段，将默认值设置为当前东八区时间
-- mysql
ALTER TABLE table_name 
ADD gmt_create DATETIME DEFAULT CONVERT_TZ(UTC_TIMESTAMP(), '+00:00', '+08:00') NOT NULL;

-- sql server
-- 480 = 8h × 60min
ALTER TABLE table_name
ADD gmt_create DATETIME2 DEFAULT SWITCHOFFSET(SYSDATETIMEOFFSET(), 480) NOT NULL;
~~~

Windows中时间格式为UTC  
中国 ISO3166 CN 中国标准时间 (UTC+08:00)
