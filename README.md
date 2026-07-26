# rexx-agent-manifesto
​[Manifesto] Rethinking AI Agents: REXX Agent &amp; Architecture Insights (1993-2026). 從 1993 年 IBM《REXX Agents》看現代 AI 的軟體脂肪。告別笨重的 LangChain，重塑極簡、微秒級、低功耗的下一代 Agent Runtime！ 🔗 Welcome to Fork, Discuss &amp; Build the Prototype!
================================================================================
【致新一代AI架構師：告別軟體脂肪，從30年前IBM《REXX Agents》看AI Agent的極簡重構】
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

這正是我想向新一代工程師們重新推薦REXX（Restructured Extended Executor）及其背後架構哲學的原因。隨信附上我1993年致IBM的原始信件。

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
