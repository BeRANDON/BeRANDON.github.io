---
layout: post
title: "Elements Source Issue in Reports"
subtitle: "To enrich the report writing, specific for online blog writing, multi-media elements are required to embedded in the documents. The elements includes latex formular, images, SVGs, flowchart and so on. One can find different techniques to suport them. With discovery, I will continuelly fullfill this document to find solutions or alternatives for embed elements in reports. "
date: "2016-02-27T17:13:15Z"
author: brandon
category: methodology 
tags: writing 
finished: true
---

# Elements for Report Writing 

## Latex Formular

`Mathjax`: This is an open-sourced excellent js codes that can translate latex formular to html codings. 
`http://atomurl.net/math/`: A website that generates latex figure based on latex formular via the google api. For exmaple, one can uese http://chart.apis.google.com/chart?cht=tx&chl=%20%20%5Cfrac%7Ba%7D%7Bb%7D%20 to present as <img src="http://chart.apis.google.com/chart?cht=tx&chl=%20%20%5Cfrac%7Ba%7D%7Bb%7D%20">.

## Google

![google](https://photos.google.com/share/AF1QipONG7wlD23XDL3Cb1L-nuzye3aIEdq-AdM-pgo2eXH5WlLfIcOluYKujtRsvcY5vQ/photo/AF1QipNDZnouMZ6XxXGy5yEOp7-Mrh51iJ-U0LNeGaxp?key=Rl95bURWSTJBcTJpdUJhNjdra3BSZHdxLXAyVjVn)

## Github As Content Provider

The independent sources provider are multiple. However, github is my favourite one, since I can control versions and provide flexible access. One can stores files in github, and access them through specific links. You can also use `githubusercontent` or a third party access service `rawgit` to access raw files. However, `cdn.rawgit` will store previous files while `rawgit` and `githubusercontent` will load current file. For example, one can use following codes to embed images in blog:

![rawgit](https://cdn.rawgit.com/BeRANDON/Source/master/avatar.jpg)
![rawgit]\(https://cdn.rawgit.com/BeRANDON/Source/master/avatar.jpg)

![rawgit](https://rawgit.com/BeRANDON/Source/master/avatar.jpg)
![rawgit]\(https://rawgit.com/BeRANDON/Source/master/avatar.jpg)
![githubusercontent]\(https://raw.githubusercontent.com/BeRANDON/Source/master/avatar.jpg)

One can find more dicussion from here https://www.zhihu.com/question/19758488.

> 国外大厂商的图床有google 的picasa和雅虎的flickr，不过google有政策问题，雅虎也日薄西山，哎。国内的有七牛云存储，可以做专业的图床服务，是按需付费的，不会有经济上的负担，支持图片过滤，是专注于云存储的公司，camera360就是这家做的。在大批量图片处理上应该不会有问题

> 国外http://img.ly 或 http://cl.ly 等等一大堆做得比较好用，服务也非常稳定，这么多年一直在稳定的运行着 ， 
> 国内之前http://tu.6.cn做得相当不错，可惜后来废了，footbig也允许外链，也挂了，http://51.com也允许外链，后来也不允许了 

Actually, flickr website services are shit. Don't like it.
Photobucket is also shit. Slow and unfriendly. 
For a coder, github is the most friendly way to share. Despite current git service is not so convinient, the github is improving the services.

## SVG 

> One can find more in my blog about 'how to make flowchart in blog writing'.

Basically, SVG refers to some chart that can be recongnizied by html. Visio is the most powerful tool to generate SVGs. However, it is not portable and cross-platforms. **Therefore, I suggest to use LucidChart, yEd, TikZ, flowchart.js & js-sequence-diagrams instead.**

## MindMap

MindMap is a specific element requirement. Some SVG (flowchart) tools also contain the moudels for mindmap. However, I prefer the specific software because of the short-cuts and more beautiful presentation. With shortcut, I can record the mindmap blindly.

### XMind

> XMind provides free version of software across MacOS Windows, Win-portable and Linxu. Moreover, it allows you to upload 'xmind' and publish the file through html iframe. The problem is that published xmind could not be edited anymore.

<iframe src="http://www.xmind.net/embed/nzst" width="750px" height="360px" frameborder="0" scrolling="no"></iframe>

### MindMup

MindMup is website-based online mindmap tool. You can use it directly without registration. You can publish your mindmaps and store them on the public data content diretory which can be accessed by anyone who know the project address. The anonymous user can also get authorized by google drive or github to load or store '.mup' files. For the `gold mup user`, he can own his personal storage space, which has little meaning for me. It can export to freemind, png, pdf and mup. 

However, the presentation file you published is static. You can only edit the project according to the mup project number and publish to another presentation file. This is not convinient when you want to cite a dynamic changing mindmap in your blog writing that may be updated in the furture.

<iframe src="https://atlas.mindmup.com/2016/02/b6617090bef601331f785dad84f55260/data_not_mining/index.html" width="600px" height="360px" frameborder="0" scrolling="no"></iframe>
<iframe src="https://atlas.mindmup.com/2016/02/186dd4b0bfc5013366942967f38fd63c/another_and_store_at_sub_fold/index.html"></iframe>

### LucidChart 

Far away from a completed mindmap software.

### text2mindmap

`Pros`:
- Translate Indented Text to mindmaps. 

`Cons`:
- Cannot publish.
- Cannot control the presentation style.

### MindMeister

`Pros`:
- One can embed the published mindmaps from mindmeister server, while the mindmaps can be updated automatically. 

`Cons`:
- Cannot be sync with dropbox or github. 
- Only the paid user can export to freemind version. 
- Online version has not good shortcut operations.

<iframe width="600" height="400" frameborder="0" src="https://www.mindmeister.com/maps/public_map_shell/659356386/summer-holidays?width=600&height=400&z=auto&presentation=1" scrolling="no">
