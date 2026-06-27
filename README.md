# tulayCy: A Specialized Taglish Morphological Analyzer 🇵🇭

An open-source, high-performance Natural Language Processing (NLP) pipeline built specifically to analyze intra-word code-switching (Taglish). 

By integrating **spaCy** and **calamanCy** (powered by the gold-standard 15.6k sentence **UD-NewsCrawl treebank**), `tulayCy` strips away conversational hybrid affixes and infixes to map the grammatical structure of mixed sentences and isolate underlying English root words.

---

## 📐 How It Works (The Processing Layer)

Taglish operates at the intersection of Austronesian morphosyntactic templates and Germanic/Romance vocabularies. When a mixed string enters the engine, it moves through a strict 3-stage computational pipeline:

[ Input Text: "Fino-forward ko yung link sa GC." ]
│
▼
┌───────────────────────────────────────────────┐
│ Stage 1: Token-Level Language ID (LID)        │
└───────────────────────────────────────────────┘
• Fino-forward ➔ [MIXED]   • ko ➔ [TAGALOG]
• yung ➔ [TAGALOG]         • link ➔ [ENGLISH]
│
▼
┌───────────────────────────────────────────────┐
│ Stage 2: Morphological De-Stacking Engine     │
└───────────────────────────────────────────────┘
• Input: "Fino-forward"
• Isolates grammatical infix template: "-ino-"
• Extracts clean English root: "forward"
│
▼
┌───────────────────────────────────────────────┐
│ Stage 3: Cross-Lingual Semantic Realignment   │
└───────────────────────────────────────────────┘
• Maps grammatical intent (Incomplete Aspect)
• Normalizes structure for downstream analytics

