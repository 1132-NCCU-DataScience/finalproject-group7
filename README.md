[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/HR2Xz9sU)
# [GroupID] 人口流動與多項社經因素對六都房價之影響探討
本專案以台灣六都（台北、新北、桃園、台中、台南、高雄）住宅房價為研究對象，整合政府開放資料中的房價、CPI、利率、年所得、失業率與人口遷移資料，透過 R 語言進行：

- 資料清理與欄位標準化
- 房價與各變數關係之視覺化探索
- 時間序列預測（ARIMA）
- 多元線性與固定效果模型建構
- 共線性與異常偵測分析
- 城市間房價影響力比較（斜率檢定）

---

## 專案目標

- 探討人口流動、利率、CPI、失業率等因素與六都房價之關聯
- 建立多元與進階迴歸模型預測房價變動
- 判斷各城市影響房價的主要變因是否一致
- 尋找房價與變數間的矛盾或異常模式

---

## Contributors
|組員|系級|學號|工作分配|
|-|-|-|-|
|何大南|資科碩二|110753202|團隊中的吉祥物🦒，負責增進團隊氣氛| 
|張小明|資科碩二|xxxxxxxxx|團隊的中流砥柱，一個人打十個|

## Quick start

1. **環境需求：**
   - R 4.x 以上版本
   - 已安裝以下套件（如未安裝請先 `install.packages(...)`）：

     ```r
     tidyverse, readr, lubridate, janitor, purrr,
     forecast, car, lmtest, sandwich, nlme, plm,
     broom, ggcorrplot, ggpubr
     ```

2. **執行分析主程式：**
（須確保該目錄中同時有 六都房價整合表_UTF8.csv 檔案存在）

   ```r
   Rscript code/six_city_analysis.R

## Folder organization and its related description

```
project-root/
├── code/                    # 分析主程式與說明
│   ├── six_city_analysis.R
│   └── README.md
├── data/                   # 原始來源與整合後 CSV
│   ├── 六都房價整合表_UTF8.csv
│   └── SOURCE/             # 各類原始來源（CPI、失業率、交易量等）
├── results/                # 輸出圖表與模型結果
│   └── model_and_EDA/
├── docs/                   # 專案報告與簡報文件
│   ├── 書面分析.pdf
│   ├── 展演海報.pdf
│   └── 期末專案提案.pdf
└── README.md               # 本說明文件
```


### docs
|檔名|說明|
|--|--|
|`期末專案提案.pdf`|初步規劃研究方向，聚焦於人口遷徙對六都房價的影響，並探討房價上漲是否受非人口因素驅動（如炒房），包含資料來源彙整、研究動機與預期成果。|
|`書面分析.pdf`|詳細呈現資料分析流程與模型建構結果，從離群值剔除、共線性檢定、迴歸診斷到 Panel 模型與 GLS 模型的比較，為專案的最終分析報告。|
|`展演海報.pdf`|濃縮視覺化呈現研究成果，包括多元迴歸與固定效果模型摘要、異常城市分析（如臺南與臺北的「脫鉤現象」），並提供政策建議與模型比較結果（Adjusted R², AIC）。|
|`初步分工與排程.pdf`|小組成員早期分工規劃與時程表，協助專案順利推進，分工涵蓋資料處理、模型分析、簡報設計與結果彙整等。|

### data
|檔名|說明|
|--|--|
|`六都房價整合表_UTF8.csv`|主分析資料表（欄位皆清整完畢）|
|`SOURCE/六都房價原始檔/`|各縣市交易紀錄（2013–2024）依地區分類|
|`SOURCE/CPI_各月.csv`|消費者物價指數資料（來自主計處）|
|`SOURCE/利率與房貸資料.csv`|央行提供的各期利率與平均貸款利率資料|
|`SOURCE/各縣市人口流動.csv`|人口淨遷入資料（含時間與地區）|
|`SOURCE/年平均所得與失業率.csv`|主計處社經資料整理表|

> 📌 *`SOURCE/` 資料夾內檔案大多為手動爬取、整合與轉換格式，並在主程式中進行欄位標準化。*

### code
儲存主程式與說明文件，整合資料清理、視覺化、建模與匯出流程。

|檔名|說明|
|--|--|
|`six_city_analysis.R`|主分析程式，依序執行資料前處理、探索性視覺化、模型建構與圖表輸出等任務。|

程式涵蓋：
- 欄位轉換與變數建立
- 城市別與全體趨勢圖（❶–❿）
- 多元線性、固定效果、GLS 與 Panel 模型建構與比較
- 模型診斷圖（殘差圖、VIF 熱圖等）與斜率檢定

### results
* What is your performance?
* Is the improvement significant?

## References
使用套件：

- tidyverse, forecast, lubridate, janitor

- car, lmtest, sandwich, nlme, plm, broom

- ggcorrplot, ggpubr

- 其他資料來源與變數說明請見 data/SOURCE/ 內各檔案、 docs/ 報告內容、code/six_sity_analysis.R 註解。