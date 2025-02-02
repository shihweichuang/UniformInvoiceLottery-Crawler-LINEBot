# 統一發票中獎查詢機器人

<br>

## 主要功能

使用者在 LINE Bot 中輸入「指定中獎月份」，系統即可回傳「統一發票中獎資訊」。

<br>

## 專案發想

雖然電子統一發票已逐漸普及，但仍有機會拿到紙本發票，需手動對獎。

每次對獎時，都得開啟發票對獎網站、輸入號碼或比對獎號，長期下來既耗時又麻煩。

市面上雖有多款發票兌獎 App，卻需要額外下載，佔據手機容量。

「能否更快速查詢發票是否中獎，且不佔用手機空間？」即為此次專案的發想起點。

<br>

## 解決方案

使用 Python 的爬蟲套件(requests, BeautifulSoup)爬取單頁、多頁的資料，再結合 LINE BOT SDK ，以達到本次專案預期功能。

之所以使用 LINE Bot 作為本次專案介面，是根據 <a href="https://datareportal.com/reports/digital-2023-taiwan?_trms=ac920f3ad09a7a33.1693645815116">DIGITAL 2023: TAIWAN</a> 指出 LINE 為台灣占主導地位的社群媒體平台。

透過該介面能夠接觸到更多的潛在使用者。

此外，LINE Bot 中的呈現方式 (如：Bubble、Carousel) 可以清楚列出文字內容並搭配圖片，有利於使用者進行評估、選擇。

<br>

## 開發過程紀錄

1. 規劃預期效果、使用者介面、整體使用流程

2. 觀察統一發票中獎頁面：需要爬取甚麼資料、所需資料是否橫跨多個頁面

3. 進行爬蟲，取出所有資料

4. 整理爬取下的資料

5. 使用 Python FastAPI 串接 LINE Bot ，嘗試匯出所需內容

6. 確認成功匯出後，打包成函式

7. 問題克服

8. 使用者反饋

9. 後續微調

<br>

## 開發期間遇到的問題

### 1. 爬取資料的時間較長

待補

解決方法：

待補

<br>

## 爬取頁面

### 1. <a href="https://invoice.etax.nat.gov.tw/index.html">財政部稅務入口網-統一發票號碼獎中獎號碼</a>

抓取資訊：獎別、中獎號碼、中獎號碼說明、頒獎期間。

<img src="https://i.imgur.com/t13Cvia.png" alt="" width="556" height="900">


### 2. <a href="https://www.fisc.com.tw/TC/News/Content?CAID=8c3e35f6-30d4-4a87-9c16-da80241c1be1&CTID=4f6dccd9-fccd-4ebb-b2ee-2e925bf4fe0f">財金資訊股份有限公司-統一發票兌獎服務</a>

抓取資訊：統一發票實體通路兌獎據點資訊，如獎別、據點、服務時間。

<img src="https://i.imgur.com/4C4a7vs.png" alt="" width="556" height="750">

## 使用方式

1. 輸入 ---> 統一發票中獎<br>
   回傳 ---> 統一發票中獎
<img src="https://i.imgur.com/c02dztJ.jpeg" alt="Bubble【統一發票中獎】" width="556" height="480">

2. 點擊 ---> 統一發票中獎 - 113年 09 ~ 10 月<br>
   帶入 ---> 統一發票中獎：113年 09 ~ 10 月<br>
   回傳 ---> 統一發票中獎：113年 09 ~ 10 月<br>
<div style="text-align: right;">
   <img src="https://i.imgur.com/EUVgK8P.jpeg" alt="Bubble【統一發票中獎：113年 09 ~ 10 月 中獎號碼】" width="556" height="480">
</div>
