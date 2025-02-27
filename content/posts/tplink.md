---
author: "Franciszek Łopuszański"
title: "Minecraft server on TP-Link router."
date: "2025-02-27"
cover: 
    image: "images/openwrt"
    alt: "cat"
    relative: false
---

# Why not just use Raspberry pi?

Boring

Expesive 

Undocumented

| Board type | Performace | Entry Difficulty | Documentation | HW Mods | Cost |
|------------|------------|------------------|---------------|---------|------|
| Raspberry pi ex. RPI 5 | Moderate | Low | Good | :white_check_mark: external :warning: internal | High ~ 120USD |
| x86 boards ex. thinkpad x200 | High | Low | Moderate | :x: external :warning: internal | Mid ~ 50USD |
| Old android phones | Moderate | Mid | Non Existant | :x: external :x: internal | Low <20USD |
| TP-Link routers :heart: | Super Low | Mid/High | Low | :warning: external :white_check_mark: internal* | Low <5USD | 

Okay so when it comes to experimenting on electronic harware it is silightly difficult to find something both cheap and understandable. On one hand we have bords like raspberry pi 4 and 5 which offer high performance and are quite easy to modify not due to good documantation but rather great effort of comunity to reverse enginner as much about this hardware as possible for example how to connect full size GPU to x1 PCI-E bus ... bruh. They are great but in the current market they are to expensive to justify any low level modifications as damaging rpi can hurt my wallaet quite a lot ( I have killed PI 3B+ ). On the other hand we can buy old x86 laptops or pc for under 20$. With this solution if we want modern support we need to look for things such as 64bit, UEFI and unlocked BIOS which are common for machines sold after 2010. But there is huge problem when it comes to modyfing such hardware as it would require understanding intel ME or amd PSP reprograming AGESA PCBP and probrably porting coreboot to facilitate easy modifications. Then we have mobile phones but they are extreamly unfriendly to work with as most SOC's from poth qualcom and mediatek except for outliers such as SD845 are compleatly undocumented and do not work without magic binary blobs as well as it is extreamly easy to lose control over the device if we accidently disable UART and display isn't yet functional. 

So what can satisfy our budget, avalibility and ease of modification. For this purpose I love playing around with old TP-Link routers. They are dirt chip as I often buy them locally for 3 USD used and many of them already have some linux support from Open WRT project so we are not left without any docs. In this article I want to show you that such devices can be used for both software and hardware mods and serve as great learning expiience if you know what you are doing ( still much easier than custom coreboot or reverse enginerring of production mode phone ).

