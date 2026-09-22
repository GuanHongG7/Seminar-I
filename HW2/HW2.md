2026/9/22
# 上課筆記
## 1. 使用深度學習模型預測特發性黃斑上膜手術後的視覺預後
### 研究背景
特發性黃斑上膜在臨床上面遇到以下問題:
手術後黃斑厚度已經改善，但為什麼視力仍可能不佳
是否可以單純利用術前 OCT 影像預測術後視力
### 研究流程
術前 OCT 影像  
→ 影像前處理  
→ ROI 分割  
→ 資料增強  
→ 深度學習模型  
→ 術後視力預後分類  
→ Grad-CAM 解釋模型判斷依據

使用的深度學習模型：
- Inception-v3
- ResNet-101
- VGG-19
 
透過5-fold cross validation(五折交叉驗證)評估模型

### 資料篩選
排除以下條件：
- Secondary ERM，次發性黃斑上膜
- Stage I ERM
- 曾有增殖性糖尿病視網膜病變、糖尿病黃斑水腫、玻璃體切除術或外傷病史
- 術後黃斑水腫或 ERM 復發
- 曾接受其他眼內手術，單純白內障手術除外
- 可能影響視力的眼內混濁
- OCT 影像品質不佳

### 資料分佈
訓練集644張

額外測試52張

訓練集:驗證集 8:2

### 影像預處理
首先從原始 OCT 中擷取視網膜區域，移除不需要的背景，只保留與 ERM 相關的視網膜結構。

### 模型建立
| Model        | Input size |
| ------------ | ---------- |
| Inception-v3 | 299 × 299  |
| ResNet-101   | 224 × 224  |
| VGG-19       | 224 × 224  |

Optimizer:SGDM — Stochastic Gradient Descent with Momentum

模型評估:5-fold Cross Validation

做法是將資料分為五份，每次使用其中一份作 Validation，其餘四份 Training，總共訓練五次，最後計算五次結果的平均表現。

### Grad-CAM
Grad-CAM 可以產生 Heat Map：
- 紅／黃區域：模型較關注的位置
- 藍色區域：影響較低

### 模型表現
評估指標包括：
- Recall
- Specificity
- Precision
- F1-score
- Accuracy
- AUC

ResNet-101在三種CNN中整體表現較佳。

## 2.以形態定量與放射組學分析預測兒童幕上低級別膠質瘤相關癲癇

### 研究目的
- 分析兒童幕上低級別膠質瘤的 MRI 影像特徵
- 比較有癲癇與無癲癇患者之間的差異
- 萃取腫瘤位置、形狀、強度與紋理等影像特徵
- 利用 Machine Learning 建立癲癇預測模型
希望藉由 MRI 影像，在手術或治療前判斷患者是否較容易發生與腫瘤相關的癲癇。

### 研究資料

研究共分為兩組：

- 有癲癇：23 位患者
- 無癲癇：25 位患者

### MRI 特徵比較

研究比較有癲癇與無癲癇患者的腫瘤位置與 MRI 特徵。

其中最明顯的是：Temporal lobe

有癲癇患者中約：73.9%

腫瘤主要位於顳葉，而無癲癇組只有：16%

代表腫瘤位置可能是與癲癇發生非常重要的因素之一。

### 影像處理流程
T2-FLAIR MRI  
→ 影像前處理  
→ 腫瘤 ROI 標記  
→ Spatial normalization  
→ Radiomics 前處理  
→ 特徵萃取  
→ Feature selection  
→ Machine Learning  
→ Predict seizure

## 3. 使用腦電圖與機器學習預測憂鬱症藥物的長期療效
### 研究主題
研究利用：
- EEG（Electroencephalography，腦電圖）
- EEG 功率特徵
- Functional Connectivity（功能性連結）
- Phase Synchronization（相位同步）
- Machine Learning
來預測重度憂鬱症患者接受藥物治療後，
在不同治療時間點是否會對藥物產生良好反應。

### 研究對象

研究共納入：
77 位 Major Depressive Disorder（重度憂鬱症患者）
收集的資料包含：
- Week 0 EEG
- Week 1 EEG
- Week 4 HAM-D score
- Week 6 HAM-D score
- Week 8 HAM-D score
在治療開始前與治療一週後記錄 EEG，接著第 4、6、8 週評估患者的憂鬱症改善程度。

### 整體研究流程
EEG 資料  
→ EEG preprocessing  
→ Artifact removal  
→ 頻帶分割  
→ EEG 特徵萃取  
→ Functional Connectivity / Power analysis  
→ Machine Learning  
→ Leave-One-Out Cross Validation  
→ 預測 Week 4、6、8 的藥物療效

### EEG Preprocessing

首先對 EEG 進行前處理。

Selected EEG  
→ FIR bandpass filtering（0.5–30 Hz）  
→ Common average re-referencing  
→ ICA 去除眼動等 Artifact  
→ 各 EEG 頻帶 Bandpass filtering

