### Cloudgarage Developer's Meetup
* 2018-10-30
* @FoxBoxsnet

---
### $ WHOAMI

<div style="float: left;">
![@FoxBoxsnet](assets\img\icon.png)
</div>

* Id: @FoxBoxsnet
* 職業: くらうどえんじにあー
* 業種: 某データセンター事業者

---

###### DAP(Dev Assist Program)
##### 知ってますか？

+++

# DAP 使ってますか？

* vCPU 1Core, Mem 1G
* 3 インスタンス使えます
* 申し込みはこちらから
  * https://cloudgarage.jp/dap/

![](assets\img\dap.png)

---

### 余談
#### 情報ソースどうしてる？

+++

### 余談
#### 情報ソースどうしてる？

* 障害情報の RSS を登録する
  * https://cloudgarage.jp/maintenance/feed/
* TECH & SUPPORT BLOG
  * https://tech.cloudgarage.jp/feed
* ツイッターで `#CloudGarage` を漁る

+++

### 余談
#### 情報ソースどうしてる？


ツイッターの検索窓にこんな感じで入れるといい感じ
```
"#cloudgarage" OR
"CloudGarage" OR
"cloudgarage" 
-from:CloudGarage_IN 
-to:CloudGarage_IN lang:ja

```

---

### 余談
#### アドベントカレンダー

* 今年もやろうと思う

+++

### 余談
## アドベントカレンダー

* ~~今年もやろうと思う~~


+++

### 余談

#### アドベントカレンダー


![](assets/img/01.png)

+++

### 余談

#### アドベントカレンダー

* ~~今年もやろうと思う~~
* もうすでに登録されてた...<br>(早すぎまるでCloudGarageのストレージによう)
  * https://adventar.org/calendars/2967

---


# 本題

* リリースしてからパフォーマンスどうっすか？
* リリース直後に UnixBentch 取ってるので比べてみる

+++

# レギュレーション

* **BOX3/2GBプラン**
* CPU: 2Core
* MEM: 2GB
* SSD: 100G

+++

### UnixBentch

* 去年、今年、比率を書く

+++

### 結果
#### Dhrystone

| System Benchmarks Index Values | INDEX<br>2017/07/28 | INDEX<br>2018/10/30 | % |
| ------------------------------ | ------------------- | ------------------- |-- |
| Dhrystone 2 using register variables | 2021.0              | 1930.1              | 95.50 |
| Double-Precision Whetstone           | 522.6               | 501.2               | 95.90 |
| Execl Throughput                     | 758.8               | 631.5               | 83.22 |

+++

### 結果
#### File Copy


| System Benchmarks Index Values        | INDEX<br>2017/07/28 | INDEX<br>2018/10/30 | %     |
| ------------------------------------- | ------------------- | ------------------- | ----- |
| File Copy 1024 bufsize 2000 maxblocks | 2009.1              | 1903.0              | 94.71 |
| File Copy 256 bufsize 500 maxblocks   | 1268.3              | 1201.2              | 94.47 |
| File Copy 4096 bufsize 8000 maxblocks | 4239.9              | 3972.5              | 93.69 |

+++

### 結果
#### Pipe & Process

| System Benchmarks Index Values | INDEX<br>2017/07/28 | INDEX<br>2018/10/30 | %     |
| ------------------------------ | ------------------- | ------------------- | ----- |
| Pipe Throughput                | 1127.7              | 1079.0              | 95.68 |
| Pipe-based Context Switching   | 222.5               | 179.7               | 80.76 |
| Process Creation               | 658.0               | 543.1               | 82.53 |

+++

### 結果
#### Shell & System Call


| System Benchmarks Index Values | INDEX<br>2017/07/28 | INDEX<br>2018/10/30 | %     |
| ------------------------------ | ------------------- | ------------------- | ----- |
| Shell Scripts (1 concurrent)   | 2067.7              | 1768.0              | 85.50 |
| Shell Scripts (8 concurrent)   | 2902.2              | 2756.7              | 94.98 |
| System Call Overhead           | 1608.9              | 1606.7              | 99.86 |

+++

### 結果
#### Total

| System Benchmarks Index Values | INDEX<br>2017/07/28 | INDEX<br>2018/10/30 | %     |
| ------------------------------ | ------------------- | ------------------- | ----- |
| System Benchmarks Index Score  | 1244.5              | 1135.1              | 91.20 |

---

### dd テスト

+++

### dd テスト
#### 1-8GB

| count | MB/s<br>2017/07/28 | MB/s<br>2018/10/30 | % |
| ----- | ------------------ | ------------------ |-- |
| 1GiB  | 1,000               | 833               | 83.30 |
| 2GiB  | 988                 | 923               | 93.42 |
| 4GiB  | 1,000               | 868               | 86.80 |
| 8GiB  | 980                 | 874               | 89.18 |

+++

### dd テスト
#### 16-64GB

| count | MB/s<br>2017/07/28 | MB/s<br>2018/10/30 | % |
| ----- | ------------------ | ------------------ |-- |
| 16GiB | 914                | 910                | 99.56 |
| 32GiB | 909                | 885                | 97.35 |
| 64GiB | 973                | 904                | 92.90 |

---

### Total

* パフォーマンスが全然落ちてなくて驚いた。
* やはり Disk 速度はばけもの

| bench | Value<br>2017/07/28 | Value<br>2018/10/30 | % |
| ----- | ------------------- | ------------------- |-- |
| UnixBentch | 1244.5              | 1135.1              | 91.20 |
| dd         | 966.28              | 885.28              | 91.61 |



---



### アドベントカレンダー

* ~~今年もやろうと思う~~
* もうすでに登録されてた...<br>(早すぎまるでCloudGarageのストレージによう)
  * https://adventar.org/calendars/2967



---

End

---
