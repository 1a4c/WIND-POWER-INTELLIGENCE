**核心數學物理引擎實作：**
   * **`filterWindSpeed`（Layer 2）**：實作了低通指數濾波器（Exponential Moving Average），在降雨噪音高時自動增強阻尼，過濾瞬間衝擊雜訊，將原始風速平滑傳遞給狀態機。
   * **`updateSCurvePitch`（Layer 7）**：實作了工業級的 **S 形（S-Curve）加減速軌跡限制演算法**。當輸入手動階躍指令或風速突變時，限制其最大加速度（Acceleration）與最大角速度（Velocity），模擬液壓或伺服馬達的物理行程極限，防止機械結構損毀。
   * **`calculateResonanceVibration`（Layer 8）**：高頻嚙合共振。當啟動主動減震時，系統執行類似主動降噪（Active Damping）的反相消干涉。

2. **多頻道實時示波（High-Performance Canvas Scope）：**
   * 將物理計算與動畫、圖表同步綁定。利用三個 Canvas 畫布，每秒 60 幀無縫繪製歷史數據，將複雜的訊號變化以直觀、流暢的動態曲線展示。
