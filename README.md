# HW09 兩場活動報名整理器
# 姓名: 林立晴
# 學號: D1420575
# =====================================================

# 固定的兩個活動名稱，以 tuple 保存。
activity_names = ("桌遊體驗", "電影欣賞")
# 用活動名稱查詢每人費用。
unit_fees = {"桌遊體驗": 120, "電影欣賞": 80}

board_title = activity_names[0]
movie_title = activity_names[1]

# -----------------------------------------------------
# 測試一：原始資料
# -----------------------------------------------------
print("=== 測試一 ===")
board_raw_1 = " Amy, Ben, amy, Cora "
movie_raw_1 = " ben, Dora, ERIC, ben "

# 1. 整理資料，建立保留重複的串列
board_list_1 = board_raw_1.replace(" ", "").lower().split(",")
movie_list_1 = movie_raw_1.replace(" ", "").lower().split(",")

# 2. 集合去重與運算
board_set_1 = set(board_list_1)
movie_set_1 = set(movie_list_1)

common_1 = board_set_1 & movie_set_1
all_parts_1 = board_set_1 | movie_set_1
only_board_1 = board_set_1 - movie_set_1
only_movie_1 = movie_set_1 - board_set_1

# 3. 排序與預覽
sorted_board_1 = sorted(list(board_set_1))
sorted_movie_1 = sorted(list(movie_set_1))
sorted_common_1 = sorted(list(common_1))
sorted_all_1 = sorted(list(all_parts_1))
sorted_only_board_1 = sorted(list(only_board_1))
sorted_only_movie_1 = sorted(list(only_movie_1))
preview_notice_1 = sorted_all_1[:2]

# 4. 費用計算與摘要保存
summary_1 = {
    "桌遊人數": len(board_set_1),
    "電影人數": len(movie_set_1),
    "共同人數": len(common_1),
    "總不重複人數": len(all_parts_1),
    "報名人次": len(board_set_1) + len(movie_set_1),
    "桌遊應收": len(board_set_1) * unit_fees[board_title],
    "電影應收": len(movie_set_1) * unit_fees[movie_title],
    "總應收": (len(board_set_1) * unit_fees[board_title]) + (len(movie_set_1) * unit_fees[movie_title])
}

# 5. 輸出測試一結果
print(f"活動：{board_title}，每人 {unit_fees[board_title]:.2f} 元")
print(f"活動：{movie_title}，每人 {unit_fees[movie_title]:.2f} 元")
print(f"桌遊整理串列：{board_list_1}")
print(f"電影整理串列：{movie_list_1}")
print(f"桌遊去重名單：{sorted_board_1}")
print(f"電影去重名單：{sorted_movie_1}")
print(f"桌遊人數：{summary_1['桌遊人數']} 人")
print(f"電影人數：{summary_1['電影人數']} 人")
print(f"共同參加者：{sorted_common_1}")
print(f"共同人數：{summary_1['共同人數']} 人")
print(f"只參加桌遊者：{sorted_only_board_1}")
print(f"只參加電影者：{sorted_only_movie_1}")
print(f"全部參加者：{sorted_all_1}")
print(f"總不重複人數：{summary_1['總不重複人數']} 人")
print(f"報名人次：{summary_1['報名人次']} 人次")
print(f"通知名單前兩位：{preview_notice_1}")
print(f"桌遊應收：{summary_1['桌遊應收']:.2f} 元")
print(f"電影應收：{summary_1['電影應收']:.2f} 元")
print(f"總應收：{summary_1['總應收']:.2f} 元\n")


# -----------------------------------------------------
# 測試二：新增一位電影參加者
# -----------------------------------------------------
print("=== 測試二 ===")
board_raw_2 = " Amy, Ben, amy, Cora "
movie_raw_2 = " ben, Dora, ERIC, ben, Frank "

board_list_2 = board_raw_2.replace(" ", "").lower().split(",")
movie_list_2 = movie_raw_2.replace(" ", "").lower().split(",")

board_set_2 = set(board_list_2)
movie_set_2 = set(movie_list_2)

common_2 = board_set_2 & movie_set_2
all_parts_2 = board_set_2 | movie_set_2
only_board_2 = board_set_2 - movie_set_2
only_movie_2 = movie_set_2 - board_set_2

sorted_board_2 = sorted(list(board_set_2))
sorted_movie_2 = sorted(list(movie_set_2))
sorted_common_2 = sorted(list(common_2))
sorted_all_2 = sorted(list(all_parts_2))
sorted_only_board_2 = sorted(list(only_board_2))
sorted_only_movie_2 = sorted(list(only_movie_2))
preview_notice_2 = sorted_all_2[:2]

summary_2 = {
    "桌遊人數": len(board_set_2),
    "電影人數": len(movie_set_2),
    "共同人數": len(common_2),
    "總不重複人數": len(all_parts_2),
    "報名人次": len(board_set_2) + len(movie_set_2),
    "桌遊應收": len(board_set_2) * unit_fees[board_title],
    "電影應收": len(movie_set_2) * unit_fees[movie_title],
    "總應收": (len(board_set_2) * unit_fees[board_title]) + (len(movie_set_2) * unit_fees[movie_title])
}

print(f"桌遊整理串列：{board_list_2}")
print(f"電影整理串列：{movie_list_2}")
print(f"桌遊去重名單：{sorted_board_2}")
print(f"電影去重名單：{sorted_movie_2}")
print(f"共同參加者：{sorted_common_2}")
print(f"只參加桌遊者：{sorted_only_board_2}")
print(f"只參加電影者：{sorted_only_movie_2}")
print(f"全部參加者：{sorted_all_2}")
print(f"總不重複人數：{summary_2['總不重複人數']} 人")
print(f"報名人次：{summary_2['報名人次']} 人次")
print(f"通知名單前兩位：{preview_notice_2}")
print(f"總應收：{summary_2['總應收']:.2f} 元\n")


# -----------------------------------------------------
# 測試三：兩場去重後完全相同
# -----------------------------------------------------
print("=== 測試三 ===")
board_raw_3 = " Amy, Ben, amy, Cora "
movie_raw_3 = " AMY, ben, CORA, amy "

board_list_3 = board_raw_3.replace(" ", "").lower().split(",")
movie_list_3 = movie_raw_3.replace(" ", "").lower().split(",")

board_set_3 = set(board_list_3)
movie_set_3 = set(movie_list_3)

common_3 = board_set_3 & movie_set_3
all_parts_3 = board_set_3 | movie_set_3
only_board_3 = board_set_3 - movie_set_3
only_movie_3 = movie_set_3 - board_set_3

sorted_board_3 = sorted(list(board_set_3))
sorted_movie_3 = sorted(list(movie_set_3))
sorted_common_3 = sorted(list(common_3))
sorted_all_3 = sorted(list(all_parts_3))
sorted_only_board_3 = sorted(list(only_board_3))
sorted_only_movie_3 = sorted(list(only_movie_3))
preview_notice_3 = sorted_all_3[:2]

summary_3 = {
    "桌遊人數": len(board_set_3),
    "電影人數": len(movie_set_3),
    "共同人數": len(common_3),
    "總不重複人數": len(all_parts_3),
    "報名人次": len(board_set_3) + len(movie_set_3),
    "桌遊應收": len(board_set_3) * unit_fees[board_title],
    "電影應收": len(movie_set_3) * unit_fees[movie_title],
    "總應收": (len(board_set_3) * unit_fees[board_title]) + (len(movie_set_3) * unit_fees[movie_title])
}

print(f"桌遊整理串列：{board_list_3}")
print(f"電影整理串列：{movie_list_3}")
print(f"桌遊去重名單：{sorted_board_3}")
print(f"電影去重名單：{sorted_movie_3}")
print(f"共同參加者：{sorted_common_3}")
print(f"只參加桌遊者：{sorted_only_board_3}")
print(f"只參加電影者：{sorted_only_movie_3}")
print(f"全部參加者：{sorted_all_3}")
print(f"總不重複人數：{summary_3['總不重複人數']} 人")
print(f"報名人次：{summary_3['報名人次']} 人次")
print(f"通知名單前兩位：{preview_notice_3}")
print(f"總應收：{summary_3['總應收']:.2f} 元")# hw09
