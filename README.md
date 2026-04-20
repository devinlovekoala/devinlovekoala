<div align="center">

# ✨ Hi, I'm Yuxuan Liu ✨

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&duration=3000&pause=1200&color=C0392B&center=true&vCenter=true&multiline=true&width=560&height=60&lines=Graph-Enhanced+RAG+%26+KG+Quality;Multimodal+Understanding+%26+LLM+Agents)](https://git.io/typing-svg)

📍 Beijing, China &nbsp;|&nbsp; 🎓 BUPT (Telecom Engineering)

[![Website](https://img.shields.io/badge/HOMEPAGE-devinlovekoala.github.io-1B3A5C?style=for-the-badge&logo=github)](https://devinlovekoala.github.io)
&nbsp;
[![Demo](https://img.shields.io/badge/LIVE_DEMO-drawsee.cn-C0392B?style=for-the-badge)](http://drawsee.cn)

</div>

---
## About

**ZhaoXi · Drawsee** — a full-stack AI platform for electronics education, led as project owner since 2024. Recognized as a National-Level Innovation & Entrepreneurship project at BUPT.

Four core capabilities set it apart:

- **Circuit-domain multimodal RAG** — a purpose-built pipeline for electronic circuit documents, recovering schematics into structured knowledge rather than treating them as images to caption
- **Professional circuit simulation** — schematic construction and SPICE-level analog simulation driven by Modified Nodal Analysis (MNA) dynamic matrices, with full frontend interactivity
- **LLM × circuit design workflow** — a formal intermediate language bridges natural language and circuit formal representations, enabling LLM reasoning to operate directly on circuit semantics
- **Flow-graph interaction model** — tree-structured conversation graph replacing linear chat, where each response becomes a node users can branch from, explore in parallel, or revisit independently

These four capabilities together surfaced two concrete failure modes in production RAG systems: LLM-driven entity extraction silently introduces noise into knowledge graphs, and multimodal document processing loses critical circuit structure when schematics are treated as images to caption rather than graphs to parse. These problems motivated extensions to two open-source projects from [HKUDS Data Intelligence Lab](https://github.com/HKUDS):

- **[NoiseFilter-RAG](https://github.com/devinlovekoala/NoiseFilter-RAG)** — built on LightRAG, adds confidence scoring and noise-aware retrieval to diagnose and filter graph-level extraction noise. Stage 1: strict precision 0.15 → **0.22**, pairwise win rate 0.4385 → **0.4615**.
- **[CircuitModalProcessor](https://github.com/devinlovekoala/RAG-Anything)** — built on RAG-Anything, converts circuit schematics into first-class KG entities via VLM + netlist parsing instead of caption-only injection. Phase 1: circuit-focused QA **8/8** vs **3/8** baseline.

---

## Research Projects

|      | Project                                                      | Built on                      | Key Result                                                   |
| ---- | ------------------------------------------------------------ | ----------------------------- | ------------------------------------------------------------ |
| 🔬    | **[NoiseFilter-RAG](https://github.com/devinlovekoala/NoiseFilter-RAG)** | HKUDS / LightRAG (EMNLP 2025) | Graph precision 0.15 → **0.22** · Win rate 0.4385 → **0.4615** |
| 🔌    | **[CircuitModalProcessor](https://github.com/devinlovekoala/RAG-Anything)** | HKUDS / RAG-Anything          | Circuit-focused QA **8/8** vs **3/8** baseline               |

## Engineering Projects

|      | Project                                                      | Stack                                | Highlights                                                 |
| ---- | ------------------------------------------------------------ | ------------------------------------ | ---------------------------------------------------------- |
| 🎓    | **[ZhaoXi · 昭析](http://drawsee.cn)**                       | Spring Boot · RAG · LLM Agent        | 500+ users · 73% retention · 🥇 1st Prize Beijing 2024      |
| 🎬    | **[Smart Video Analyzer](https://github.com/devinlovekoala/smart-video-ecosystem)** | Seed1.5-VL · Python                  | 5-pass concurrent VLM pipeline · 100% pipeline reliability |
| ⚡    | **[Drawsee Backend](https://github.com/devinlovekoala/drawsee-backend-java)** | Spring Boot 3 · LangChain4j · Qdrant | Token-budget-aware retrieval · latency ≤ 1.5s              |
| 🖥️    | **[Drawsee Web](https://github.com/devinlovekoala/drawsee-web)** | React · ReactFlow · TypeScript       | Tree-structured conversation · 3-layer streaming render    |

---

## Research Focus
![GraphRAG](https://img.shields.io/badge/GraphRAG-1F3A5F?style=for-the-badge&labelColor=1F3A5F)
![Multimodal](https://img.shields.io/badge/Multimodal_RAG-3C3489?style=for-the-badge&labelColor=3C3489)
![Agents](https://img.shields.io/badge/LLM_Agents-0B6E4F?style=for-the-badge&labelColor=0B6E4F)

![MultiAgent](https://img.shields.io/badge/Multi--Agent_Systems-0B6E4F?style=for-the-badge&labelColor=0B6E4F)
![Preprocessing](https://img.shields.io/badge/Modality_Preprocessing-1F3A5F?style=for-the-badge&labelColor=1F3A5F)


## Tech Stack

**RAG & Knowledge Graphs**

![GraphRAG](https://img.shields.io/badge/GraphRAG-2F3E46?style=flat-square&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-52796F?style=flat-square&logo=langchain&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-52796F?style=flat-square&logoColor=white)
![Milvus](https://img.shields.io/badge/Milvus-52796F?style=flat-square&logoColor=white)
![pgvector](https://img.shields.io/badge/pgvector-52796F?style=flat-square&logo=postgresql&logoColor=white)
![Neo4j](https://img.shields.io/badge/Neo4j-6D597A?style=flat-square&logo=neo4j&logoColor=white)

**LLM & Multimodal**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white)
![scikit--learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)

**Engineering**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-0D1117?style=flat-square&logo=docker&logoColor=2496ED)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white)
