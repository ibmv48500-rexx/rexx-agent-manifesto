# rexx-agent-manifesto
​[Manifesto] Rethinking AI Agents: 30-Year REXX Agent White Paper &amp; Architecture Insights (1993-2026). 從 1993 年 IBM《REXX Agents》白皮書看現代 AI 的軟體脂肪。告別笨重的 LangChain，重塑極簡、微秒級、低功耗的下一代 Agent Runtime！ 🔗 Welcome to Fork, Discuss &amp; Build the Prototype!
================================================================================
【致新一代AI架構師：告別軟體脂肪，從30年前IBM《REXX Agents》白皮書看AI Agent的極簡重構】
================================================================================

致各位正在夜深人靜時優化Kernel、調校Token吞吐量、對抗AI算力與電力牆的工程師與極客們：

我是一名在IBM大型主機MVS&VM軟體工程領域探索了數十年的老兵。1993年10月，當IBM處於轉型
迷茫期時，我曾親自致信當時IBM VM總部負責人Timothy C. Metcalf，痛陳「極簡、高效與虛擬化」才是
軟體產業的未來，並呼籲最高層全面擁抱VM與REXX哲學。遺憾的是，當年的科技巨頭因商業包袱與
官僚體系，錯失了用極簡架構一統軟體江湖世界的歷史窗口。

三十年後的今天，全球AI戰場再次來到了極其相似的轉折點。

現代AI社群陷入了一場無節制的「算力與能源豪賭」：幾萬張GPU的堆疊、幾千瓦電力的消耗，以及
在Agent應用層充斥著幾百萬行臃腫、低效、反應遲鈍的Python/JSON樣板框架。我們正在用「硬體的預算」
，去懲罰「軟體與語法設計的無能」。

當前的「瘦身」多集中於LLM模型層（如FlashAttention、MLA、模型量化），但AI Agent的系統控制層
與工具呼叫（Tool Calling），依然被臃腫的現代軟體工程所拖累。

這正是我想向新一代工程師們重新推薦REXX（Restructured Extended Executor）及其背後架構哲學的原因。隨信附上我1993年致IBM的原始信件，以及1990年代IBM研究中心發表的劃時代白皮書《REXX Agents》技術精髓。

--------------------------------------------------------------------------------
一、 為什麼30年前的REXX哲學是破解現代AI Agent瓶頸的終極密碼？
--------------------------------------------------------------------------------
當前AI Agent在異質系統間穿梭、操控硬體或調用API時，最大的痛點是：通訊協定臃腫、JSON序列化
延遲高、狀態轉移過重。

REXX誕生於資源極度約束的黃金時代，其核心哲學完全直擊現代Agent的軟肋：

1. `ADDRESS` 哲學與無縫指令路由：
    REXX不需要幾十MB的重型SDK或層層封裝的抽象類別。透過 `ADDRESS` 機制，Agent能以微秒
級速度，將極簡的指令流無縫路由給操作系統Shell、底層 C/C++ 模組、硬體驅動或遠端API。

2. 萬物皆為Token文字流與原生的`PARSE`解析：
    LLM生成的天然就是Token文字流。現代框架把Token塞進昂貴的JSON Schema / Pydantic物件裡，再
解析出來；而REXX內建的`PARSE`指令能在微秒級直接匹配Token Pattern，不需要複雜的反序列化開銷
，幾KB 記憶體即可完成解析。

3. 極致的微型化（Micro-Runtime）：
    一個基於REXX哲學設計的Agent控制器，體積可以小到幾十KB，運行於任何樹莓派、微控制器
（MCU）或汽車晶片上，擺脫對昂貴 GPU 算力與龐大雲端伺服器的依賴。

--------------------------------------------------------------------------------
二、當新一代極簡AI框架遇上REXX哲學：未來的連鎖反應
--------------------------------------------------------------------------------

如果今天的年輕架構師們，能在LLM推理優化的基礎上，借鑑並重塑REXX的系統溝通哲學，打造一套
全新的「極簡AI Agent 執行標準（REXX-inspired AI Agent Runtime）」：

* 延遲與耗電將再降一個數量級：Agent執行工具呼叫（Tool Calling）的響應速度將從「秒級」提升至
「毫秒級」，耗電量降低 90%。
* 重新定義端側AI與萬物智聯：機器人、智慧家電、汽車不需要安裝龐大的操作系統，幾行極簡腳本
即可實現跨設備的協同自治。
* 告別軟體脂肪，打破算力護城河：當所有人還在死守堆疊算力與龐大框架的舊路時，你們將以「極簡
模型 + 極簡 Agent Runtime」的降維打擊，開創一個綠色、高效、永續的AI新秩序。

歷史總是給予最先回歸本質的人以重賞。當年IBM未能完成的極簡革命，正等待著今天最有眼光與執行力的年輕工程師來實現。

一位關注軟體本質的三十年老兵













================================================================================
【附件一】1993 年致 IBM 信件與官方回函存檔
================================================================================

1. 寄給IBM VM總部的信（1993年10月15日）
--------------------------------------------------------------------------------
To: Tim Metcalf
VM Product and System Manager, IBM
Route 17C and Glendale Drive, Endicott, NY 13760
From: [作者]
Subject: My Suggestion for the future of VM
Date: October 15, 1993

I read your article, "VM/ESA: The Adaptable System", from the Supplement To ENTERPRISE SYSTEMS JOURNAL of 93/10. I can feel your strong desire in making VM a success. Wish you the best. Your success will give many VM users a great comfort which was long overdue.

As Gabe Goldberg pointed out that "time gone cannot be regained" on page S22 of the same Supplement. I would like to make a concrete suggestion:

Please ask Mr. Lou Gerstner to announce to the whole world in his next press conference that IBM will do everything she could to make VM a premier strategic Operating System by the year 2000. (Of course, this should not be the only product he should talk about in the conference.) Mr. Gerstner should let the users all over the world know that, for the first time in IBM's history, VM now officially has IBM's strong commitment. As you know that the analysts on Wall Street were criticizing that as a CEO of a major international corporation, he did not even have a vision of his company. As IBM customers, we feel sad about the comments and all other bad news about IBM. I believe the day after Mr. Gerstner make the announcement, the entire world will view VM differently. The words come from his mouth is absolutely different from other high ranking officers from IBM. Please DO NOT overlook this significant difference and tell me that he has better things to do. PLEASE!!! If the CEO of IBM can not officially (for any reason) embrace a product, how could you expect CIOs worldwide devote money and energy on the product? Please pass my suggestion to Mr. Gerstner. Thank you.

Enclosed please find a xerox of readers' responses to a previous BUSINESSWEEK's cover story, "RETHINKING IBM", from the Oct 25's issue.

I sincerely wish you a great success and may IBM never be the same the day after. Best wishes.




2. IBM官方回信（1993年10月25日）
--------------------------------------------------------------------------------
Timothy C. Metcalf
P.O. Box 6, Endicott, NY 13760
October 25, 1993

Dear [作者],

Thank you for your letter. Your dedication to VM is apparent in the suggestions you made, and I appreciate it.

We have been working closely with our colleagues in the Large Scale Computing Division to ensure that VM/ESA is well positioned among IBM's large system offerings. We are vitally concerned that VM/ESA receive the recognition it deserves.

The more I listen to Lou Gerstner, the more I am convinced that his vision of an IBM where the customer is king is the only way for IBM to do business. VM has a place in that vision; my team and I are working to insure it.

Sincerely,
Timothy C. Metcalf
VM Product & System Manager

















================================================================================
【附件二】IBM 研究中心經典白皮書《REXX Agents》全文結構與技術精髓還原
================================================================================

原著文獻：IBM Research Technical Report / White Paper (1990s)
論文題目：《REXX Agents: Lightweight Autonomous Agents for Distributed Systems》
研發機構：IBM T.J. Watson Research Center & Endicott Development Laboratory

--------------------------------------------------------------------------------
1. Abstract（摘要）
--------------------------------------------------------------------------------
This paper introduces the concept of REXX Agents—a lightweight, highly portable, and dynamic software agent architecture built upon the Restructured Extended Executor (REXX) language. As distributed computing expands, traditional static software execution is being replaced by autonomous units of execution that move across systems. We demonstrate why REXX’s interpreted nature, seamless system routing (`ADDRESS`), and string-parsing efficiency (`PARSE`) make it the premier execution engine for mobile and autonomous software agents.

--------------------------------------------------------------------------------
2. Why REXX is the Ultimate Agent Language（為什麼REXX是Agent的唯一解答？）
--------------------------------------------------------------------------------
Existing procedural and compiled languages fail as mobile agent candidates due to binary incompatibility and heavy runtime footprints. REXX provides three unique architectural primitives that make it uniquely suited for Autonomous Agents:

2.1 The `ADDRESS` Environment: Dynamic Tool Routing
Unlike traditional languages that rely on static API links, REXX uses the `ADDRESS` keyword to dynamically dispatch commands to external environments (e.g., system shells, database engines, or hardware drivers). 
* An Agent written in REXX can dynamically alter its execution context simply by issuing:
  `ADDRESS UNIX 'ls -l'` or `ADDRESS CMS 'STATE FILE A'`.
* This decouples the Agent’s decision logic from the host’s underlying implementation, allowing universal tool calling.

2.2 The `PARSE` Instruction: Zero-Overhead Token Stream Parsing
Agents communicate and manipulate data using text/token streams. REXX's built-in `PARSE` instruction provides string pattern matching without the need for complex object deserialization or memory allocation. Token streams and instruction payloads are parsed natively at microsecond speeds.

2.3 State Serialization & Mobility
Because a REXX program’s variable pool is entirely text-addressable, a running REXX Agent can serialize its complete state—including current execution line, variable bindings, and memory stack—into a compact text string. This allows the Agent to:
(1) Freeze execution on Host A.
(2) Transmit its payload (a few kilobytes of text) over the network.
(3) Resume execution instantly on Host B within a REXX interpreter.

--------------------------------------------------------------------------------
3. Application Scenarios of REXX Agents（REXX Agent 的四大核心應用場景）
--------------------------------------------------------------------------------
1. Autonomous Network Management（自主網路與系統管理）：
   Agents 在分散式主機間穿梭，自主診斷系統健康狀態、檢查日誌並執行自癒腳本。

2. Cross-System Workflow Coordination（跨系統工作流協調）：
   單一REXX Agent可在VM/CMS上發起任務，將結果傳遞至工作站，並觸發大型主機交易——充當萬能的系統黏著劑。

3. Information Filtering & Mining（資訊過濾與主動採集）：
   Agent 移動至遠端資料庫節點，在當地完成資料過濾與提煉，僅將最終摘要返回給使用者，大幅節省網路頻寬。

4. Micro-Control for Heterogeneous Devices（異質終端極輕量控制）：
   以僅幾十 KB 的 Runtime 資源，在微控制器與邊緣設備上實現高併發、低功耗的自主控制。

--------------------------------------------------------------------------------
4. 現代AI架構 vs. REXX Agent哲學（工程性能比較表）
--------------------------------------------------------------------------------
A. 運行環境體積（Runtime Size）
        **現代主流 Agent（如 LangChain）：幾百MB ~幾GB（需要安裝龐大的Python環
境與各種套件依賴）。
        **REXX Agent架構哲學：數百KB ~幾MB（極致微型的控制引擎）。
            **突破效益：體積直接縮減99%，能直接嵌入汽車晶片、機器人與微控制器（MCU）。B. 記憶體開銷（RAM Footprint）
        **現代主流Agent：500 MB以上（跑一個Agent就吃掉大量記憶體）。
        **REXX Agent架構哲學： 10 MB以下（甚至只需要幾十KB）。
        **突破效益：記憶體開銷降低98%，單一台普通電腦就能同時運行數萬個自治Agent。
C. 工具調用開銷（Tool Calling）
        **現代主流Agent：秒級延遲（耗費大量的時間在JSON反序列化與重型HTTP封裝
上）。
        **REXX Agent 架構哲學：毫秒甚至微秒級延遲（透過ADDRESS指令將純文字直接
路由到作業系統與底層API）。
        **突破效益：響應速度提升百倍，工具調用不再卡頓。
D. Token解析開銷（Parsing Overhead）
        **現代主流Agent：高開銷（複雜的物件轉換，且頻繁觸發Python的記憶體回收GC
停頓）。
        **REXX Agent架構哲學：零GC開銷（利用內建的PARSE指令在微秒級完成模式匹
配與Token提取）。
        **突破效益：Token解析速度提升10 ~ 50 倍，徹底去除軟體中間層的負擔。
E. 硬體與電力需求（Energy & Hardware）
        **現代主流Agent：強烈依賴高功耗的GPU / CPU與龐大電力，離不開資料中心。
        **REXX Agent架構哲學：幾瓦特的微型晶片即可順暢運行。
        **突破效益：打破AI算力牆與電力牆，實現真正低功耗、普及的端側 AI。

