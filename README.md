# NYCU-ICLAB-2024-Spring 修課心得 & 修課指南
>> 我正在緩慢更新中
>> 勘誤＆疑難雜症歡迎聯繫我 kevin861222@gmail.com
## 目錄
1. [摘要](#摘要)
2. [前言](#前言)
3. [資料夾指引](#資料夾指引)
4. [背景](#背景)
5. [主觀聲明](#主觀聲明)
6. [正文](#正文)

## 摘要
##### 該學期資訊
- 課程名稱：積體電路設計實驗 Integrated Circuit Design Laboratory
- 扣除退選全班平均：78.92 分
- 學期初總修課人數：127 人
- 退選人數：38 人
- 調分：約莫 2 分
- 授課語言：英文
>*退選人數是用期末考缺考人數估計*


>*每人調分幅度未必相同，僅供參考*

>*期中期末考無額外加分*

>*部分實驗題目是考古題，造成1de通過率提升，但是RANK更競爭*

##### 個人成績資訊
- 原始分數：87.14
- 等第：A+
- RANK：23 / 127
  
|      | Lab01  | Lab02 | Lab03 | Lab04 | Lab05 | Lab06 |OT |    MIDTERM PROJECT | MID EXAM |
| ------------|:------:|:-----:|:-----:|:-----:|:-----:|:-----:|:--------------:|:-----:|:-------:|
| Rank        |  21|16|NA|22|15|60|NA|53|NA||
| Score       |94.74|95.87|100|93.37|66.08|82.12|50|82.07|76.5|
| Pass Rate (%)  | 89.76 | 85.83 | 75.59 | 74.80 |59.06|77.95|2.36|68.50|75.65*|
| Portion of Score (%)|5|5|5|5|5|5|5|8|8|
-------------------------
|     | Lab07  | Lab08 | Lab09 | Lab10 Bonus | Lab11 | Lab12 | LAB13|   FINAL PROJECT  | FINAL EXAM |
| ------------|:------:|:-----:|:-----:|:-----:|:-----:|:-----:|:--------------:|:-----:|:-------:|
| Rank        |58|3de|1|NA|4|ME_3|NA|3|NA|||
| Score       |97|40|100|100|98.95|99.37|100|99.3|95.5|
| pass rate  |74.80|66.14|66.14|76.38|67.72|68.50|68.50|67.72|80.39*|
| 成績比重 (%)|5|5|5|3|5|5|5|8|8|

>**代表該次段考平均分數*

##### 初始成績分布
![成績分布長條圖](https://github.com/kevin861222/NYCU-ICLAB-2024-Spring/assets/79128379/5b2c2efd-a4c4-408a-b033-87a21f6b766e)

##### 個人成績長條圖
![grade長條圖](https://github.com/kevin861222/NYCU-ICLAB-2024-Spring/assets/79128379/40c8b7ed-87d4-40f6-8a21-9755878a9d02)



## 前言
雖然網路上已經有非常非常多關於這門課程的評價以及心得文，但是我覺得我的身份比較特別，再加上這一路上踩過不少別人沒有遇到的坑，所以打算用不同的角度詮釋一下這門課程的價值，也記錄一下不是天才的我是怎麼活過這學期的，姑且算是一個窺視孔，讓有遠大抱負的學弟妹們可以好好衡量自己是否真的準備好了，以及理性的評估這門課程的價值。

## 資料夾指引
``` bash
+--- ~
|   README.md （心得）
|
+---修課指南
|   |   README.md 
|   |
|   +---最齊全のICLAB準備事項
|   |   |   README.md
|   | 
|   +---Verilog_小知識
|   |   |   README.md    
|   | 
|   +---Verilog_黑魔法
|   |   |   README.md
|   | 
|   +---ICLAB_高分攻略
|   |   |   README.md
|               
\---My_code
    |   README.md
    +---Lab01
    +---Lab02
    .
    .
    .
```


## 背景
##### 在 iclab 之前修過哪些課 / 做了哪些準備
- 電子碩-CA 計算機結構
- 電控碩-VLSI 超大型積體電路設計
- 電子碩-SOC 系統晶片設計 
- 電子碩-DIC 數位積體電路
- 資工科碩-AAML 機器學習晶片架構設計
- 電控碩-AFPGA 進階可程式邏輯系統設計與應用
- HDLbits 全刷完
- 2學期 FPGA 應用相關的大學部專題 
- 張添烜教授數位電路與系統的YT影片

##### 技能樹
- 熟爛 Verilog 
- 略懂 System Verilog 
  -- 整學期會有兩個Lab是用 System Verilog
- 熟爛 Python 
  -- Python 在這門課主要是用來產 pattern 或是爆裂 case 
- 略懂 shell script 
  -- 可以寫腳本加速驗證流程，不用每次都一條一條跑，省超級多時間
- 略懂 Linux 指令
  -- server 很多操作都需要用到這些指令，如果不會這些指令也能通過這門課
  -- Tmux搭配後台運行在 try 02 極限 cycle period 的時候滿有幫助的 (詳見修課指南)

##### 實驗室 / 科系
揭曉開頭所言，我大學不是電機系而是機械系，研究所也不是 ics 實驗室，我只是一個毅力過人的瘋狗，單純覺得數位電路很有挑戰性，再加上源源不絕的興致，秉持著一句富貴險中求，賭上我的愛、勇氣、希望，一路闖關至此，我是真的好累，但我還想往更高的地方前進。

##### 該學期課程
這門課的 Loading 前面都感覺不出來，起初我修了 iclab 以及一門據說很輕鬆的電腦視覺(CV)，但是 Lab5 到期中考、期中 Project 的負擔實在太重，難度一口氣飆升到最高點，Maze routing 讓我差點往生，所以後來把 CV 退掉了。

##### 實驗室負擔
實驗室挺自由，每週有團咪，差不多一個學期我要報告三篇論文，以碩一來說算滿輕鬆了，謝謝天使老闆，讚嘆天使老闆。


## 主觀聲明
>以下是我修完這門課程，出於自身經驗的評價
##### 過譽與否 

這個問題取決於心態，畢竟每年都會有一些題目有些和去年一樣，這些lab是非常好拿分的，但若你能秉持自我訓練的精神，當個苦行僧，自己想架構、算法，不魔改別人的 code ，雖然傻了點不過肯定滿載而歸，在求職面試上都能如魚得水，硬實力和心理素質都能邁向更高層次。

反之，如果每次都無腦看著 best code 的投影片開始刻架構，你能保住髮量和睡眠時間，不過 coding 和設計能力很難跳耀式的提升，你能帶走的就是一些電路觀念還有走完 cell-base 的設計流程，多少有點空虛。

* Lab 1-4 , 7-13 沒參考架構僅看設計tip，
* FP 參考乘法器切多少stage，其餘架構和det算法自己想
* Lab 6 , MP 高度參考前人架構再自己寫一版，收穫大幅下降
* Lab5 傻傻的沒參考歷屆，自己想從頭架構，雖然結果不亮眼，但是學到很多東西也很有成就感，有種不留遺憾的爽，但這個 lab 份量多到會往生，重視生命的學弟妹們建議還是先去看別人的架構

對於參考前人 code 這件事情，我是抱持支持態度的，理解別人的設計也是一種非常重要的軟實力，但是出於時間緊湊，前人的code多半都有註解不夠清楚的問題，再加上很少人會投注時間回頭寫很詳細的README給學弟妹看，能快速吸取的只有一些設計TIP，或是參考 pipeline 切法以及 cycle period ，想要在短時間看懂高人的作品，然後加入自己的想法進一步的優化，更勝於藍，我認為是比較困難的。


##### 燙金的數位ic敲門磚
這門課提供了很好的管道讓非 ics 實驗室的學可以更深入的接觸設計流程，像是 Jasper Gold / innovus 以及真實的 SRAM micro ，18週的課程洗禮也能讓PPA掌控能力大幅提升，加分效果不可忽視。

以求職來說，對於底子好的學生能錦上添花，相信能非常順利找到心儀的工作，反觀血統不純正或是其他系所的學生我認為是必要經歷，因為沒有修過這門課程根本不算真正的瞭解設計晶片，不過目前景氣不存在「修過iclab就能進入XXX公司」的說詞，僅僅只有這門課程的加持是遠遠不夠的，還需要更多歷練才能把這得來不易的敲門磚昇華成入場券。

最後，數位電路工程師本身就是壁壘很高的職位，以我非電子所亦非電機所的背景修完這門課，再加上先前的其他經歷，我也未能肯定自己能因此突破高牆，一些很重視學歷的公司，我連面試機會都拿不到，我也沒有辦法展現我是有實力的學生，但凡事不試試看怎麼知道結果呢，曾經的我很努力，現在的我也還在努力，未來的我也會繼續努力下去，路是自己選的，就算被拒絕了、遇到挫折了也不要輕易放棄，希望螢幕前的你還有所有在這條路追逐夢想的你們都能不忘初衷，念念不忘，必有迴響。


##### 實用性

對於原先底子就很強的學生來說，這門課可能無法進一步的培養你寫 verilog 或是設計硬體的能力，因為再複雜的題目，verilog 的變化性也就那樣，而且這門課程的設計偏向競賽導向，也就是說題目設計以及計算 perf 的公式無法比擬現實遇上的真實問題，很多題目一看就是拿來練手用的，現實中不可能用硬體實現，現實也不會一昧追求 perf 不計 Area 只為了設計出 latency=1 的電路，或是不計 power 瘋狂存取，做出一塊一上電直接燒掉的電路。

但這門課完全可以激起爆發性，要在這麼短的時間內設計出一個 bug-free 的電路，已經很不容易了，還要集成眾多黑魔法才能取得出眾的表現，長時間超頻運轉，思路不斷突破上限，激發出不少潛力，個人非常有感。

再者就是心靈層面的磨練，修課當修心，多跌倒幾次就不怕痛了。

##### 修課的終點
在挑戰 iclab 之前，聽到不少傳聞都說修完這門課就具備工作的能力了，是修課版圖的最後一片拼圖，對於這些說法，我的答案是「大確實」，經過這一學期的洗禮，不論抗壓性或是設計能力都得到了顯著的提升，題目的多樣性也能讓學生接觸到各種層面的問題，一些業界要求的能力(AMBA/CDC/Low power...)在這門課中也都接觸過了，絕對有十足的能力面對職場上的挑戰。

不過修完這門課我感到自己非常渺小，有非常多不足的地方，自己和天才還是有很大一段差距，能進步的空間綽綽有餘，目前所接觸到的知識也只是數位電路中的冰山一角，即便對PPA的掌控游刃有餘，但是對於驗證、以及系統層的設計，都是未曾深入瞭解過的領域。

##### 心境和修為的昇華
這門課可以帶你體會成為大師的三個境界，見自己、見天地、見眾生，講白話一點就是讓你知道自己的不足，從錯誤中學習，和各路高手切磋，激發遇強則強的潛力，隨後悟出門道，成人之美，普渡眾生。


## 正文
##### 帛
我大三的時候，那時候正好是大徵才時代的濫觴，整個校園生意盎然，努力必有收穫是當時的圭臬，看著不少控制組學長姐靠著修課鬼轉硬體工程師進入一線大公司，運氣好一點還能進到超香部門，簡直祖墳裂開冒青煙，即便當時還是機械小菜雞的我，彷彿也能看見不久後的自己成為竹科新貴，只因為自己對寫code滿感興趣，再加上已經有接觸過邏設和FPGA這些基礎課程，於是沒有太多顧慮的開始往數位ic培養技能樹，網路爬文後更是單純的以為iclab將會這場競賽的終點，是我踏入夢想職缺的入場券，只要修過這門課，一線豬屎屋任我挑。

帶著滿懷熱血，還有不怕死的傻勁瘋狂排課，只要有空堂就把它塞進去，不開放初選的課我就直接寫信，知道這樣會很辛苦，但是想著以後年薪夠我吃到鮭魚絕種，再累好像都是值得的。（不過事後有發現自己繞路了，有些課不太相關我也給他修下去）

起初新手村磨練技能的我我沈溺於學習的快樂之中，拿到A+就認定自己離成功更近一步，也越修越有幹勁，但當我開始挑戰碩士班課程，實作的佔比逐漸提升，難度也瞬間飆高，慢慢意識到這條鬼轉之旅遠比我想的困難，Project一出來，資電大神和自己的差距高下立見，被降維打擊到懷疑人生，狠狠地加深骨子裡非純血的自卑感，我曾數度想要放棄這份理想，但我那該死的好勝心還是逼著我前進，我一直覺得我只是選錯科系，但我的天賦不輸那些天之驕子，縱使學的力不從心，但我依舊死撐活撐，逆境中成長。

##### Others

直到有一天，我在二手拍看見一個頭貼很玩咖的男生發了家教文，剛好我也有修那門課，而且我也正在溺水中，於是就鼓起勇氣跑去密他，想說可以找個人來討論，結果發現他也是非資電背景，從那時候開始，我才發現教室裡有非常多Others和我一樣痛苦學習，而且很多還比我更菜，慢慢的我開始敢在班上找路人當隊友，結識來自各方的同學，也發現多數同學都很熱心助人，不會把我視為搶飯碗的敵人，電資的壁壘雖然很高，但是人和人之間的排他性卻是我自己假想出來的，而我也在幫助他人的同時找回那份學習的成就感。

* Others : 就業博覽會的表單上通常只有台清交可以填寫，阿樂是非純血資電的我們對自己的戲稱

##### 滑翔翼
時間來到大四下學期，我提前進入實驗室，那時我懷抱滿腔熱忱，不只排了15學分的碩班課程，還立志要發一篇頂刊，氣宇軒昂的定了一個SLAM硬體加速的題目（現在想想還是覺得很瘋），雖然我老闆聽不太懂我想幹嘛，但還是讓我自己訓練自己，這段時間至碩一上學期，都在一個又一個的 deadline 與看不完的論文中度過，現在回想起來，那段時間我的能力真的是火箭式增長，是少部分和肝指數成正比的時光。

硬體設計方面，在賴瑾教授的SOC收穫滿滿，不只 verilog 能寫能改能通靈，對於架構設計也是充滿各種想法，非常感謝這門課，但對不起我沒有修 ASOC 而是跑去修 iclab ，魚與熊掌不可兼得啊。
而 DIC 這門課則是提前讓我接觸到工作站的使用，以及 01 , 02 , 03 sim。

觀念方面，AAML還有論文給了我非常多的啟發，這些大型電路是怎麼做到不斷超越，每一個設計背後的考量、取捨又是什麼，是付出了什麼作為代價換取更強的效益，當我深入瞭解後，悟出了一個道理，數位電路不存在無中生有，等價交換是不可打破的鐵律。

但除了硬實力與觀念的收穫，我認為人脈才是這時期最大的收穫，因為孤身修課所以認識了一些和我一樣沒有隊友的同學，但這些人多半只是背景不正確所以烙單，實力上大家都強的不要不要，也是在這個期間讓我找到和我一起勇闖 iclab 的隊友。

##### 忘卻神殿
時間來到碩一下，進入魔王關卡準變面臨一場血戰，非常幸運的，我和我所有的隊友都成功加簽，順利組隊，我們有提供資源的人，有提供算法的人，有會寫pattern的人，也有臉皮厚敢幫忙發文的人，根本就是夢幻隊伍，我很認真的參考歷代學長姐的心得文以及修課建議，一步一腳印的快樂學習，前面幾個lab也非常順利的通過1de，拿到不錯的名次，可惜的是離 bestcode 還有好長一段距離，我覺得我已經很捲了，或許就是說明我並非天才的鐵證了吧。

不過我也不是那麼在意排名，分數看起來不錯就知足了，正當我以為這樣的順遂會一直持續下去，Lab5 憑空殺出一到超難的題目，那時第一次著手規模這麼大的電路，光是合成就要跑好久，debug時間指數成長，還不自量力的自己想新架構，打死不抄前人的Github，通宵了一整晚，終於做出可以通過管神 pattern 的第一版，以為是個勵志故事嗎？ 結果遇上 03 violation ，直接 2de ，隨後又通靈了老半天還是找不出問題，非常懊悔非常想死。

這是我生平第一次體會到裡不從心有多絕望，身邊都沒有人遇到 03 error ，只能自己救自己，我的 03 並不是 coding style 不良造成，我花了接近一個下午的時間把所有程式改寫，依舊沒有解掉問題，打開波形發現控制訊號變成 High impedance，但卻不知道怎麼解決，心中有千萬個為什麼是我在吶喊，覺得自己是最不幸的學生，遇上這麼折騰的苦難，最後厚臉皮的跑去問助教，在超讚助教的幫忙下才找出問題，他是我的英雄，到現在還是很感謝他。

* 結果是我 if 條件式少寫一個 in_valid，純粹是 code 寫錯，但至今還是不知道為什麼01沒驗出來，詳細的03解法我有整理在指南裡面，可以參考看看

##### 如履薄冰
經歷了第一次 2de ，我檢討了事發原因：
1. 經驗不足，缺乏穩定性，思想縝密層級趕不上電路規模，寫到後面都不知道自己在寫什麼，開了很多多餘的變數，有些根本沒使用到，或是功能一樣卻開兩套，忘了前面有一樣的可以共用。
2. 時間掌控不佳，花了太多時間探討架構，光是決定開多大的SRAM就猶豫半天，以至於後面遇上貧頸沒有足夠的時間修正。
3. 太過自負，明明題目沒變但是卻不參考前人的程式，硬要自己想算法，最後perf也才RANK15，還不如參考去年 best code 自己寫一版，看到 RANK 1~4 都是用 best code 的架構，有種瞎忙半天自討苦吃的後悟。

大起大落讓我有活著的感覺，不過還是不要太頻繁比較好，畢竟長時間睡眠不足，真的會怕心臟扛不住，於是我把修課策略調整成非常保守的模式，不求高分只求1de通過，不再承擔七折的風險，也避免心靈層面的二重打擊，主打一個俗辣修課大法，放下自尊苟且偷生。

隨後 Lab6 / MP 都用簡單的方法實現，拿了普普通通的名次，雖然壓力小了許多，但總覺得那裡怪怪的，我不確定我到底想要什麼，但我很清楚我不甘願就只有這樣，一直感覺到有什麼東西在作祟，應該是該死的好勝心吧，畢竟每次搞事都是他，這次也優先懷疑是他。

##### 小丑
在做完 Lab7 之後，原本可以悠哉的休息兩天，等待新 lab 的到來，可是我卻打開去年上課的影片，提前開始看起 System verilog ，衝著 Lab8 的截止有兩個禮拜，心裡想著這次應該能捲個 best code ，解鎖人生成就，開了一個共編表單和我的超強隊友們較量彼此的 performance ，為了節省面積，開始鋌而走險，使用不合規的 AXI 降低控制資源，為了降低 cc 數，提前發出 Write request，把面積、CC數、clk period 都壓到不可置信的地步，看似瘋狂，實則走火入魔，隔天一個 1de 01 fail 送你個全套小丑造型。

笑死，直接心態炸裂，我覺得我自己驗了那麼多包 pattern 都有過，一定是助教搞事，沒有多想就先寄信給助教確認，結果才發現是漏驗一條 spec ，因為我直接拿網路上的 pattern 來驗證，也沒有確認他到底驗了什麼沒驗什麼，再加上我狂妄的加上預先發 Write request 的功能，才導致違反這條 spec ，心涼了一半，剩下的一半用來改 2de 還有自我懷疑，因為只是一個小錯誤，修修補補後就能順利通過助教的 pattern 了，簡單驗了 dram laterncy = 1 , 2 , 4 , 16 , 64 的 case 後就 00tar 交出去了。

想著晚上還有飯局，是幾個隊友為了慶祝撐過期中地獄的小慶祝，勉強打起精神，強顏歡笑，但長期熬夜加上我低落的心情，讓我半杯就倒，在酒精的麻醉下，我認清了我是個心力憔悴的男子，沒有逞強的必要，索性進入休眠模式，靠在牆角聽著朋友說笑，一位朋友分享她拿到google的實習，我很是羨慕，在交大這個不缺天才的環境，我這樣的小角色確實滿壓抑的，另一位朋友分享他去旅遊和打工換宿的經驗，我想起我被修課荼毒到毫無品質的生活，或許幾年之後我會是一個毫無樂趣沒有靈魂的空殼也說不定，接著另一位朋友又聊到以前玩得多嗨，接觸過多少形形色色的人，我意識到我兩點一線的生活，以及一灘死水的社交圈，這些應該都是我不再年輕的象徵，最後忘了是誰開啟感情話題，破破爛爛的全是我不知道怎麼面對的問題，那個當下不論用哪種角度哪種眼光哪種定義，我都是一是無成，但也就這樣吧，那天的薯條很好吃，我吃了一大堆，還有一盤很好吃的冷凍水餃，至少我還有吃的興致，這樣的心態夠我活一輩子了。

因為通宵的緣故，從早補眠到晚上，用睡覺硬是從月曆上來跳過一天，晚上吃點東西簡單休息後又去睡覺了，再次睜開眼睛已經是禮拜三的早晨，準備迎接新的 lab ，但迎面而來的是 2de 01 fail，讓我頓時掉入絕望中，飯也吃不下了，這故事告訴我要先吃早餐再看email，還要及時行樂，意外和明天不知道哪一個先來。

我心想我不可能這麼粗心吧？連續 fail 兩次？ 還是我交錯檔案？ 還是助教在搞事？ 匆匆忙忙的跑回去，請兩個朋友一起幫忙驗證，打了好幾次都 pass，當下認定是助教在搞，心中鬆了一口氣，趕快寄信給助教確認，但得到的回應卻是非常完整的波形截圖以及錯誤，才想到會不會是 Dram laterncy 的緣故，調整成 100 後果真 fail 了，或許這就是谷底，是所有的痛楚全都漫漶，還是我的感官以至乾癟，我心中毫無波瀾，平靜的嚇人，帶著毫無語調的口吻和協助我 demo 的朋友用致謝後，拿著筆電回到實驗室的座位上，我已經忘了我是怎麼度過那漫長的一天的，我只記得我望著我空蕩蕩的軀殼，身體逐漸化作塵埃，那是我靈魂的忌日。

我想起一句話，人在劇痛後僅存的感知是麻痺，很可悲但對我而言卻是很有用的防禦機制，我樂觀的相信命定論，我相信這一切的發生終將不可悖逆，認定這也是一種悟道，一種海闊天空，飯還是要吃，日子還是要過。

事後檢討：
1. 太過盲目追求成績，但根本沒意義，現實中也不太可能為了一點點面積而使用不合規的 AXI 協議。
2. 心態不夠沈穩，1de沒過之後就只想著趕快弄出可以動的硬體交一交，逃離負面情緒。
3. 人都有失常的時候，學會尊重生命的低谷。

##### 無敵星星
隔天，大助公佈了 Lab1 ~ Lab9 以及段考所有人的得分還有排名，我算了一下自己的成績，假如剩下的每一個 lab 和考試，我都能拿到100分，外加分享會有1分的bonus，那麼我的總平均將會剛剛好是 90 ，還是有 A+ 的機會。

正常人看到這種局勢，應該早就躺平了，只求安穩修完這門課，但我是瘋子，我沒有忘記我的初衷，打從一開始我就奉行富貴險中求的精神，賭上生命追尋我的理想，如今也一樣，啥都別想，幹就完了。

一顆後追的火種就此點燃，要是我付出了100%的努力還是無法達到，那我就付出200%的努力，我認為這場競賽的敵人已經不是分數，也不是其他同學，而是自我，我能否確保驗證足夠嚴謹，我能想出多好的架構，我能多快實現出來，在截止之前我能優化多少，每當進度往前推移，我不再問其他隊友做到哪裡，而是看我還剩多少時間，問自己是否已經盡力了，只要時間還有力氣，我就繼續燃燒。

這種不在乎成敗的灑脫，讓我能置身事外看清眼前的問題，我的表現比以往都還優異、穩定，而且我也有更好的心態可以幫助其他人，慢慢手把手教學，反正我已經不需要計較成績了，我的排名就是落後很多，我只要把握留在場上的機會，讓自己玩得開心就好，有任何我可以努力的地方一率全力以赴。

##### 等價交換
但是另一方面，這也是一把雙面刃，每當成績出爐，我看見自己又拿到99分，心中不是雀躍而是沈甸甸的壓力，但表我還要繼續努力下去，而我承受壓力的感官也從暫時喪失邁向永久喪失。

就這樣一路來到 Final Project ，這場角逐的賽末點，其實我的身心都已經面臨崩潰邊緣了，我知道我又輕敵了，透支的代價不是只有落髮、胃痛、腹瀉、到和、心悸、食慾不振，最恐怖的是免疫力下降，我在最後一週感冒，頭超級痛，痛到無法專注，無法思考，或許是時候休息一下了，但我還是嬉皮笑臉，貫徹富貴險中求的精神，只因為這是最後一次了，真的很想要很想要徹底的贏一次，很想要證明我活著。

不過最後還是留下的小小的遺憾，因為頭痛的緣故導致 Final Project 進展不如預期，最後迫於時間壓力沒有辦法好好的解 critical path ，我的這份設計還沒有完全發會極限，我預期 cycle period 至少還能再降個 0.6 ns ，最終只有拿到第三名，不過我是真的盡力了，我是最棒的。

結束了這門課程，沒有期待已久的心曠神怡，沒有鬆了一口氣的感覺，我虛度了好多天，彷彿失去重心，很多以前我感興趣的事情，現在都提不起勁，以前最愛的薩爾達傳說解了幾個神廟就不知道要幹嘛，沒有什麼好奇心，熱血的排球少年看沒幾集就覺得劇情呆板，鮭魚也覺得沒有以前好吃，荒野亂鬥也開始在一起勝負，出個門覺得好懶散，認識新的朋友覺得好麻煩，也不想運動，不想和人交談，只想靜靜的放空，沒有物慾，失去了衝動，種種跡象讓我發現我好像失去了最簡單的快樂，那種不用考慮未來，只專致於眼前的快樂，希望一段時間後我能慢慢恢復。


##### 回顧 

「 有人可以對痛苦很有天份，而我並不是這樣的人。這點是不是因為我有一種漠不關心的機制、一種嘲諷的措施，我希望自己更痛苦，好讓這個世界終於變得真實，好去體會一種更尖銳的存在。不過我卻從來不曾處於純粹痛苦的狀態。我希望有一天，我能受痛苦的煎熬，能有所超越。我還未遇到我的故事。」---節錄自 蘇菲．卡爾《極度疼痛》
