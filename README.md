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
      "cell_type": "code",
      "execution_count": 1,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "Px1IjI4xIog3",
        "outputId": "320ca58d-9f7a-4293-c983-3959370139c1"
      },
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
      ],
      "source": [
        "# --- 測試一：原始資料（4 人、折價券 100 元）---\n",
        "event_name = \"  WEEKEND DINNER  \"\n",
        "meal_amount = \" NT$1,200 \"\n",
        "people = \"4\"\n",
        "\n",
        "service_rate = 0.10\n",
        "discount = 100\n",
        "budget_per_person = 300\n",
        "\n",
        "# 1. 整理聚餐名稱：去除頭尾空白並轉成小寫\n",
        "clean_event_name = event_name.strip().lower()\n",
        "\n",
        "# 2. 整理餐費並轉成數值；人數轉成整數\n",
        "clean_meal_str = meal_amount.replace(\"NT$\", \"\").replace(\",\", \"\").strip()\n",
        "clean_meal_amount = float(clean_meal_str)\n",
        "num_people = int(people)\n",
        "\n",
        "# 3. 分步計算費用（服務費以原始餐費計算，再扣折價券）\n",
        "service_fee = clean_meal_amount * service_rate\n",
        "total_amount = clean_meal_amount + service_fee - discount\n",
        "cost_per_person = total_amount / num_people\n",
        "\n",
        "# 4. 判斷是否超過每人預算（布林值）\n",
        "is_over_budget = cost_per_person > budget_per_person\n",
        "\n",
        "# 5. 輸出費用摘要（金額顯示到小數點後兩位）\n",
        "print(f\"聚餐名稱：{clean_event_name}\")\n",
        "print(f\"原始餐費：{clean_meal_amount:.2f} 元\")\n",
        "print(f\"服務費：{service_fee:.2f} 元\")\n",
        "print(f\"折價券：{discount:.2f} 元\")\n",
        "print(f\"應付總額：{total_amount:.2f} 元\")\n",
        "print(f\"分攤人數：{num_people} 人\")\n",
        "print(f\"每人費用：{cost_per_person:.2f} 元\")\n",
        "print(f\"每人預算：{budget_per_person:.2f} 元\")\n",
        "print(f\"是否超過預算：{is_over_budget}\")"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "# --- 測試二：人數改為 \"5\"，折價券維持 100 元 ---\n",
        "event_name = \"  WEEKEND DINNER  \"\n",
        "meal_amount = \" NT$1,200 \"\n",
        "people = \"5\"\n",
        "\n",
        "service_rate = 0.10\n",
        "discount = 100\n",
        "budget_per_person = 300\n",
        "\n",
        "# 1. 整理聚餐名稱\n",
        "clean_event_name = event_name.strip().lower()\n",
        "\n",
        "# 2. 整理餐費與人數型別\n",
        "clean_meal_str = meal_amount.replace(\"NT$\", \"\").replace(\",\", \"\").strip()\n",
        "clean_meal_amount = float(clean_meal_str)\n",
        "num_people = int(people)\n",
        "\n",
        "# 3. 分步計算費用\n",
        "service_fee = clean_meal_amount * service_rate\n",
        "total_amount = clean_meal_amount + service_fee - discount\n",
        "cost_per_person = total_amount / num_people\n",
        "\n",
        "# 4. 判斷是否超過每人預算\n",
        "is_over_budget = cost_per_person > budget_per_person\n",
        "\n",
        "# 5. 輸出費用摘要\n",
        "print(f\"聚餐名稱：{clean_event_name}\")\n",
        "print(f\"原始餐費：{clean_meal_amount:.2f} 元\")\n",
        "print(f\"服務費：{service_fee:.2f} 元\")\n",
        "print(f\"折價券：{discount:.2f} 元\")\n",
        "print(f\"應付總額：{total_amount:.2f} 元\")\n",
        "print(f\"分攤人數：{num_people} 人\")\n",
        "print(f\"每人費用：{cost_per_person:.2f} 元\")\n",
        "print(f\"每人預算：{budget_per_person:.2f} 元\")\n",
        "print(f\"是否超過預算：{is_over_budget}\")"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "mJbH4Cu_J3ry",
        "outputId": "bb861d9a-219f-4add-f70e-b9d646efeffd"
      },
      "execution_count": 4,
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
      "cell_type": "code",
      "source": [
        "# --- 測試三：人數恢復為 \"4\"，折價券改為 220 元 ---\n",
        "event_name = \"  WEEKEND DINNER  \"\n",
        "meal_amount = \" NT$1,200 \"\n",
        "people = \"4\"\n",
        "\n",
        "service_rate = 0.10\n",
        "discount = 220\n",
        "budget_per_person = 300\n",
        "\n",
        "# 1. 整理聚餐名稱\n",
        "clean_event_name = event_name.strip().lower()\n",
        "\n",
        "# 2. 整理餐費與人數型別\n",
        "clean_meal_str = meal_amount.replace(\"NT$\", \"\").replace(\",\", \"\").strip()\n",
        "clean_meal_amount = float(clean_meal_str)\n",
        "num_people = int(people)\n",
        "\n",
        "# 3. 分步計算費用\n",
        "service_fee = clean_meal_amount * service_rate\n",
        "total_amount = clean_meal_amount + service_fee - discount\n",
        "cost_per_person = total_amount / num_people\n",
        "\n",
        "# 4. 判斷是否超過每人預算\n",
        "is_over_budget = cost_per_person > budget_per_person\n",
        "\n",
        "# 5. 輸出費用摘要\n",
        "print(f\"聚餐名稱：{clean_event_name}\")\n",
        "print(f\"原始餐費：{clean_meal_amount:.2f} 元\")\n",
        "print(f\"服務費：{service_fee:.2f} 元\")\n",
        "print(f\"折價券：{discount:.2f} 元\")\n",
        "print(f\"應付總額：{total_amount:.2f} 元\")\n",
        "print(f\"分攤人數：{num_people} 人\")\n",
        "print(f\"每人費用：{cost_per_person:.2f} 元\")\n",
        "print(f\"每人預算：{budget_per_person:.2f} 元\")\n",
        "print(f\"是否超過預算：{is_over_budget}\")"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "QRu7Cb4QJ8be",
        "outputId": "dd884b7f-7b3d-4b8e-85e2-154e107b9eaf"
      },
      "execution_count": 6,
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
