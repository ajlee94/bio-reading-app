# ISU113 生物年度分類與證據

本輪只處理ISU113。完整32頁混科題本內，生物學（含生理學）在PDF27–32、印刷1–6，共50題；其餘三科排除。50題完整原頁已逐題視讀，裁圖保留全部題幹與A–D；沒有附圖、跨頁或共用題組。Q14、25、30、36、44、50另開裁圖覆看。

## 入口與紀錄

- [逐題入口](index.html)／[全部年度報表](../../biology_chapter_report/report.html)／[CSV](review.csv)
- [主判讀](review.json)／[另存覆核](second-review.json)／[分類疑義解決](issue-resolution.json)
- [首輪理由](decision-notes.psv)與[第二輪比較](second-review-notes.psv)由本輪逐題撰寫；first-pass.tsv與second-review.tsv各自保存。覆核者為同一Codex /root，非盲證據比較，未宣稱有第二位外部審查者，也未宣稱全部原圖重開兩次。
- [完整題圖座標與雜湊](question-manifest.json)／[視讀紀錄](visual-inspection.json)
- [來源契約](source-contract.json)／[同年釋疑結果欄](biology-clarification-scoped.json)／[獨立計算](calculation-check.json)

## 官方來源及界線

本輪由義守大學[歷屆試題頁](https://www.isu.edu.tw/admissions/30?category=7&year=115)所連[官方ZIP](https://www.isu.edu.tw/storage/files/9crd3xNNj7FiMlpyB92xu98jBE5cQrUWvqPB0ZfK.zip)取得具名113年度成員。頁面選單年度115與試卷年度分開判斷。下載記錄在source/supplemental/ISU113/download-manifest.csv；初次沙盒WinError10013後授權重試成功。

官方113成員38頁：1–32題本、33答案、34–38釋疑。全38頁文字及72dpi像素與本地三份分件相同；本地候選組合包更與官方成員SHA256相同。沒有把兩個不同大小的PDF檔案宣稱雜湊相同。見[逐頁比對](official-combined-comparison.json)。本地原件、原清單及其他年度未改。

答案只用本地PDF1／官方33最下方第四張生物表。生物釋疑只用本地PDF3下方至5／官方36–38，排除PDF3上方英文31；Q4跨3–4、Q30跨4–5，續文完整保存。共Q2、4、7、25、30、33、43七題；Q25原A改A/B，Q30原D改B/C/D，其餘五題維持。其餘43題未列本輪取得公告，不宣稱未取得的其他公告不存在。審議日期2024-04-24，發布日期未獨立查證。

## 教材、最小條目與科學說明

本地Campbell Biology 12e PDF4版名、48目錄已實看；PDF35–50新提取目錄並依左右欄驗證條目完整題名、起始印刷頁及父Concept。正文PDF頁=印刷頁+49，逐題以相關段落文字實讀，不宣稱全部正文整頁視讀。

三個文字目錄差異原樣保留：L0724漏and Ions、L1238漏DNA、L2776 Rhythms與實際Rhythmic Beat不同。正式分類採真實PDF完整題名，source/textbook/Campbell toc.txt不修改。Q18腦區功能在49.2概念正文，目錄沒有更細腦區條目，故以真實Concept49.2為最小可用項；Q43次項同理。正文小標不冒作目錄葉項。

14組[補充來源](supplemental-sources.json)記URL、實讀範圍與作者證據紀錄SHA256。未下載遠端全文的來源不冒稱有檔案雜湊；摘要、檢索段落及整頁已讀範圍均區分。現代技術、Rh、外胚乳、ANT等由原始研究或官方教材補足，不能宣稱本地Campbell有具名毒素或2023得獎事件。

官方採計與科學說明分欄。Q14 RF、自體免疫機制，Q19 EGG／EEG，Q23 QRS去極化／收縮，Q25總通氣4000／肺泡3040，Q30光激發電子與直接間接產物，Q36 Aβ斑塊細胞外，Q43松果體間腦定位，Q44 NO角色，Q48排卵延遲等差異不消除。分類待審0只表示50題分類疑義已查證解決，不表示題文或官方解釋皆無科學概括問題。

## 合入、備份與回復

主表審查紀錄/biology_chapter_report/question_chapter_classification_manual.csv原600列無ISU113，本輪只新增50列，共650。原CMU115–106、ISU115、ISU114的全部原欄位值及列序保持。[交易紀錄](master-transaction.json)詳列新增列及雜湊。

事前備份為審查紀錄/backups/ISU-113-20260909T163427，共13檔；[baseline.json](baseline.json)另存4460份原資產路徑與SHA256。qa/restore-dry-run是隔離回復複製演練，不覆寫正式檔案。若日後明確授權回復，先核對baseline中各備份雜湊、檢查新工作，再依相同相對路徑還原13檔；本輪沒有執行正式覆寫還原。ISU114狀態交接完整保存在事前TASK_STATE.md。

同章最小次條目完整保留，章級主章每題一次，次章排除主章並去重，合併每題每章只計一次。信心0.98為覆核分級而非校準正確機率。

## 工具與驗證

Codex內建Python加-X utf8執行tools/integrate_isu113_review.py及tools/build_isu113_audit_page.py；共用報表生成器tools/build_biology_chapter_report.py原位元保留。準備工具的事前基準不可重建或覆蓋；tools/prepare_isu113_delivery.py僅重用程式架構，本年來源、判讀及驗證均另製，不是把前年度證據換年號。

資料驗證tools/validate_isu113_review.py；官方結果欄與計算、來源界線驗證tools/verify_isu113_additional.py；內建Node執行tools/check_isu113_browser.cjs進行實際Chromium桌面及兩種手機尺寸操作。手機尺寸操作不代表實體手機測試。

## 接續

完成各項檢查後才更新TASK_STATE.md為DONE並封存。下一次只重新分類ISU112：[可貼上提示詞](next-prompt-ISU112.md)。本次不自動續跑、發布、提交、推送或建立排程。

## 完成驗證與停止


DONE — ISU113全部50題正式分類、分類待審0。封存時間2026-09-09T17:09:36.813940+08:00（Asia/Taipei）。

- 62個唯一主次目錄、精確題名／起始頁／父Concept，以及153頁本輪正文來源與雜湊通過驗證。
- 主表650列，原600列全欄位及列序相同；4460份原資產、13份事前備份及隔離回復複製演練通過。
- 主章50、額外次章9、合併59；12題有同章最小次目照存。三口徑及全年排名／趨勢／入口同步。
- 桌面1440×900、手機尺寸390×844及360×800實際Chromium操作632項PASS；8張UI截圖實看，沒有整頁橫向溢出。原圖新分頁原尺寸閲覽與返回已操作；實體手機NOT_EXECUTED。
- 七題釋疑含兩個跨頁續文、兩項更正、計算及來源差異等補充驗證34項PASS。
- [資料](qa/data-validation.json)／[補充驗證](qa/additional-validation.json)／[操作](qa/browser-validation.json)／[視覺](qa/visual-review.json)／[封存](closeout-manifest.json)。
- 測試伺服器與瀏覽器已結束。下次只處理ISU112，須使用者啟動。本次不自動續跑、發布、提交、推送或建立背景工作。
