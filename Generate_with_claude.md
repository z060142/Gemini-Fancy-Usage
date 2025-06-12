# 使用其他AI創建Gemini Canvas應用

## 概述

你可以使用Claude、ChatGPT等其他AI來創建網頁應用，然後在Gemini Canvas上運行。這讓你能結合不同AI的優勢，獲得更好的開發體驗。

## 核心Prompt模板

使用以下標準化Prompt來請求其他AI創建網頁應用：

```
請寫出一個單一頁面的網頁程式，API的部分用以下的方法不要改動，網頁利用gemini處理文字，imagen-3.0生成圖片，並互相作用。

// --- API Configuration --- 
const API_KEY = ""; // Gemini API金鑰會自動處理 
const GEMINI_API_URL = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${API_KEY}`; 
const IMAGEN_API_URL = `https://generativelanguage.googleapis.com/v1beta/models/imagen-3.0-generate-002:predict?key=${API_KEY}`;

[在此添加你的具體需求描述]
```


## 使用流程

### 1. 在其他AI平台創建應用
- 使用上述Prompt模板
- 添加你的具體功能需求
可參考 [PromptTemplate.md](./PromptTemplate.md)，其中包含建立 APP 可用的範例 Prompt。
- 獲得完整的HTML程式碼

### 2. 在Gemini Canvas部署
1. 開啟Gemini的Canvas模式
2. 讓Gemini建立一個Hello world網頁
3. 點擊Canvas中的「程式碼」
4. 將其他AI生成的程式碼完全取代Hello world的程式碼
5. 切換到預覽模式即可使用

### 3. 功能驗證
- 確認Gemini文字處理功能正常
- 測試Imagen圖片生成功能
- 檢查兩者互動是否順暢

## 優勢

- **發揮各AI特長**：利用Claude的程式和版面設計能力，Gemini的API整合
- **快速開發**：無需處理API金鑰和環境配置
- **即時測試**：在Canvas中立即預覽和調試
- **穩定運行**：使用Gemini的原生API支援

## 注意事項

- 必須保持API配置代碼不變
- 確保程式碼是單一HTML檔案格式
- API金鑰由Gemini Canvas環境自動處理
- 不支援localStorage等瀏覽器存儲API