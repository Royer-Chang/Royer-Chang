# AI 應用生態系總覽

> 本文以「冰山」分層結構，整理現代 AI 應用技術棧的各層工具與職責。  
> 越上層越接近產品落地，越下層越接近基礎能力與治理工具。

---

## 一、各層工具總表

| 層級 | 類別 | 圖中工具 / 代表產品 | 主要用途 |
|:---:|:---:|:---|:---|
| Level 0 | 部署 | Groq、AWS、Google Cloud、Together.ai | 模型推理部署、算力供應、雲端託管與擴展 |
| Level 1 | 評估 | LangSmith、Phoenix、DeepEval、ragas | 測試提示詞、評估回答品質、檢驗 RAG 表現 |
| Level 2 | LLMs | Kimi、Gemini Pro、Claude、GPT | 核心大語言模型，負責語言理解與生成 |
| Level 3 | 框架 | LangChain、KimiIndex、Haystack、DSPy | 串接模型與工具、RAG 流程編排、Agent 調用 |
| Level 4 | 向量資料庫 | Pinecone、Chroma、Milvus、Weaviate | 儲存向量資料、相似度搜尋、語意檢索 |
| Level 5 | Embedding | Nomic、Ollama、Voyage AI、OpenAI | 將文字或內容轉成向量，支援語意比對 |
| Level 6 | 資料抽取 | Firecrawl、Scrapy、Docling、KimiParse | 網頁爬取、文件解析、非結構化資料轉換 |
| Level 7 | 記憶 | Zep、Mem0、cognee、Letta | 保存對話歷史、使用者記憶、長期上下文管理 |
| Level 8 | 對齊 / 治理 | Guardrails AI、Arize、Langfuse、Helicone | 輸出安全控制、系統監控、追蹤與成本治理 |

---

## 二、各層實際用途說明

### Level 0｜部署
把模型或 AI 服務真正跑起來，提供穩定的推理能力與雲端算力。  
**實際場景：** 讓 chatbot 對外提供服務、降低推理延遲、管理 GPU 資源與雲端費用。

---

### Level 1｜評估
量化 AI 系統的表現，確保回覆準確、相關且無幻覺。  
**實際場景：** 測試 prompt 改動的效果、驗證 RAG 是否找對資料、比較不同模型的輸出品質。

---

### Level 2｜LLMs
提供語言理解、生成、推理、摘要與問答等核心能力。  
**實際場景：** 問答機器人、文件摘要、程式碼輔助、多輪對話助理。

---

### Level 3｜框架
把 LLM 與資料、工具、流程串接成完整的 AI 應用。  
**實際場景：** RAG 檢索流程、Agent 工具調用、多步驟工作流、prompt chain 編排。

---

### Level 4｜向量資料庫
儲存向量並執行相似度搜尋，支撐知識庫檢索。  
**實際場景：** 從大量文件中找最相關段落、建立企業知識庫、讓模型根據資料庫內容回答。

---

### Level 5｜Embedding
把文字、段落或圖片轉成向量，方便後續檢索與相似度計算。  
**實際場景：** 文件切片後做語意搜尋、相似問題匹配、多語系跨語言檢索。

---

### Level 6｜資料抽取
把網頁、PDF、HTML、掃描文件等原始資料轉成可用格式。  
**實際場景：** 爬取網站建立知識庫、從 PDF 擷取表格與段落、將非結構化資料轉為 RAG 可用內容。

---

### Level 7｜記憶
讓系統記住使用者偏好、過往互動與任務狀態，提升長期對話能力。  
**實際場景：** 個人助理記住偏好、客服機器人保留歷史脈絡、多輪 Agent 任務不中斷。

---

### Level 8｜對齊 / 治理
控制輸出品質與安全性，並提供全面的系統觀測能力。  
**實際場景：** 限制輸出格式、追蹤錯誤與成本、監控延遲與 token 用量、防止不合規回答。

---

## 三、值得特別關注的工具

### 核心大模型
| 工具 | 關注原因 |
|:---|:---|
| **GPT (OpenAI)** | 生態最成熟，API 穩定，工具調用能力強 |
| **Claude (Anthropic)** | 長上下文與安全性優異，企業應用常見 |
| **Gemini Pro (Google)** | 多模態能力突出，Google 生態整合佳 |

---

### 框架
| 工具 | 關注原因 |
|:---|:---|
| **LangChain** | 社群最大，整合最廣，是入門 RAG / Agent 的首選 |
| **DSPy** | 程式化優化 prompt 與 pipeline，工程與研究價值高 |
| **Haystack** | 在檢索與問答場景表現穩定，適合企業知識庫 |

---

### 評估與觀測
| 工具 | 關注原因 |
|:---|:---|
| **LangSmith** | 開發與除錯體驗佳，與 LangChain 深度整合 |
| **ragas** | 專為 RAG 設計的評估框架，簡單實用 |
| **Helicone** | API 監控與成本追蹤輕量易用 |
| **Phoenix / Arize** | 企業級 AI observability，適合 production 監控 |

---

### 資料抽取
| 工具 | 關注原因 |
|:---|:---|
| **Firecrawl** | 網頁爬取 + 結構化抽取一體化，近年熱度極高 |
| **Docling** | 文件解析能力強，對 PDF / Office 文檔特別有用 |

---

### 記憶
| 工具 | 關注原因 |
|:---|:---|
| **Mem0** | 輕量記憶層，近年社群關注度快速成長 |
| **Zep** | 對話記憶與 session 管理，整合容易 |
| **Letta** | 偏 Agent memory 與長期狀態，架構設計前衛 |

---

### 觀測與治理
| 工具 | 關注原因 |
|:---|:---|
| **Langfuse** | 開源 LLM observability，自架或雲端皆可 |
| **Guardrails AI** | 輸出格式與安全約束，適合需要嚴格控制輸出的場景 |

---

## 四、整體優先級建議

```
第一優先（基礎能力）
  GPT / Claude / Gemini  ·  LangChain / DSPy  ·  Pinecone / Milvus  ·  OpenAI Embedding

第二優先（落地必備）
  Firecrawl / Docling  ·  ragas / LangSmith / Phoenix  ·  Mem0 / Zep

第三優先（觀測與治理）
  Arize / Helicone  ·  Guardrails AI  ·  Langfuse
```

---

> **一句話總結：**  
> 一個成熟的 AI 應用不是只靠 LLM，而是由**部署、評估、框架、向量庫、Embedding、資料抽取、記憶與對齊治理**等多層工具共同組成。
