---
layout: post
title: "Begin to use sysuthesis template"
date: 2014-03-29 18:02:23
catagories: SVM Introduction preparationForPaper
---

Thanks to [zhibo's sysu thesis template](https://github.com/zhibo/sysuthesis), we can use tex in writing our graduation thesis.  
I used the whole day in setting up the environment and contemplate to write my experience today. My system is Debian 7 of 64bit with gcc version 4.6.3.  

###Install Texlive###
We can download the fresh and the brand new Texlive from [tug.org](https://www.tug.org/texlive/). Then follow the [guide for linux user](https://www.tug.org/texlive/quickinstall.html) to install the lovely but cumbersome Texlive. I chose to install it fully, and the choice took me roughly 2800 packages to download which is around 3.6G.  

###Get the template###
Download the [template from Github](https://github.com/zhibo/sysuthesis), then get into the bachelor/ folder and make. If you don't have ``make``, you should install it by ``$ sudo apt-get install build-essential make``. This will prompt lots of errors. The one I met is the fonts [SIMKAI.TTF] and SIMSUN not found.

###Install the fonts###
Download the fonts that are missed. I download it from ... Oh I did a bad thing in copying them directly from my Windows in ``C:\Windows\Fonts``. I copied all them out (Because I do not wanna bother in selecting the fonts) to ``/usr/share/fonts/winfonts/``. Notice that the ``winfonts/`` folder is not exist originally and you should create one.  
Then we have those fonts in our ``/usr/share/fonts/winfonts``, we should ensure they have the right permission. ``sudo chmod 644 /usr/share/fonts/winfonts/*``. Then update the fonts by ``sudo mkfontscale && sudo mkfontdir && sudo fc-cache -fv``.  
But that was not enough. The fonts were reported to be 'not found'. Actually, the ctex did not have the right name of these fonts in our specific system. Go to 
``/usr/local/texlive/2013/texmf-dist/tex/latex/ctex/fontset/`` and edit ctex-xecjk-winfonts.def. Replace the [SIMKAI.TTF]. The fonts of Kaiti can be seen by ``$fc-list :lang=zh-cn``, for example you will see  
``/usr/share/fonts/winfonts/simkai.ttf: KaiTi,楷体:style=Regular,Normal,obyčejné,Standard,Κανονικά,Normaali,Normál,Normale,Standaard,Normalny,Обычный,Normálne,Navadno,Arrunta``  
Then use the first English word, KaiTi, to replace the [SIMKAI.TTF]. Note that there is more than one place you should replace. Replace all the missing fonts that are reported as 'not found'. Now you can go back to your template folder and ``$ make`` again. Passed!

