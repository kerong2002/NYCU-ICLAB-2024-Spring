## single core CPU with domain specific IP
### Performance
- Clock Period : 3.9 ns
- Total Latency : 9166 cycles for 1000 instructions
- RTL Area (03_gate_sim) : 491881.4081  μ𝑚<sup>2 </sup>
- Core Area (06_post_sim) : 703267.488  μ𝑚<sup>2</sup>
- Memory Area :68199.14844 μ𝑚<sup>2</sup>
- Performance : (Total Cycle x Clock Period)<sup>3</sup> x Core area = 4.907 E+21
- Rank : 3 / 127

### 實驗概述
1. 實作帶有特化 IP 的 single core CPU 。
2. 涵蓋驗證以及從 RTL 到 APR 端的設計，須通過 post-sim 驗證。 
3. 特化 IP 為 Determinent 。
4. 指令集如下
   > ADD <br>
   > SUB<br>
   > MULT<br>
   > SET LESS THAN<br>
   > LOAD<br>
   > STORE<br>
   > BRANCH<br>
   > DET<br>


### 實驗評論
1. 再次感謝這門課讓我接觸到這些知識。
2. 驗證是門大學問，CPU 會碰到的問題太多了，要設計出嚴密的 pattern 比想像中花時間，軟體能力在這時候顯現出重要性。

### Tips

1. 不能用任何形式的二維陣列取代/修改 16 個 CPU register，否則會造成合成時重新命名，造成驗證失效。
2. 可以使用 Design hardware，不使用 n-stage multiplier 會造成 critical path ，嚴重影響整體性能。
3. 助教驗證的測資是隨機產生，資料間沒有 Spatial Locality 與 Temporal Locality ，再加上題目規定每執行完 10 筆指令要將 Data 同步到 DRAM ，造成設計 instruction cache 效益會遠大於 data cache，也就是說 Data cache 發生 miss 的機率會非常高，不過我的架構還是將兩者都實現出來。
4. pseudoDRAM 延遲不是固定常數，而是 100 至 1000 cycles ，我的策略是加深 pipeline 來降低 clock period ，因為最耗時的不是運算而是 cache miss 像 DRAM 讀取資料以及 Write back 。
5. Write back 部分我設計了兩個模式，single data write back 以及 burst write back，模式選則取決於 dirty data 數目。
6. Determind 的部分我想出了一個很厲害的算法，可以省下很多面積，也讓控制簡化很多，可以參考我的 excel 。
7. 迫於時間壓力，我未能將我的架構優化到極限，最終只有拿到 RANK3 ，如果未來題目沒有太大的更動，可以嘗試使用我的架構繼續優化，目前 critical path 位於 determind 上的乘法器，可以嘗試使用更多的 stage ，或是在 mux 處多切一層 pipeline ，性能將有所提升。
8. 狀態機非常繁瑣，無法用文字呈現，我平板中的筆記也抽象到凡人無法理解，建議安裝 terosHDL 檢閱我的 code ，這個插件可以很好的顯示出每個狀態間的關係。
9. 想要大幅加速運算可以設計 instruction preload / predecode 。
10. 不建議設計 Out of order ，太過複雜，有些東西單純用硬體解會掉光所有頭髮，遇到 Data Hazards 就用 stall 解決，決勝關鍵是 clock period 以及 DRAM 訪問次數。
11. 我的設計通過的非常嚴謹的測試，經由高達 150 組 DRAM 資料的洗禮，以及人為產生的 corner case ，可以放心的使用我的架構。由於我不是 Pattern 原作者，並不打算公布出來，但可以提供一些驗證想法。
    > a. data cache 和 instruction cache 同時發生 miss <br>
    > b. 遇到往回跳的 branch 指令，並且發生 miss<br>
    > c. write back 和 instuction cache miss 同時發生<br>
    > d. Data miss (Load inst) 但存在 dirty data<br>
    > e. branch loop ，也就是新的 pc 等同舊的 pc ，或是往回跳但 CPU reg 數值未被更動，造成那條 branch 指令永遠成立 (助教說這有可能發生)<br>
    > f. branch 跳出 preload 範圍<br>

### APR

![截圖 2024-09-26 上午8 05 05](https://github.com/user-attachments/assets/1fba8da0-2394-4905-9736-5be39f6ff79c)


![截圖 2024-09-26 上午8 05 17](https://github.com/user-attachments/assets/26a90b92-c60b-4a5e-90d7-b6df262d8e62)





### 其他叮囑
1. 最後一哩路，加油。
