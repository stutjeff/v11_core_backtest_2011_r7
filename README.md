# V11-Core 2011 Euro Debt / US Credit Downgrade Shock Backtest R9

這是 V11-Core 的 2011～2012 事件型回測。

測試重點：

- 2011 歐債危機與美國債信降評衝擊後，V11 是否能從 452 切到 514。
- 2011 Q3 / 2012 Q2 全球風險升溫時，是否避免繼續進攻。
- 2012 風險修復後，是否能從 514 回到 452，或在確認後進入 433。

## 回測期間

```text
2011-04-01 ～ 2012-12-31
```

## 執行

```bash
pip install -r requirements.txt
python v11_core_2011_backtest.py
```

## 輸出

```text
output/v11_core_2011_weekly_modes.csv
output/v11_core_2011_switch_log.csv
output/v11_core_2011_summary.md
```

## R9 核心邏輯

- 452：平常作戰 / 中性偏進攻底盤
- 514：危機升溫 / 防守避震
- 433：R 模式確認 / 防守反擊

R9 包含：

- R3 慢熊防守邏輯
- R5 急殺 V 型快速回攻通道
- R9 更嚴格的中型修復通道

這一關用來確認：R9 在 2011～2012 這種「多波段風險衝擊」裡，會不會太慢、太快，或亂切模式。


## R9 新增重點

- 針對 2011 歐債型 / 信用型危機新增 credit-crisis filter。
- 若信用壓力尚未修復，V 型快速通道不能太早 514 → 452。
- 452 → 433 需要更深層修復，避免把歐債危機反覆反彈誤判成正式反攻。
