{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": []
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "source": [
        "# Python 聚餐費用試算器完整參考解答\n",
        "教師參考版。使用變數、字串處理、數字、布林與基本格式化，依題目規定先計算服務費，再扣折價券。\n",
        "\n",
        "以下三組測試各自包含完整的輸入、整理、計算與輸出，可各自獨立執行。輸出已由 Python 實際執行產生。"
      ],
      "metadata": {
        "id": "BNn4JUXVvfqx"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "# 測試一：原始資料\n",
        "本組人數為 4 人，折價券為 100 元。請執行下方完整儲存格。"
      ],
      "metadata": {
        "id": "e2BTOanAvvzU"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "# 1. 原始資料：保留文字資料，另外建立整理後的變數。\n",
        "event_name = \"  WEEKEND DINNER  \"\n",
        "meal_amount = \" NT$1,200 \"\n",
        "people = \"4\"\n",
        "\n",
        "service_rate = 0.10\n",
        "discount = 100\n",
        "budget_per_person = 300\n",
        "\n",
        "# 2. 整理聚餐名稱。\n",
        "clean_event_name = event_name.strip().lower()\n",
        "\n",
        "# 3. 清理餐費文字，再轉換餐費與人數的型別。\n",
        "clean_meal_text = meal_amount.replace(\"NT$\", \"\").replace(\",\", \"\").replace(\" \", \"\")\n",
        "meal_value = float(clean_meal_text)\n",
        "people_count = int(people)\n",
        "\n",
        "# 4. 先按原始餐費計算服務費，再扣除折價券。\n",
        "service_fee = meal_value * service_rate\n",
        "total_amount = meal_value + service_fee - discount\n",
        "amount_per_person = total_amount / people_count\n",
        "\n",
        "# 5. 比較結果直接保存為 bool。等於預算時不算超過。\n",
        "is_over_budget = amount_per_person > budget_per_person\n",
        "\n",
        "# 6. 輸出時才將金額格式化為兩位小數。\n",
        "print(f\"聚餐名稱：{clean_event_name}\")\n",
        "print(f\"原始餐費：{meal_value:.2f} 元\")\n",
        "print(f\"服務費：{service_fee:.2f} 元\")\n",
        "print(f\"折價券：{discount:.2f} 元\")\n",
        "print(f\"應付總額：{total_amount:.2f} 元\")\n",
        "print(f\"分攤人數：{people_count} 人\")\n",
        "print(f\"每人費用：{amount_per_person:.2f} 元\")\n",
        "print(f\"每人預算：{budget_per_person:.2f} 元\")\n",
        "print(f\"是否超過預算：{is_over_budget}\")"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "BNRMwaVzrjcI",
        "outputId": "bd37e7b6-f8da-4f33-c72d-944dd6e732cf"
      },
      "execution_count": 7,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "聚餐名稱：weekend dinner\n",
            "原始餐費：1200.00 元\n",
            "服務費：120.00 元\n",
            "折價券：100.00 元\n",
            "應付總額：1220.00 元\n",
            "分攤人數：4 人\n",
            "每人費用：305.00 元\n",
            "每人預算：300.00 元\n",
            "是否超過預算：True\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "# 測試二：只將人數改成 5 人\n",
        "本組人數為 5 人，折價券為 100 元。請執行下方完整儲存格。"
      ],
      "metadata": {
        "id": "jva1-GiXv2gH"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "# 1. 原始資料：保留文字資料，另外建立整理後的變數。\n",
        "event_name = \"  WEEKEND DINNER  \"\n",
        "meal_amount = \" NT$1,200 \"\n",
        "people = \"5\"\n",
        "\n",
        "service_rate = 0.10\n",
        "discount = 100\n",
        "budget_per_person = 300\n",
        "\n",
        "# 2. 整理聚餐名稱。\n",
        "clean_event_name = event_name.strip().lower()\n",
        "\n",
        "# 3. 清理餐費文字，再轉換餐費與人數的型別。\n",
        "clean_meal_text = meal_amount.replace(\"NT$\", \"\").replace(\",\", \"\").replace(\" \", \"\")\n",
        "meal_value = float(clean_meal_text)\n",
        "people_count = int(people)\n",
        "\n",
        "# 4. 先按原始餐費計算服務費，再扣除折價券。\n",
        "service_fee = meal_value * service_rate\n",
        "total_amount = meal_value + service_fee - discount\n",
        "amount_per_person = total_amount / people_count\n",
        "\n",
        "# 5. 比較結果直接保存為 bool。等於預算時不算超過。\n",
        "is_over_budget = amount_per_person > budget_per_person\n",
        "\n",
        "# 6. 輸出時才將金額格式化為兩位小數。\n",
        "print(f\"聚餐名稱：{clean_event_name}\")\n",
        "print(f\"原始餐費：{meal_value:.2f} 元\")\n",
        "print(f\"服務費：{service_fee:.2f} 元\")\n",
        "print(f\"折價券：{discount:.2f} 元\")\n",
        "print(f\"應付總額：{total_amount:.2f} 元\")\n",
        "print(f\"分攤人數：{people_count} 人\")\n",
        "print(f\"每人費用：{amount_per_person:.2f} 元\")\n",
        "print(f\"每人預算：{budget_per_person:.2f} 元\")\n",
        "print(f\"是否超過預算：{is_over_budget}\")"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "dHm7rGMXwWls",
        "outputId": "467c0ab2-0e3e-48e0-93b7-4944acac37c6"
      },
      "execution_count": 48,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "聚餐名稱：weekend dinner\n",
            "原始餐費：1200.00 元\n",
            "服務費：120.00 元\n",
            "折價券：100.00 元\n",
            "應付總額：1220.00 元\n",
            "分攤人數：5 人\n",
            "每人費用：244.00 元\n",
            "每人預算：300.00 元\n",
            "是否超過預算：False\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "# 測試三：恢復 4 人，折價券改成 220 元\n",
        "本組人數為 4 人，折價券為 220 元。請執行下方完整儲存格。"
      ],
      "metadata": {
        "id": "Ym-IWiiMwaff"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "# 1. 原始資料：保留文字資料，另外建立整理後的變數。\n",
        "event_name = \"  WEEKEND DINNER  \"\n",
        "meal_amount = \" NT$1,200 \"\n",
        "people = \"4\"\n",
        "\n",
        "service_rate = 0.10\n",
        "discount = 220\n",
        "budget_per_person = 300\n",
        "\n",
        "# 2. 整理聚餐名稱。\n",
        "clean_event_name = event_name.strip().lower()\n",
        "\n",
        "# 3. 清理餐費文字，再轉換餐費與人數的型別。\n",
        "clean_meal_text = meal_amount.replace(\"NT$\", \"\").replace(\",\", \"\").replace(\" \", \"\")\n",
        "meal_value = float(clean_meal_text)\n",
        "people_count = int(people)\n",
        "\n",
        "# 4. 先按原始餐費計算服務費，再扣除折價券。\n",
        "service_fee = meal_value * service_rate\n",
        "total_amount = meal_value + service_fee - discount\n",
        "amount_per_person = total_amount / people_count\n",
        "\n",
        "# 5. 比較結果直接保存為 bool。等於預算時不算超過。\n",
        "is_over_budget = amount_per_person > budget_per_person\n",
        "\n",
        "# 6. 輸出時才將金額格式化為兩位小數。\n",
        "print(f\"聚餐名稱：{clean_event_name}\")\n",
        "print(f\"原始餐費：{meal_value:.2f} 元\")\n",
        "print(f\"服務費：{service_fee:.2f} 元\")\n",
        "print(f\"折價券：{discount:.2f} 元\")\n",
        "print(f\"應付總額：{total_amount:.2f} 元\")\n",
        "print(f\"分攤人數：{people_count} 人\")\n",
        "print(f\"每人費用：{amount_per_person:.2f} 元\")\n",
        "print(f\"每人預算：{budget_per_person:.2f} 元\")\n",
        "print(f\"是否超過預算：{is_over_budget}\")"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "1PRqiPilwd4Z",
        "outputId": "50ada748-1f63-4b6a-e4b7-63a91623a91a"
      },
      "execution_count": 49,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "聚餐名稱：weekend dinner\n",
            "原始餐費：1200.00 元\n",
            "服務費：120.00 元\n",
            "折價券：220.00 元\n",
            "應付總額：1100.00 元\n",
            "分攤人數：4 人\n",
            "每人費用：275.00 元\n",
            "每人預算：300.00 元\n",
            "是否超過預算：False\n"
          ]
        }
      ]
    }
  ]
}
