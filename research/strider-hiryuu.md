# Strider Hiryuu — X68000 Research

Erik & Koyuki

## 研究成果

已實機驗證 V15 永久 System DIM 補丁成功。V15 搭配 V29 RetroArch 金手指，可抵擋一般小怪的部分攻擊，並正常擊敗 Boss、通過關卡。

## V15 永久補丁

三處 CPU 指令位址：

- $03350A
- $033538
- $033632

三處原始 BCS.W 指令均改為 NOP NOP（4E71 4E71）。

V15 已成功寫入 System DIM，並經實機測試。

注意：以上為執行時 CPU 位址，不能直接視為 DIM 檔案偏移。

## V29 獨立金手指

CPU 位址：$0AA365
資料寬度：8-bit
持續鎖定：00

V29 保留為獨立 RetroArch 金手指，不寫入 DIM。

## 實測限制

V15 搭配 V29 時，一般小怪的部分攻擊無法傷害玩家，但 Boss 從上往下的攻擊仍可能命中。這是可正常過關的實用版本，不是已驗證的完全無敵。

## Credits

Erik — 實機測試與驗證
Koyuki (ChatGPT) — 分析與研究紀錄
