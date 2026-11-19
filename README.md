# Python 聚餐費用試算器完整參考解答

本解答對應「Python 資料型別實作作業：聚餐費用試算器」，使用變數、字串方法、型別轉換、數字運算、布林比較與 f-string。程式採逐步寫法，可直接貼到 Colab 執行，不需要自訂函式或迴圈。

## 一、完整程式

以下是第一組測試的完整程式[cite: 1]。

```python
# 1. 原始資料：保留文字資料，另外建立整理後的變數
event_name = "  WEEKEND DINNER  "
meal_amount = "  NT\$1,280 "
people = "4"

service_rate = 0.10
discount = 100
budget_per_person = 380

# 2. 整理聚餐名稱
clean_event_name = event_name.strip().lower()

# 3. 清理餐費文字，再轉換餐費與人數的型別
clean_meal_text = meal_amount.replace("NT\$", "").replace(",", "").replace(" ", "")
meal_value = float(clean_meal_text)
people_count = int(people)

# 4. 先按原始餐費計算服務費，再扣除折價券
service_fee = meal_value * service_rate
total_amount = meal_value + service_fee - discount
amount_per_person = total_amount / people_count

# 5. 比較結果直接保存為 bool，等於預算時不算超過
is_over_budget = amount_per_person > budget_per_person

# 6. 輸出時才將金額格式化為兩位小數
print(f"聚餐名稱：{clean_event_name}")
print(f"原始餐費：{meal_value:.2f} 元")
print(f"服務費：{service_fee:.2f} 元")
print(f"折價券：{discount:.2f} 元")
print(f"應付總額：{total_amount:.2f} 元")
print(f"分攤人數：{people_count} 人")
print(f"每人費用：{amount_per_person:.2f} 元")
print(f"每人預算：{budget_per_person:.2f} 元")
print(f"是否超過預算：{is_over_budget}")
