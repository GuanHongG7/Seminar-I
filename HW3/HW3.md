2026/9/29
# 陳冠宏 11563137 上課筆記
## 微型氣體感測器產品設計開發
### 研究背景
氣體感測器主要用於偵測環境中的氣體種類與濃度，應用範圍涵蓋工業安全、室內空氣品質、智慧工廠、IoT、車用系統及穿戴式裝置等。
傳統氣體感測器雖然已廣泛應用，但仍面臨幾個問題：
- 感測器尺寸較大
- 功耗較高
- 多點監測資料分散
- 不同環境溫濕度容易造成量測漂移
- 長時間使用後可能產生感測器老化與基線漂移
- 不同感測器之間的一致性不足
- 多種氣體可能產生交叉干擾
- 缺乏即時校正與智慧分析能力

因此目前氣體感測技術逐漸朝向：

- 微型化
- 低功耗
- 高靈敏度
- 高選擇性
- 快速響應
- 多氣體辨識
- 智慧校正
- IoT 系統整合

### MEMS 氣體感測器的優勢

MEMS（Micro-Electro-Mechanical Systems）技術可將氣體感測器、微加熱器、電極與感測薄膜整合在非常小的晶片面積中。

主要優點包括：

- Sensor size 小
- Power consumption 低
- 升溫速度快
- 可大量製造
- 容易整合 MCU、IoT 與智慧演算法
- 適合建構分散式氣體監測系統

### 研究流程
材料 → 元件 → 模擬 → 製程 → 感測 → 訊號處理 → AI 校正 → 實場驗證 → 產品化

1. 感測材料選擇

金屬氧化物半導體氣體感測器：
- SnO₂
- ZnO
- TiO₂
- WO₃
- In₂O₃
- Fe₂O₃
- - NiO
- CuO
- Co₃O₄
- Cr₂O₃

2. MEMS 微加熱器設計

Metal Oxide Sensor 通常必須在一定溫度下工作

3. ANSYS 模擬

利用 ANSYS 進行分析：

- Temperature Distribution
- Thermal Stress
- Power Consumption
- Structure Deformation

4. IoT 與資料平台

系統可以執行以下動作：

- 即時顯示多顆 Sensor
- 儲存歷史資料
- 分析趨勢
- 偵測異常
- 進行 Remote Monitoring

### 成果
與其他 Sensor 相比：

大型 Sensor：

- 高濃度量測
- 高功耗
- 尺寸較大

微型 Sensor：

- 低濃度量測
- 低功耗
- 小尺寸

因此 MEMS Sensor 更適合：

- 可攜式裝置
- IoT
- Smart Building
