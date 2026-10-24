# Awesome-Visual-Search-Discovery-API

## Top Visual Search & Discovery API Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Multimodal CLIP Embeddings, E-commerce Product Matching & Self-Hosted Visual Search*  

**Last updated: March 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Visual Search & Discovery APIs**. These tools enable "search by image" — a shopper uploads a photo and the system returns visually similar products, or a user points a camera at an object and gets matching results — using computer vision and vector embeddings rather than keyword matching.



**Examples** include Marqo, VisualMatch, imgsearch, ViSenze, Syte, Clarifai, Google Cloud Vision Product Search, and Nyris (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, CLIP-based matching, and transparent vector search — ideal for e-commerce teams wanting visual search without per-query API fees, and developers who need a search engine they can deploy on their own infrastructure.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **ViSenze** — **The e-commerce visual search specialist.** Offers Search by Image, Automatic Object Recognition (detects fashion items including top, dress, bottom, shoe, bag, watch), and product search by ID with filter queries . **Trained on fashion and retail categories**, with SDKs for JavaScript and mobile. **Best for retailers** wanting a specialized visual search API with automatic object detection and merchandising rules.



- **Syte (by Nayax)** — **The AI product discovery platform for six retail verticals** — fashion, jewelry, home décor, furniture, DIY, and eyewear . **Auto-tags entire catalogs** with visual attributes (color, material, style, shape, occasion) that power on-site filters, search, and even LLM visibility . **Shoppable images, visual & text search, personalized recommendations, cross-sell bundles, and out-of-stock alternatives** . **Vendor-reported 4X CVR uplift and 13% AOV uplift** . **Best for fashion and home retailers** wanting end-to-end discovery with automatic catalog tagging.



- **Clarifai** — **The general-purpose computer vision platform.** Provides image recognition, object detection, and custom model training via gRPC and REST APIs . **Official Python gRPC client** for integrating recognition into applications . **Best for teams needing broad vision capabilities** beyond just visual search, including custom model training.



- **Google Cloud Vision Product Search** — **Google's managed visual product search.** Retailers create products with reference images and add them to product sets; queries return visually and semantically similar results ranked by similarity . **Supports home goods, apparel, toys, packaged goods, and general categories** . **Best for GCP-native retailers** wanting managed visual search integrated with Google Cloud.



## Open-Source GitHub Projects



- **Marqo** — **The open-source tensor search engine that unifies embedding generation and search.** Apache-2.0 licensed, **4,900+ GitHub stars** . **Tensor search** converts documents, images, and other data into vector collections, enabling human-like matching of search requests to files . **Use cases**: user search and recommendation systems, **multimodal search (image-to-image, text-to-image, image-to-text)**, chatbots, and text/image classification . **Integrates HuggingFace CLIP models** for image search — set `model` to a CLIP model and add image URLs as documents . **Runs via Docker**: `docker run --name marqo -it --privileged -p 8882:8882 marqoai/marqo` . **Python client**: `mq.index("my-first-index").add_documents([...])` and `mq.index("my-first-index").search(q="...")` . **Supports lexical search, field-specific search, and custom models** . **Best for teams wanting a self-hosted, general-purpose tensor search engine** with both text and image search capabilities.



- **VisualMatch** — **The AI-powered visual product search engine for e-commerce.** **Uses OpenAI CLIP (`openai/clip-vit-base-patch32`) to match uploaded product photos against a catalog** . **512-dimensional embeddings with cosine similarity search**, achieving **<100ms search latency** via brute-force vector search over pre-computed embeddings . **Instagram DM bot integration** via NovinHub webhooks — customers can find and buy products directly from DMs . **Web dashboard** for catalog management and search testing . **Docker-ready** with one-command deployment . **Best for e-commerce teams** wanting a focused visual product search solution with conversational commerce integration.



- **imgsearch** — **The lightweight reverse image search engine.** **Based on TinyCLIP and HNSWlib**, running on devices with as little as **2GB RAM** . **Supports search by image and search by text description** . **TinyCLIP model selection** ranges from `ViT-8Y` (lowest resource, 41.1% ImageNet accuracy) to `ViT-63LY` (highest accuracy, 64.5%) with `ViT-45LY` as the default balance . **Python client** for programmatic access: `cli.search('./query.jpg', num=5, similarity=80)` returns `(path, similarity%)` tuples . **Database operations** include listing databases, getting info, and clearing . **Best for developers** wanting a minimal, lightweight reverse image search they can embed in applications or run on modest hardware.



### Additional Strong Open-Source Options



- **OmniSearch** — Semantic & visual product discovery using Qdrant/Milvus and HuggingFace CLIP/Sentence-BERT. **Early-stage** (v0.1.0) with FastAPI architecture . Best for teams wanting a modern vector-DB-backed foundation to build on.

- **nearest-image-class** — Image classification and retrieval toolkit using embeddings and FAISS. **Supports DashScope visual embedding models** with SQLite persistence, disk caching, and batch classification . Best for teams wanting a classification-focused visual search pipeline with Chinese cloud model integration.



**Frameworks for building custom systems**: Combine **Marqo** for a general-purpose tensor search engine with text and image search, **VisualMatch** for e-commerce-focused visual product search with Instagram DM integration, **imgsearch** for a lightweight reverse image search on modest hardware, and **ViSenze** or **Syte** if managed visual search with automatic catalog tagging justifies the cost — to build a visual search stack tailored to your catalog size, query latency requirements, and tolerance for self-hosted infrastructure.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Visual search tools differ significantly in embedding model, catalog size ceiling, and deployment model. **Marqo is the most complete open-source option** with both text and image search via CLIP, but requires Docker and a running service . **VisualMatch is e-commerce-focused** with Instagram DM integration, but uses brute-force search over pre-computed embeddings — fine for small-to-medium catalogs, not millions of products . **imgsearch is the lightweight option** running on 2GB RAM, but its TinyCLIP models trade accuracy (41-64% ImageNet) for efficiency . **ViSenze and Syte are managed platforms** with automatic catalog tagging and merchandising rules, at per-query or enterprise pricing . **CLIP-based matching is not the same as exact product matching** — visually similar is not identical, and recall for subtle variations (same shirt, different color) depends on the embedding model.

- Self-hosted open-source solutions require proper Docker configuration, sufficient RAM for the chosen embedding model (CLIP models range from ~100MB to several GB), and a vector index for catalogs beyond a few thousand items.



---



**Made for e-commerce engineers, retail technologists, and developers building visual search and product discovery into their applications.**

Let's make visual search and discovery more open, self-hostable, and catalog-aware.
