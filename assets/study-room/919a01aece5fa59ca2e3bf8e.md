# TCU110 生物年度分類

範圍限本年度 Q01–Q50。主表仍為 `審查紀錄/biology_chapter_report/question_chapter_classification_manual.csv`，新增本年度50筆；原1250筆不改。年度入口為 `index.html`，總入口為 `../../biology_chapter_report/report.html`。

## 證據與限制

- 原題本8頁（含封面）；印刷／PDF2–8為50題。Q2密碼表、Q12神經放電圖完整保留，無跨頁或共享題幹。
- 首輪完整原頁視讀，第二輪重新開啟50張全寬裁圖；覆核者均為Codex /root。另存非盲第二輪紀錄，並非第二位審查者或外部專家驗收。
- 同年答案1頁；混科釋疑3頁，生物只占PDF2–3的11題，其餘科目排除。官方答案與釋疑本輪重新下載，SHA-256與本地文件完全一致；題本官方舊連結轉向HTML，使用原清冊已保存的5138同年鏡像，不冒充重新取得官方題本。
- **Q30原答案表B、釋疑正文稱原D但結果欄寫維持原答案。最終官方採計仍未定。** 主表答案保留兩來源衝突文字，原答案仍B，未自行改答；`review.json`的`final_scoring`為null，`scoring_status`為`UNRESOLVED_OFFICIAL_CONFLICT`。本題可確定分類，故分類待審0與採計衝突分開。
- Q3中英詞、Q26非隨機交配、Q27 PIN2周轉、Q29 ABA運輸、Q43分裂措辭、Q44遺傳密碼、Q46 FT用詞及Q49 A/D範圍歧義均保留在逐題科學說明。
- Campbell Biology 12e及本地文字目錄均存來源hash；23張教材頁像實看（版次1、目錄16、正文6）。188個正文頁新提取作導航與稽核，實讀為各題聚焦段與所列6張正文全頁，不宣稱188頁全部逐字通讀。沒有目錄子條目的16.3、21.1、35.2可直接作最小條目。
- 13組補充來源分別記錄實讀段落、HTTP下載或web摘要讀取範圍；機器驗證頁、HTML轉址與證書錯誤不作有效全文。首次受限網路回應曾被初版抓取腳本覆寫，已補存明確標示的作者回顧紀錄並修正為append，沒有捏造原始receipt。

## 檔案

`source-contract.json`、`question-manifest.json`及`answer-transcription.json`保存來源範圍、原圖區域、hash及答案兩次核對。`first-pass-before-second-review.psv`保存首稿原樣；`second-pass-amendments.json`記錄讀圖後修訂。`decision-notes.psv`與`second-review-notes.psv`為分開撰寫的判斷，再組成`review.json/csv`、`first-pass.tsv`、`second-review.json/tsv`及`issue-resolution.json`。`independent-calculations.json`保存Q2、16、25、50重算。

`statistics.csv`包含主章50、純次章17及主加次67個章級計次；同章最小次目另存，章級每題每章去重。

## 備份與驗證

修改前備份為 `審查紀錄/backups/TCU-110-20260910T150257`，13個可回復檔案及17,557個原有保護資產的hash見`baseline.json`。回復演練只複製到本年度`qa/restore-dry-run/`，不覆蓋工作區。

資料與瀏覽器檢查結果以`qa/data-validation.json`及`qa/browser-validation.json`為準。資料、操作及最終截圖視讀均已通過，TASK_STATE更新為DONE。手機尺寸操作是Chromium viewport實際操作，不等同實體手機測試。

必要時使用Codex內建Python執行 `tools/integrate_tcu110_review.py`、`tools/build_tcu110_audit_page.py`、`tools/validate_tcu110_review.py`，內建Node執行 `tools/check_tcu110_browser.cjs`。整合有主表併發與保留欄位防護；不要重跑 `prepare_tcu110_review.py` 重建基準，也不要執行已完成年度工具。

本輪不發布、提交、推送或自動續跑。下一次只在明確要求後處理TCU109。

## 完成驗證

完成時間：2026-09-10T15:44:25.478088+08:00。正式50／50、分類待審0；主表1,300列，原1,250列全部欄位、值及列序保留，17,557原資產雜湊一致。13檔備份及隔離回復演練PASS，未覆寫正式檔。

36項資料驗證PASS，涵蓋76個最小條目、188頁正文來源、限定合入、來源差異及三種統計。Python與生成JavaScript語法PASS。Chromium於1440×900、390×844、360×800實際操作712項PASS，8張最終截圖逐張視讀PASS。實體手機及第二位外部審查者NOT_EXECUTED。測試瀏覽器與本地伺服器已關閉。

[資料驗證](qa/data-validation.json) · [操作驗證](qa/browser-validation.json) · [截圖視讀](qa/visual-qa.json) · [收尾記錄](closeout.json) · [完整檔案雜湊](artifact-manifest.json) · [下次TCU109完整提示詞](next-prompt.txt)。`tools/closeout_tcu110_review.py`僅記錄本次已驗證的收工狀態，不可重跑覆寫完成紀錄。
