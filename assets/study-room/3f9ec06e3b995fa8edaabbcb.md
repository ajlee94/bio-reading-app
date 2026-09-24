# CMU111 生物年度覆核

本資料夾只處理 CMU111 Q01–Q50。原圖、官方答案、官方釋疑與科學分析分開保存；每題對照本地 Campbell Biology 12e 真實最小目錄。年度入口為 [index.html](index.html)，全部年度入口為 [report.html](../../biology_chapter_report/report.html)。完成驗證狀態見 qa/ 與 closeout-manifest.json；封存檔產生前不代表已收工。

## 來源及實讀範圍

- 原卷9頁，逐題實看PDF2–9，所有題幹、A–D及圖均納入。Q33、34各保留整個根部題組；Q47、48各保留完整遺傳題組。
- 同年度官方答案4頁，只用生物PDF4。釋疑14頁，只用PDF8下半部–14的13題生物釋疑；PDF8上半部英文及PDF1–7其他科目不套入。Q13原B更正為B或D，其餘49題維持原答案。
- 來源身份、SHA256及副本比對見 source-contract.json；source_pages/保留渲染頁，questions/保留50題完整裁圖，question-manifest.json記錄來源頁、裁切區、文字及雜湊。原PDF不修改。
- 79個實際使用目錄條目以本地文字TOC與PDF35–50精確標題、起始頁核對；正文印刷頁+49=PDF頁。textbook_evidence/是本輪提取的證據頁及聚焦實讀紀錄，不宣稱提取整頁就是整頁視覺精讀。視覺抽核TOC PDF46及正文PDF965、817、1146。
- first-pass.tsv與second-review.tsv分開保存50筆手動判斷；second-review.json為結構化覆核。覆核者皆Codex /root，屬同一執行者非盲證據比較，不是外部第二位審查者。
- supplemental-sources.json記26組原始研究／官方資料、實讀範圍與URL；摘要或搜尋返回文字不冒稱全文已下載。這些補充只供科學查證，不是另一年度的官方答案。

## 欄位與統計

review.json／review.csv含原答案與正式採計、最小主次條目、雙頁碼、主次理由、科學說明及覆核索引。issue-resolution.json逐題記錄備選與解決理由。pending_review=0指目錄分類已由證據確定，並不表示每一句原題或官方釋疑皆科學正確。信心0.98為覆核者分級，非校準正確率。

主分類50次，排除主章後的額外次章13次，主加次63次。所有同章最小次條目保留；章級每題每章去重。主表合入前只有CMU115–112共200題，因此本輪追加CMU111共50題，合入後250題，原200題每個原欄位完整保留。見 master-transaction.json。

主要保留差異：Q1非侵入限定不在原題；Q8 Epo天數；Q9 HBcAg原字；Q10酒精種類；Q13雙答案；Q23抽樣方法界線；Q38原核RNA加工與「轉譯」原字；Q41稍異配研究；Q43調節蛋白不保證恆定表達；Q48釋疑小數位筆誤與完全選汰假設；Q49代表類群推論非分子起源定年；Q50被子植物年代與Rhynie Chert。詳細原文及來源見逐題紀錄，不以分類完成抹除差異。

## 備份與驗證

備份：審查紀錄/backups/CMU-111-20260909T062024，逐檔基準見 baseline.json。原source/、Answer/及CMU115–112年度證據的全部路徑／雜湊均受保護。qa/restore-dry-run僅把備份複製至隔離位置核對，不覆蓋目前主表。正式還原前應確認沒有後續要保留的新工作，依baseline.files的明確清單還原；新增年度證據不需刪除。正式還原未執行。

重建報表用Codex內建Python及UTF-8執行 tools/build_biology_chapter_report.py、tools/build_cmu111_audit_page.py；不重新執行prepare或年度合入。驗證用 tools/validate_cmu111_review.py，及內建Node執行 tools/check_cmu111_browser.cjs、tools/check_cmu111_cold_navigation.cjs。年度腳本綁定本輪基準，不可把舊年度腳本當通用分類器。

qa/data-validation.json驗證50題、主表、答案釋疑、目錄、頁文雜湊、三種統計、全年度排名及趨勢。qa/browser-validation.json記錄真實Chromium在1440×900、390×844、360×800的操作；是手機尺寸及觸控模擬，非實體手機。qa/visual-review.json只記實際開圖範圍。臨時測試伺服器與瀏覽器由工具結束時關閉。

本輪停止於CMU111；下一次僅CMU110，提示詞在 next-prompt-CMU110.md。未自動續跑、發布、提交或推送。
