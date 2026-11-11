# Juntao Chen — Project Portfolio

**English** | [简体中文](README.zh-CN.md)

> **Portfolio note.** Company confidentiality agreements and patent-related considerations limit what I can disclose, so the original project source code is kept private. This portfolio presents the system architectures, my technical contributions, and the outcomes through screenshots and screen recordings where available.

## Featured Projects

### 01 Medical Rehabilitation Platform

Independently developed a multi-client platform connecting clinician-prescribed plans, patient training, real-time AI feedback, training records and periodic assessments. The project evolved from a multimodal prototype into clinician web, patient Web/H5 and WeChat applications. A two-server deployment separates patient-side real-time and memory-intensive workloads from lighter clinician-side services.

- **Focus:** Real-time video, multimodal integration, speech feedback, training sessions, clinical workflows and cross-server access optimisation.
- **Technology:** FastAPI, React, WeChat Mini Programs, MongoDB / GridFS, OpenCV, multimodal LLM and TTS.
- [Project background, architecture and implementation](projects/medical-rehabilitation.md)

### 02 AI Furniture Design & After-sales Platform

Independently developed a furniture project spanning design tools and after-sales services. The design workflow processes CAD drawings, editable 3D white models and visualisations; the WeChat application handles AI support, service tickets and management analysis.

- **Focus:** CAD image processing, Three.js interaction, generative design workflows, multimodal support and service-ticket lifecycles.
- **Technology:** FastAPI, Three.js, WeChat Mini Programs, PostgreSQL, Redis, vision-language and image-generation services, LLM and ASR.
- [Project background, architecture and implementation](projects/ai-furniture-platform.md)

### 03 Embedded AI Travel Companion & Voice Terminal

A physical embedded project with independently developed terminal applications, supporting services and speech integration. Connects ESP32 hardware, Wi-Fi / 4G, GPS / BLE, map visualisation and an ASR–LLM–TTS pipeline. Following breadboard validation, I designed a PCB and assembled a demo with a 3D-printed enclosure.

- **Focus:** Embedded development, hardware–software integration, streaming audio, device and session management, and location-aware interaction.
- **Technology:** ESP32 / C++, Python, FastAPI, WebSocket, BLE, React maps, ASR and TTS.
- [Project background, architecture and implementation](projects/embedded-ai-companion.md)

## Other Projects

### Visual Recognition & Edge Safety System

**Purpose:** An enterprise visual-safety pipeline covering annotation, training, scenario algorithms, real-time edge analysis and alerts, configured for different clients.

**Architecture:** Data and annotation → training and algorithms → video ingestion and edge inference → event rules and alerts → monitoring and history. Data preparation handles samples, labels and dataset conversion. The model layer trains detectors, implements scenario algorithms and exports deployment-ready models. Services run on edge computing boxes, decoding camera streams, preprocessing frames, executing inference and converting detections into business events.

**Edge deployment:** Debugged and adapted boxes used by different clients, including Houmo, Sophon and Quxin platforms. Work covered runtime environments, SDKs and drivers, model conversion, video ingestion and alerts. Checked input dimensions, preprocessing, output interpretation and scene results within device resource constraints.

**No-code annotation and training platform:** Independently developed a client-facing platform exposing automatic annotation, dataset processing, training and export through visual workflows. Users configure these processes without writing training scripts; outputs feed into edge deployment.

**Module coordination:** The platform organises data preparation and training; algorithms interpret scenes and rules; edge services analyse video; backend and presentation services provide alerts, images and history. Enterprise deliveries are configurations of this project. Related AI laboratory, annotation-centre and industrial-intelligence plans belong to the same project.

**My contribution:** Annotation, selected scenario algorithms, edge-box debugging and adaptation, plus independent development of the no-code platform. A collaborator developed the main system architecture and other core modules.

---

### Hospital Equipment Management & Quality Control System

**Purpose:** Hospital equipment inspections, fault reporting, engineering follow-up and quality-control tracking, with membership in and switching between multiple organisations.

**Architecture:** WeChat Mini Program and management web application → FastAPI → asynchronous SQLAlchemy / PostgreSQL. Redis caches organisational context; ASR and an LLM assist voice-based entry; Word / Excel services generate reports. Records are isolated by organisation and protected by member roles.

**Module coordination:** APIs access equipment, inspections, faults and audits within the selected organisation and role. ASR transcriptions are corrected using equipment lists and terminology rules, then converted into structured entries. Business changes invalidate relevant caches. Faults progress through reporting, assignment and resolution; reports use the same underlying records.

**My contribution:** Independently developed permissions, equipment workflows, fault resolution, assisted entry and reporting.

---

### Yibiao AI Tender Preparation Workbench

**Purpose:** An editable workflow for tender analysis, outline organisation, qualification matching, proposal drafting, document assembly and Word export.

**Architecture:** React / TypeScript workbench → FastAPI → parsing, qualification, drafting and export services → SQLAlchemy / SQLite. A wizard confirms analysis scope, bidding entity and chapters. Dify workflows and LLM services extract requirements, generate chapters, classify qualifications and summarise references. Libraries manage companies, certificates, past work, personnel, products and proposal documents. Document services use python-docx to populate fields, assemble attachments and export formatted files.

**Data flow:** Upload tender → confirm requirements and outline → link bidder and materials → generate and edit chapters → assemble Word document. Project records retain outputs, chapters and materials for continued editing; regression checks cover workflows, business samples and exports.

**My contribution:** Independently developed the front end, back end, document workflows, model integration and business validation.

---

### Customised Purchasing, Sales & Inventory Management System

**Purpose:** A tailored application for a surgical-suture business, including purchasing, sales, stock movements and box-to-pack unit conversion.

**Architecture:** Web client → Python / FastAPI business services → PostgreSQL. ETL scripts import orders, stock-out and sales data, standardising quantities. AI services assist queries and operations; licensing utilities and Windows / macOS scripts support installation and startup.

**Module coordination:** Importers extract orders, stock movements, packaging and sales records, then use master data and conversion rules to normalise quantities into packs. The interface displays boxes and remaining packs. Business services connect inventory, procurement and AI queries; the database stores records and relationships. Licensing and platform scripts manage deployment.

**My contribution:** Independently developed the application, data processing and deployment. Multiple versions are iterations of one project; related multi-agent inventory designs remain exploratory work.

---

### Windows AI Desktop Assistant

**Purpose:** A Windows application supporting speech, memory, tool use, desktop operations and a development-project mode.

**Architecture:** .NET / WinUI 3 main and floating interfaces → host process for data, policies and scheduling → Python sidecar for local wake-word detection, VAD and vector capabilities. Separate workers handle agents, browsers and Windows operations; MCP extends tool access. Model and speech services support streaming.

**Module coordination:** Bootstrap manages child processes. The host maintains personas, history, scheduling and permissions. The sidecar handles local wake-word detection, speech activity and retrieval; an agent worker returns tool plans, while browser and Windows workers execute actions. Personas have separate storage, credentials use Windows DPAPI, and MCP exposes external capabilities.

**My contribution:** Independently developed the application and integrations, including process lifecycles, conversations, tools, memory, installation and releases. Reused components and models remain attributable to their authors.

**Related plugins:** Independently developed persona, cross-session memory, speech and desktop extensions for an existing AI Agent Harness. The plugins connect wake-word detection, VAD, ASR and TTS to workspace conversations, with desktop tools, manual takeover, installation checks and rollback. This work extends an existing product.

---

### Dongce AI Business Management System

**Purpose:** An enterprise AI workbench for customer follow-up, approvals, meeting minutes, weekly reports and cash-flow analysis, with Word, PDF, PowerPoint and Excel generation. Supports local and cloud models and multiple deployment platforms.

**Architecture:** React conversation and management interface → Node.js → agents and tool plugins → SQLite and files. A model adapter connects local LLMs or compatible cloud APIs. Agents invoke tools from conversation context; plugins implement capabilities; storage holds conversations, configurations and business records.

**Module coordination:** Services coordinate model requests and tools, returning results and files to the conversation. Document and media services use browser tools, Poppler and FFmpeg. Configuration manages model connections, plugins and paths. Native Node.js and Docker deployments use startup and health-check scripts to coordinate services.

**My contribution:** Participated in development and iteration: model integration, plugins and tools, document processing, cross-platform operation and deployment validation.

---

### Airport Screen-based Operational Compliance Review

**Purpose:** Reads airport application screens to identify states, parameters and steps, check procedural compliance, and provide exception notifications and review evidence.

**Reference architecture:** Screen capture and window localisation → preprocessing and regions of interest → OCR / control-state recognition → page states and events → workflow state machine and rules → alerts, evidence and review records. This is a feasible reference design for production requirements; specific components remain to be checked against the historical implementation.

- **Capture and localisation:** Capture the target window with timestamps. Locate regions using boundaries, anchors or templates, accounting for resolution, scaling and movement. The capture layer supplies observations to the rules layer.
- **Recognition:** Crop, resize and adjust contrast; use OCR for parameters, modes and messages, and templates or visual recognition for controls. Produce field values, page types, confidence scores and frame references.
- **Events and workflow:** Compare deduplicated frames to infer parameter changes, navigation and confirmations. Multi-frame confirmation and timeouts reduce flicker, pop-up and transient recognition errors. A state machine tracks steps and allowed transitions.
- **Compliance:** Configure order, preconditions, ranges, combined constraints and completion criteria. Evaluate omissions, sequence errors, incorrect parameters and timeouts; flag uncertain recognition for review before a violation judgement.
- **Services and records:** Recognition processes submit events to a review service managing tasks, templates, rule versions and results. Store events and decisions, archive exception screenshots, and display evidence and review outcomes with rule-version traceability.

**My contribution:** Independently developed the production application for screen-based procedural review. Also built a React demo simulating prescribed regions and click sequences; the demo and production recognition system are distinct implementations.

---

### Railway Document Automation Applications

**Purpose:** Exam-question generation, extreme-weather notices and regulation revisions for railway training and document maintenance.

**Architecture:** React / Vite → document parsing or structured inputs → Dify / AI services → editing, comparison and export. The question generator parses DOCX paragraphs and supports editing, regeneration and Excel export. The notice tool builds prompts from organisation, weather, time and route data, then streams formatted drafts. The revision tool handles encodings and chunks, displaying original-to-revised text differences.

**My contribution:** Independently developed document processing, AI integration, interfaces and outputs for all three applications, presented as one series with separate task-specific workflows.

---

### Breakfast Ordering Agent

**Purpose and architecture:** React customer and management interfaces → FastAPI → MongoDB. An LLM invokes menu and order tools; ASR / TTS supports speech; a digital-avatar interface presents replies. Customers can ask questions and order in natural language.

**My contribution:** Independently developed the front end, back end, ordering logic and model / speech integrations.

## Undergraduate Projects

Coursework and practical projects completed during my BSc in Computer Science at Durham University (2021–2024), presented separately from professional work.

| Project | Scope and technology | My contribution |
| --- | --- | --- |
| Clinical Data Analysis & Retinal Image Processing | Pandas / Seaborn analysis of bilateral clinical data from 244 patients; OpenCV perspective correction, denoising, illumination / colour balancing and inpainting | Individual work; preprocessing prepared inputs for an existing classifier |
| CIFAR-100 Classification & Generation | Lightweight PyTorch CNN and convolutional VAE; latent-vector interpolation | Individual work; a 99,022-parameter CNN achieved 40.9% test accuracy after 10,000 optimisation steps |
| Multi-server Load Allocation Simulation | C simulation comparing blocking rates for JSQ, Power-of-d and threshold policies under different service-time distributions | Individual work; nine comparison scenarios |
| IBM EDFLIX Online Learning Platform | PHP, JavaScript, MySQL and WordPress; bookmarks, comments, five-star ratings and personalised recommendations | Team project; developed all front-end, back-end and database components, including porting recommendation logic to PHP |
| Python 3D Rendering & Physics Interaction Engine | Camera control, dynamic lighting, collision detection and physical responses | Individually extended a university-provided engine and built a demonstration scene |

<details>
<summary>Additional coursework: music generation, TCP messaging and the travelling salesman problem</summary>

| Project | Scope and technology | My contribution |
| --- | --- | --- |
| RNN / LSTM Music Generation | Python note and melody sequence modelling; Node.js / Express for search, resources and generated-result interaction | Individual work |
| TCP Multi-client Messaging | Python sockets, TCP and threads; connections, broadcasting, disconnect handling and logs | Individual work |
| Travelling Salesman Search | Python genetic algorithm and A* search; partially matched crossover (PMX) preserves unique cities in routes | Individual work |

</details>
