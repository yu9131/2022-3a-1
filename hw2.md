|任務 |說明 |需時(天)|前置任務|
|:--:|:----|:-----:|:------:|
|1   |研擬計畫|1|-|
|2   |任務分配|4|1|
|3   |取得硬體|17|1|
|4   |程式開發|70|2|
|5   |安裝硬體|10|3|
|6   |程式測試|30|4|
|7   |撰寫使用手冊|25|5|
|8   |轉換檔案|20|5|
|9   |系統測試|25|6|
|10  |使用者訓練|20|7, 8|
|11  |使用者測試|25|9, 10|
---
```mermaid
gantt
    title 甘特圖

    section 研擬計畫
    工作1 :a1, 2022-10-03, 1d
        
    section 任務分配
    工作1 :a2, after a1, 4d
       
    section 取得硬體
    工作1 :a3, after a1, 17d
    
    section 程式開發
    工作1 :a4, after a2, 70d
        
    section 安裝硬體
    工作1 :a5, after a3, 10d
        
    section 程式測試
    工作2 :a6, after a4, 30d
    
    section 撰寫使用手冊
    工作1 :a7, after a5, 25d
    
    section 轉換檔案
    工作1 :a8, after a5, 20d
    
    section 系統測試
    工作1 :a9, after a6, 25d
    
    section 使用者訓練
    工作1 :a10, after a7 a8, 20d
    
    section 使用者測試
    工作1 :a11, after a9 a10, 25d
    
```
---

```graphviz
digraph {
	node[shape=record];
	rankdir="LR";
    no1 [label = "研擬計畫 | 編號:1 | 開始:第1天 | 結束:第1天 | 需時:1天"]
    no2 [label = "任務分配 | 編號:2 | 開始:第2天 | 結束:第5天 | 需時:4天"]
    no3 [label = "取得硬體 | 編號:3 | 開始:第2天 | 結束:第18天 | 需時:17天"]
    {rank=same;no2 no3}
    no1->no2
    no1->no3
    no4 [label = "程式開發 | 編號:4 | 開始:第6天 | 結束:第75天 | 需時:70天"]
    no5 [label = "安裝硬體 | 編號:5 | 開始:第18天 | 結束:第27天 | 需時:10天"]
    {rank=same;no4 no5}
    no2->no4
    no3->no5
    no6 [label = "程式測試 | 編號:6 | 開始:第76天 | 結束:第105天 | 需時:30天"]
    no7 [label = "撰寫使用手冊 | 編號:7 | 開始:第28天 | 結束:第32天 | 需時:5天"]
    no8 [label = "轉換檔案 | 編號:8 | 開始:第28天 | 結束:第32天 | 需時:5天"]
    {rank=same;no6 no7 no8}
    no4->no6
    no5->no7
    no5->no8
    no9 [label = "系統測試 | 編號:9 | 開始:第106天 | 結束:第130天 | 需時:25天"]
    no10 [label = "使用者訓練 | 編號:10 | 開始:第33天 | 結束:第52天 | 需時:20天"]
    {rank=same;no9 no10}
    no6->no9
    no7->no10
    no8->no10
    no11 [label = "使用者測試 | 編號:11 | 開始:第131天 | 結束:第155天 | 需時:25天"]
    no10->no11
}

```

