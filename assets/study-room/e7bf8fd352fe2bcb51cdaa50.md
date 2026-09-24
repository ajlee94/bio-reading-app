# ISU112 生物逐題重新分類

本輪僅處理ISU112全部50題。年度收工以完成驗證段落及closeout-manifest.json為準。

## 原始來源與範圍

- 本地題本實為27頁混科：國文1–8、化學9–15、英文16–21；生物學（含生理學）22–27，印刷1–6，共50題。原件、原目錄及舊清單不改。
- 從義守大學[歷屆試題官方頁](https://www.isu.edu.tw/admissions/30?category=7&year=115)的ZIP取得具名112年度35頁PDF，見[source-contract.json](source-contract.json)。下載頁年度及2025-12-12日期不作112試卷日期。
- 官方組合包1–27題本、28答案、29–35釋疑，全35頁與本地三分件逐頁文字及72dpi像素一致。本地候選組合包SHA256與本輪取得的112官方成員完全相同；各分件的位元雜湊分別記錄。
- 答案僅採本地PDF1／官方28最下方第四張生物表；釋疑僅採本地PDF4下方–7／官方32下方–35，排除上方英文45。12題為1、8、11、24、26、33、40、41、42、43、44、46，全部維持原答案，無生物更正。
- 釋疑審議日期2023-04-26，發布日NOT_INDEPENDENTLY_VERIFIED。其餘38題未列本輪取得公告，不宣稱不存在其他未取得公告。

## 逐題證據

[逐題入口](index.html)／[CSV](review.csv)／[完整資料](review.json)／[另存覆核](second-review.json)／[分類疑義解決](issue-resolution.json)／[官方結果欄](biology-clarification-scoped.json)。

全部50題由Codex /root在六張完整原頁中逐題視讀；另開Q32、33、35、40、44、46、50完整裁圖覆看。裁圖包含完整題幹與A–D，保留座標、SHA256及原文字讀回。原題上下標或特殊引號以原圖為準，不以文字抽取冒充視讀。

同一執行者另以教材、年度答案／釋疑與備選分類作非盲覆核，50筆獨立檔案保存；不是第二位外部審查者，也不宣稱全部原圖二次重開。本輪本地Campbell Biology 12e正文使用每題相關段落文字實讀，目錄PDF35–50獨立提取；實看版名PDF4及目錄38、43。印刷頁+49=PDF頁，條目起始頁與實際證據頁分開。

Q6、11、17、19、28、32、47等正文小標不在目錄者不冒造葉節點。Q21以974頁直接載明HPV蛋白疫苗的同章Cancer and Immunity作次目；Q25統計公式、Q43具名檢查點等超出Campbell直接文字部分，由外部來源補足。[17組補充來源](supplemental-sources.json)保存URL、實讀範圍與作者證據紀錄雜湊；未下載全文者不冒稱遠端全文雜湊。

官方採計與科學判斷分開，特別保留Q8少見矽藻、Q11D字面、Q12用語、Q16捲舌模型、Q23調控突變、Q24臨床NGS、Q29轉錄超螺旋、Q32刺絲管成分、Q33分群、Q35 ECM／anoikis、Q40得獎與遺傳物質證據、Q44histidine、Q46內源siRNA、Q50英文與中文名稱等差異。分類待審0不表示官方與科學敘述全部一致。

## 合入與回復

主表為`審查紀錄/biology_chapter_report/question_chapter_classification_manual.csv`。事前650列沒有ISU112，本輪僅新增50列；原年度650列所有欄位、值及列序須一致。

事前備份：`審查紀錄/backups/ISU-112-20260909T184156`，共13個可變檔案；[baseline.json](baseline.json)另封存4829份原source、Answer、已完成年度證據與原工具的雜湊。[master-transaction.json](master-transaction.json)記錄50列的合入及前後雜湊。

驗證會將13份備份複製至`qa/restore-dry-run/`隔離檢查，正式覆寫回復未執行。需要回復時依baseline列出的精確路徑與雜湊操作，須先確認沒有後續任務的變更；不要遞迴刪除來源目錄。

同章最小次目完整保存；章級每題每章去重，次章口徑排除已計主章。資料與排名／趨勢由共用報表工具重建，不重跑已完成年度內容。

## 驗證與接續工具

使用內建Python並加`-X utf8`：

- `tools/integrate_isu112_review.py`：本輪紀錄及限定合入，事前基準不可重建。
- `tools/build_isu112_audit_page.py`與`tools/build_biology_chapter_report.py`：年度入口與總報表。
- `tools/validate_isu112_review.py`、`tools/verify_isu112_additional.py`：資料、目錄、來源、採計及計算驗證。
- 內建Node執行`tools/check_isu112_browser.cjs`：桌面1440×900、手機尺寸390×844及360×800實際Chromium操作；不是實體手機測試。

只重用舊年度工具的呈現與驗證結構；ISU112題文、答案、釋疑、目錄判斷與兩輪紀錄均為本輪建立，不拿替換年號當作證據。

[下一次只處理ISU111的提示詞](next-prompt-ISU111.md)。順序CMU115→106、ISU115→106、TCU115→106。完成本年度即停止，不自動續跑、發布、提交、推送或排程。

## 完成驗證與停止


DONE — ISU112全部50題正式分類，分類待審0。封存時間2026-09-09T19:22:31.499688+08:00（Asia/Taipei）。

- 61個唯一主次目錄的題名、起始頁及父Concept；152頁本輪正文及雜湊驗證通過。
- 主表700列，原650列全欄位及列序一致；4829份原資產、13份事前備份及隔離回復複製演練通過。
- 主章50、額外次章8、合併58；同章最小次目題號8,13,21,24,27,33,48照存。資料、三口徑、全年排名／趨勢及入口同步。
- 桌面1440×900、手機尺寸390×844與360×800實際Chromium操作647項PASS；8張UI截圖逐張實看，無整頁橫向溢出。手機內嵌圖縮小，可由已操作的新分頁連結看原尺寸；實體手機NOT_EXECUTED。
- 12題官方生物結果欄全部維持原答案，無跨頁、無更正；計算與來源界線等補充驗證43項PASS。
- [資料](qa/data-validation.json)／[補充驗證](qa/additional-validation.json)／[操作](qa/browser-validation.json)／[視覺](qa/visual-review.json)／[封存](closeout-manifest.json)。
- 測試伺服器及瀏覽器已結束。下次僅ISU111，須使用者再啟動。本次不自動續跑、發布、提交、推送或排程。
