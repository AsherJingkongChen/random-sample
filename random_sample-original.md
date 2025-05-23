# HW3

在等候理論中，Poisson Distribution 描述固定時間內發生的事件數量，而 Exponential Distribution 描述事件發生的間隔時間。本次作業的目標是讓你透過程式實作來理解這兩種分布的特性與相互關係。

**禁止使用 NumPy、SciPy 或其他模組內建的指數/泊松分布抽樣函數。**

## Exponential Distribution（50％）

1.  **自行實作** 指數分布的隨機數產生器（要能自訂發生的速率 λ ），**禁止使用 NumPy、SciPy 或其他模組內建的指數/泊松分布抽樣函數**。
2.  產生 1000 個指數分布的隨機數，並計算它們的**均值（mean）與變異數（variance）**，檢查是否接近理論值。
3.  **畫出直方圖**，觀察數據是否符合指數分布的形狀。
4.  提示：可以用 Inverse Transform Sampling。

## 驗證 Exponential Distribution 與 Poisson Distribution 的關係（50％）

### 背景知識

Poisson Distribution 描述的是**固定時間內發生的事件數量**。而指數分布描述的是**事件之間的時間間隔**，如果事件是根據 Poisson Distribution 發生的，那麼**事件發生的間隔時間**服從 Exponential Distribution。換句話說，泊松分布與指數分布存在以下關係：

*   如果事件發生的時間間隔服從**指數分布**，那麼在單位時間內發生的事件數量就會服從**泊松分布**。
*   也就是說，如果我們產生很多**指數分布的隨機數**，並將它們累積起來，統計某段時間內發生的事件數量，那麼這些數據應該會符合泊松分布。

### 實驗設計

請按照以下步驟進行實驗，並驗證泊松分布與指數分布的關係：

1.  **使用內建函數（NumPy 或 SciPy）產生泊松分布與指數分布的隨機數：**
    *   產生 1000 個泊松分布的隨機數（使用 `numpy.random.poisson(λ, size)`）。
    *   產生 1000 個指數分布的隨機數（使用 `numpy.random.exponential(1/λ, size)`）。
2.  **驗證指數分布的間隔時間能夠模擬泊松分布：**
    *   產生 10000 個指數分布的隨機數，將這些數字看成是事件發生的間隔時間。
    *   透過累積間隔時間，計算在單位時間內發生的事件數，這些數據應該符合泊松分布。
    *   計算這些數據的均值與變異數，與泊松分布的理論值 E[X]=λ，Var(X)=λ 比較。
3.  **畫出直方圖，觀察分布形狀：**
    *   繪製泊松分布與指數分布的直方圖，檢查它們的形狀是否符合理論分布。
    *   繪製指數分布累積後得到的泊松分布直方圖，檢查其是否與內建的泊松分布相似。

### 作業繳交方式與規定：

1.  請一律使用 **Python** 實做程式碼，若是不熟悉 Python 的同學，可以觀看 蔡炎龍 教授的磨課師 課程學習！
2.  請一律使用 **colab** 完成程式碼。
3.  作業請編輯成一份 **報告pdf**，需要包含每個問題的**模擬結果截圖**與 **Colab 程式碼連結**（記得開分享）。
4.  作業請繳交至 **moodle**，配分都在題目上！
