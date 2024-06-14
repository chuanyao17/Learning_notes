# binary_search
當 right 設成 len(arr) 或 len(arr) - 1 時，二分查找算法的兩個不同設置如下：
## 當 right 設成 len(arr) 時
### bisect_left
區間設置：左閉右開區間 [left, right)
迭代條件：使用 while left < right
更新邊界：
如果 arr[mid] < x，則 left = mid + 1
如果 arr[mid] >= x，則 right = mid
最終答案：left 是插入點的位置。
### bisect_right
區間設置：左閉右開區間 [left, right)
迭代條件：使用 while left < right
更新邊界：
如果 arr[mid] <= x，則 left = mid + 1
如果 arr[mid] > x，則 right = mid
最終答案：left 是插入點的位置。
## 當 right 設成 len(arr) - 1 時
### bisect_left
區間設置：左閉右閉區間 [left, right]
迭代條件：使用 while left <= right
更新邊界：
如果 arr[mid] < x，則 left = mid + 1
如果 arr[mid] >= x，則 right = mid - 1
最終答案：left 是插入點的位置。
### bisect_right
區間設置：左閉右閉區間 [left, right]
迭代條件：使用 while left <= right
更新邊界：
如果 arr[mid] <= x，則 left = mid + 1
如果 arr[mid] > x，則 right = mid - 1
最終答案：left 是插入點的位置。

### 一般二分查找 (binary_search)
當 right 設成 len(arr) 時
區間設置：左閉右開區間 [left, right)
迭代條件：使用 while left < right
更新邊界：
如果 arr[mid] == x，則返回 mid
如果 arr[mid] < x，則 left = mid + 1
如果 arr[mid] > x，則 right = mid
最終答案：如果沒有找到 x，返回 -1。
當 right 設成 len(arr) - 1 時
區間設置：左閉右閉區間 [left, right]
迭代條件：使用 while left <= right
更新邊界：
如果 arr[mid] == x，則返回 mid
如果 arr[mid] < x，則 left = mid + 1
如果 arr[mid] > x，則 right = mid - 1
最終答案：如果沒有找到 x，返回 -1。
這樣設置保證了二分查找算法能夠正確地處理搜索過程中的邊界條件，並且找到目標元素或確認目標元素不在數組中。