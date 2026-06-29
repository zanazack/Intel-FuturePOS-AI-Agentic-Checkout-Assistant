# Intel-FuturePOS-AI-Agentic-Checkout-Assistant

Demo name
Intel FuturePOS AI — Agentic Checkout Assistant
What it demonstrates
A POS terminal running on an Intel PTL / Core Ultra Series 3 edge device that performs:

Product recognition using camera
Basket management
Promotion lookup
Local GenAI assistant
Local policy / inventory RAG
Exception detection
Intel CPU/GPU/NPU telemetry
Optional cloud sync

PTL-class systems are appropriate because Panther Lake / Core Ultra Series 3 platforms combine CPU, integrated Arc GPU, and NPU resources for edge AI workloads, with some edge systems advertised up to 180 TOPS platform AI performance.  OpenVINO is the recommended Intel software layer because it supports conventional AI, GenAI, model optimization, and local deployment across Intel hardware.


Block 1: POS transaction engine
Block 2: Product/catalog/inventory database
Block 3: Camera + vision inference
Block 4: Local GenAI assistant
Block 5: Agentic tool-calling layer
Block 6: React booth UI
Block 7: Intel telemetry + demo control panel

The key is to avoid building a huge monolithic app. Each block should be testable independently.

Target Architecture
Touch POS UI
   |
   v
React Frontend
   |
   v
FastAPI Backend
   |
   +--> POS Basket Engine
   +--> Catalog / Inventory / Promotions DB
   +--> Vision AI Service
   +--> Local RAG Service
   +--> Agentic AI Orchestrator
   +--> Telemetry Service
   |
   v
OpenVINO Runtime
   |
   +--> Intel CPU
   +--> Intel GPU
   +--> Intel NPU where supported
   |
   v
Optional Cloud Sync

OpenVINO GenAI is specifically designed to run generative AI pipelines using OpenVINO Runtime and optimized local execution, which fits the local POS assistant model.  OpenVINO 2026.2 also adds expanded GenAI capabilities, improved GPU model loading, reduced memory usage, and Model Server tool-calling enhancements that are useful for agentic edge workflows. [github.com]
