1.創一個新的Twitch帳號，作為機器人使用

2.到 https://twitchtokengenerator.com  
一進去會出現下面這個，選機器人  
![](https://hackmd.io/_uploads/SJhSsuCs3.png)  
然後拉到下面，先點Select All，再點Generate Token!  
![](https://hackmd.io/_uploads/HyVEndCo3.png)  
拉回上面，記下ACCESS TOKEN和CLIENT ID，之後會用到  
![](https://hackmd.io/_uploads/ByXd6_Rsn.png)

3.開始Coding，code都在這→ https://github.com/IBM5100o/TwitchBot  
這是主程式 命名為 app.py，keep_alive是另一個檔案，為了在線上跑用的  
![](https://hackmd.io/_uploads/ryOMxKRsh.png)  
首先把剛才的token和client_id填入，nick就填機器人的帳號  
initial_channels則是你想讓機器人在哪裡運作(機器人必須要有那些頻道的MOD，很重要)  
這樣就完成了，如果把keep_alive去掉，直接在本地端跑就可以運作了，可以先測試看看  
在頻道打 !add 1 2，機器人應該會回1+2=3

4.問題來了，你不可能一直開著電腦跑這個程式吧，所以我們需要把它丟到網路上跑  
這邊我是用 fly.io，使用教學可以看這裡 [fly教學](https://uu9924079.medium.com/fly-io-%E4%BD%BF%E7%94%A8%E5%BF%83%E5%BE%97-%E5%BE%9E%E8%A8%BB%E5%86%8A-%E4%BD%88%E7%BD%B2-nodejs-%E5%B0%88%E6%A1%88%E5%88%B0%E7%B6%B2%E5%9F%9F%E8%A8%AD%E5%AE%9A-2fee3b64fbe6)  
裝好後，把github那包放到一個資料夾，然後在那個資料夾用cmd打fly launch  
要注意的是fly.toml和Procfile這兩個檔案，如果你在fly launch的時候有覆寫到  
請把它們改回我github給的那樣，然後fly deploy機器人就上線了

5.如果怕斷線，可以用 https://uptimerobot.com ，設一個Monitor到fly  
Monitor設定的網址→https://XXX.fly.dev (你的app網址)  
簡單來說就是它會每隔一段時間去ping你的fly，提升穩定性(不用也可)

教學到此結束~  
自己寫機器人的好處是你可以做任何你想做的事  
不過如果你想要的功能沒有那麼複雜，用現有的機器人就好(例如Nightbot)