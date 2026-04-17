<div align="center">


# Yuxuan Liu

**Undergraduate @ BUPT · Telecommunications Engineering**

Graph-Enhanced RAG &nbsp;·&nbsp; Knowledge Graph Quality &nbsp;·&nbsp; Multimodal Document Understanding

[![Site](https://img.shields.io/badge/🌐-drawsee.cn-informational?style=flat-square)](https://drawsee.cn)
[![Email](https://img.shields.io/badge/📧-liuyuxuanlovept@bupt.edu.cn-informational?style=flat-square)](mailto:liuyuxuanlovept@bupt.edu.cn)

</div>

---

I build research-grade RAG systems and study the failure modes that production pipelines tend to paper over — graph noise, structural information loss in multimodal ingestion, and the gap between answer-level evaluation and what actually goes wrong inside the retrieval graph.

My work sits at the boundary between engineering and research: I care about systems that run reliably, and I care about understanding *why* they fail when they do.

---

## Projects

### NoiseFilter-RAG

**Graph noise diagnosis and confidence-aware retrieval for LightRAG**

LightRAG builds knowledge graphs via LLM-driven entity extraction. That extraction step hallucinates — introducing wrong edges and polluted retrieval context that answer-level evaluation alone does not expose. This project builds a full diagnostic and filtering layer on top of LightRAG's graph pipeline.

**Stage 1 results** (100 edges, manual annotation):

|                   | Baseline | NoiseFilter |
| ----------------- | -------- | ----------- |
| Strict precision  | 0.15     | **0.22**    |
| Lenient precision | 0.50     | **0.57**    |
| Pairwise win rate | 0.4385   | **0.4615**  |

Stage 1 confirmed the method is non-trivial. Diagnostic work then showed the bottleneck is not post-hoc scoring, but upstream extraction quality. Current work targets three structural causes: chunk-entity binding (intercept hallucinated edges before graph insertion), relation directionality preservation (fix direction collapse in storage and aggregation), and evaluation infrastructure (stable source-grounded judge, NLI signal calibration, separated graph-layer vs. answer-layer feedback loops).

Engineering deliverables include reproducible dual-run pipelines, graph-quality sampling and manual labeling tooling, pairwise LLM judge evaluation, source-grounded judge, and relation directionality / source-binding audit scripts.

> Built on [HKUDS/LightRAG](https://github.com/HKUDS/LightRAG) (EMNLP 2025)

---

### CircuitModalProcessor

**Structure recovery for circuit schematics in multimodal RAG**

RAG-Anything's native image processor captions images and injects the caption text into the knowledge graph. For circuit schematics, that means component values, net names, and topological connections disappear into prose — unavailable for precise entity-level retrieval.

CircuitModalProcessor converts circuit diagrams into first-class KG entities and relations, extending RAG-Anything's modal processor framework with a domain-specific pipeline that combines VLM captioning, netlist parsing, and component-to-entity mapping.

```
Circuit schematic
    │
    ├─ VLM caption          →  circuit-level description
    ├─ Netlist parsing       →  component list + net topology
    └─ Component→Entity      →  R1 (resistor, 10kΩ), C1 (capacitor, 100nF)
                                R1 –[electrical, via net_vout]→ C1
    │
    └─► Dual-graph KG: cross-modal structure + native text graph
```

**3-way comparison experiment** (Text-only · RAG-Anything native · CircuitModalProcessor):

| Query type            | Text-only | Native | CircuitProcessor |
| --------------------- | --------- | ------ | ---------------- |
| Component-value       | —         | —      | —                |
| Topology              | —         | —      | —                |
| Cross-modal reasoning | —         | —      | —                |

*Results to be updated on experiment completion.*

> Built on [HKUDS/RAG-Anything](https://github.com/HKUDS/RAG-Anything)

---

### ZhaoXi — AI Platform for Electronics Education

**National-Level Innovation & Entrepreneurship Programme, BUPT · Apr 2024 – Present**

Vertical-domain AI system for electronics courses, integrating RAG, multimodal processing, and a distillation-inspired knowledge injection mechanism.

- End-to-end RAG pipeline (BGE-M3 + Milvus) over course slides and lab documents; domain QA accuracy +45% over base LLM
- Cross-modal alignment layer unifying Netlist/SPICE formal descriptions, natural-language documents, and scanned lab reports into a shared embedding space
- Dynamic prompt templates bridging circuit formal language and natural language; history-aware multi-turn dialogue
- Spring Boot + RabbitMQ + Redis Stream backend; ≤ 1.5s end-to-end latency; 82% human-evaluated accuracy; 500+ users; 73% retention

Awards: **1st Prize (Beijing) — China Collegiate Computing Contest 2024** · **2nd Prize (Beijing) — China International Innovation Competition 2024**

---

## How these connect

```
ZhaoXi
  └─ Building a domain RAG system surfaced two concrete problems:
     (1) flat-vector retrieval loses formal circuit structure
     (2) LLM extraction into KGs introduces noise without visibility
         │
         ├──► NoiseFilter-RAG
         │      Diagnose and govern graph noise in LightRAG's extraction pipeline.
         │      Separate graph-quality evaluation from answer-quality evaluation.
         │
         └──► CircuitModalProcessor
                Take ZhaoXi's netlist recovery logic, inject it into
                RAG-Anything as a proper modal processor — circuit schematics
                become structured KG entities, not opaque captions.
```

---

## Stack

```
RAG & KG        LightRAG · RAG-Anything · LangChain · BGE-M3 · Milvus · Qdrant · NetworkX
Graph Learning  PyTorch Geometric · graph instruction tuning
Multimodal      VLMs · cross-modal alignment · dense embeddings
Evaluation      RAGAS · pairwise LLM judge · NLI grounding signal · manual annotation pipelines
LLM             LoRA/QLoRA (LLaMA-2, GLM-4) · Qwen-7B · prompt engineering
Engineering     Python · Java · Spring Boot · Redis · RabbitMQ · Docker · Linux
ML              TensorFlow/Keras · scikit-learn
```

---

## Awards

|                                                              |              |
| ------------------------------------------------------------ | ------------ |
| 🥇 1st Prize (Beijing) — China Collegiate Computing Contest 2024 | Project Lead |
| 🥈 2nd Prize (Beijing) — China International Innovation Competition 2024 | Project Lead |
| 🥈 2nd Prize — ICT Industry-Education Integration Innovation Contest 2024 | Team Lead    |
| 🥇 1st Prize — 10th National Undergraduate Physics Experiment Competition 2024 | Core Member  |
| 🏅 H Award — MCM/ICM Mathematical Modeling Competition 2023   | Core Member  |
