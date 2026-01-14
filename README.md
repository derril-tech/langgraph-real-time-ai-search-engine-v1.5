# 🔍 Real-Time AI Search Engine
**Powered by LangGraph + OpenAI + RAG**

> **Ask anything. Get a cited answer—fast.** A production-grade, Perplexity-style research assistant that combines real-time web retrieval, intelligent source ranking, and streaming AI synthesis with inline citations. ⚡

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![Next.js](https://img.shields.io/badge/Next.js-16-black.svg)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.2-61DAFB.svg)](https://react.dev/)
[![LangGraph](https://img.shields.io/badge/LangGraph-RAG_Orchestration-purple.svg)](https://langchain-ai.github.io/langgraph/)
[![Railway](https://img.shields.io/badge/Deploy-Railway-blueviolet.svg)](https://railway.app/)
[![Vercel](https://img.shields.io/badge/Deploy-Vercel-black.svg)](https://vercel.com/)

---

## ✨ What It Does

This is a **production-grade AI search engine** that demonstrates advanced RAG (Retrieval-Augmented Generation) orchestration:

1. **Real-Time Web Retrieval** — Queries Serper or Brave Search for fresh web results
2. **Intelligent Source Ranking** — Heuristic-based ranking with domain quality analysis
3. **Streaming AI Synthesis** — GPT-4.1-mini generates answers with inline citations in real-time
4. **Source Grounding** — Every claim is backed by ranked sources with visual credibility indicators
5. **Conversational Continuity** — Continue the conversation with AI after receiving answers

All delivered through a **streaming UI** that feels instant and responsive, with no page reloads.

---

## 🎯 Core Features

### 🤖 **RAG Pipeline & Retrieval Orchestration**
- **Multi-Stage Retrieval** — Search → Fetch → Extract → Rank → Synthesize pipeline
- **Intelligent Source Ranking** — Domain authority, content quality, and relevance scoring
- **Source Credibility Analysis** — Visual indicators for source quality and trustworthiness
- **Citation Grounding** — Inline citations [1], [2] with source verification
- **Cache-Aware Retrieval** — Redis caching for search results and fetched content

### 💬 **AI-Powered Interactions**
- **Streaming Answers** — Real-time answer generation with token-level streaming
- **AI Chat Follow-up** — Continue conversations with context-aware responses
- **Real-Time Search Suggestions** — AI-generated query suggestions as you type
- **Follow-up Questions** — Intelligent suggestions to explore topics deeper
- **Related Searches** — Discover related queries automatically

### 📊 **Search Intelligence**
- **Search History** — View and revisit past searches with AI-generated tags and filters
- **Search Collections** — Organize searches into custom collections with full CRUD operations
- **Collection Management** — Create, view, and delete collections with confirmation dialogs
- **Multi-Query Comparison** — Side-by-side comparison of multiple search results
- **Search Analytics** — Usage patterns, popular topics, and search insights
- **Export & Share** — Export answers as Markdown/Text or generate shareable links

### 🎨 **Production-Grade UX**
- **Streaming UI** — Smooth, real-time answer rendering with no page reloads
- **Perplexity-Like Interface** — Clean, focused design optimized for research
- **Dark/Light Mode** — Beautiful theme system with system preference support
- **Mobile-First** — Fully responsive design with 44px+ touch targets (WCAG compliant)
- **Tablet Optimized** — Optimized layouts and interactions for tablet devices
- **Keyboard Shortcuts** — Power user features for faster navigation (`/`, `Ctrl+K`, `Esc`, `?`)
- **Accessibility** — ARIA labels, focus management, keyboard navigation
- **Loading States** — Animated progress indicators and status messages for better UX

### 🔧 **Advanced Features**
| Feature | Description |
|---------|-------------|
| 🔍 **Streaming Search** | Real-time answer streaming with citations |
| 📚 **Source Panel** | Ranked sources with credibility scores |
| 💬 **AI Chat** | Context-aware follow-up conversations |
| 🎯 **Search Suggestions** | AI-generated query suggestions as you type |
| 🏷️ **AI Tagging** | Automatic search categorization |
| 📊 **Analytics Dashboard** | Search patterns and insights |
| 📦 **Collections** | Create, view, and delete collections |
| 🗑️ **Collection Management** | Full CRUD with confirmation dialogs |
| 🔄 **Multi-Query Compare** | Side-by-side result comparison |
| 📤 **Export & Share** | Markdown/Text export and shareable links |
| ⌨️ **Keyboard Shortcuts** | Power user navigation (`/`, `Ctrl+K`, `Esc`, `?`) |
| 🔗 **Related Searches** | Discover related topics (mobile-optimized) |
| 📱 **Mobile Optimized** | Responsive design with touch-friendly UI |

---

## 🏗️ Tech Stack

### **Frontend** ⚛️
| Technology | Purpose |
|------------|---------|
| **Next.js 16** | React 19.2 with App Router & Edge Runtime |
| **TypeScript** | Type-safe development with strict mode |
| **Tailwind CSS** | Utility-first styling with custom design system |
| **shadcn/ui** | Accessible component library |
| **React 19.2** | Latest React with Server Components |
| **Lucide Icons** | Modern icon set |

### **Backend** 🐍
| Technology | Purpose |
|------------|---------|
| **FastAPI** | High-performance async Python API |
| **LangGraph** | RAG orchestration and retrieval pipeline |
| **OpenAI GPT-4.1-mini** | Answer synthesis with citations |
| **Pydantic v2** | Data validation and serialization |
| **Async/Await** | Non-blocking I/O for performance |

### **Data & Cache** 💾
| Technology | Purpose |
|------------|---------|
| **Supabase** | PostgreSQL with schema-qualified tables |
| **Upstash Redis** | Caching, rate limiting, and session management |
| **pgvector** | Vector embeddings (optional, for future enhancements) |

### **External APIs** 🔌
| API | Purpose |
|-----|---------|
| **Serper / Brave Search** | Real-time web search results |
| **OpenAI** | GPT-4.1-mini for synthesis and chat |

### **Deployment** 🚀
| Platform | Service |
|----------|---------|
| **Vercel** | Frontend hosting with Edge Functions |
| **Railway** | Backend API deployment |

---

## 🔄 How It Works

### RAG Pipeline Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    USER QUERY                                │
│         "What is React Server Components?"                   │
└─────────────────────┬───────────────────────────────────────┘
                      │
                      ▼
┌─────────────────────────────────────────────────────────────┐
│              RETRIEVAL ORCHESTRATION                        │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Web        │  │   Source     │  │   Source     │      │
│  │   Search     │──│   Fetching   │──│   Ranking    │      │
│  │  (Serper/    │  │  (HTTP +     │  │  (Heuristics │      │
│  │   Brave)     │  │   Extract)   │  │   + Domain)  │      │
│  └──────────────┘  └──────────────┘  └──────┬───────┘      │
│                                             │               │
│                                    ┌────────▼────────┐      │
│                                    │   RAG          │      │
│                                    │   Synthesis    │      │
│                                    │  (OpenAI +     │      │
│                                    │   Citations)   │      │
│                                    └────────┬────────┘      │
└─────────────────────────────────────────────┼───────────────┘
                                              │
                                              ▼
┌─────────────────────────────────────────────────────────────┐
│              STREAMING RESPONSE                             │
│  • Answer with inline citations [1], [2]                   │
│  • Ranked source list with credibility scores               │
│  • Follow-up question suggestions                           │
│  • Related search recommendations                           │
└─────────────────────────────────────────────────────────────┘
```

### Detailed Flow

1. **Query Submission** — User submits question via playground UI
2. **Web Search** — System queries Serper/Brave Search API (cached in Redis)
3. **Source Fetching** — Top N results fetched and extracted (HTML → text, cached)
4. **Source Ranking** — Heuristic-based ranking (domain quality, content length, provider rank)
5. **RAG Synthesis** — LLM generates answer with inline citations using retrieved sources
6. **Streaming** — Answer streams to UI via Next.js Edge route (Server-Sent Events)
7. **Persistence** — Query, sources, citations, and messages saved to Supabase
8. **Follow-ups** — AI generates contextual follow-up questions

---

## 📸 Key Highlights

### 🎮 Playground Interface
*Streaming search interface with real-time answer generation, inline citations, and ranked sources*

### 📊 Source Analysis
*Visual credibility indicators, domain information, and source ranking with detailed metadata*

### 💬 AI Chat Continuation
*Context-aware follow-up conversations that maintain search context and conversation history*

### 📱 Mobile Experience
*Fully responsive design with optimized touch targets, mobile navigation, and smooth interactions*

### 🎨 Modern Design System
*Consistent theming, smooth animations, and accessibility-first approach*

---

## 📖 User Guide

### Getting Started

1. **Enter Your Question** — Type any research question in the playground
2. **Watch It Stream** — See the answer generate in real-time with citations
3. **Explore Sources** — Review ranked sources with credibility indicators
4. **Continue Conversation** — Ask follow-up questions with AI chat
5. **Save & Organize** — Create collections and export answers

### Understanding Your Results

| Section | What It Shows |
|---------|---------------|
| **Answer** | Comprehensive answer with inline citations [1], [2] |
| **Sources Panel** | Ranked sources with credibility scores and domain info |
| **Follow-up Questions** | AI-generated questions to explore the topic deeper |
| **Related Searches** | Discover related queries automatically (mobile-optimized) |
| **Search History** | View past searches with AI-generated tags and filters |
| **Collections** | Create, view, and manage custom collections |
| **Collection Items** | View all searches saved in a collection |

### Pro Tips

- **Be specific** with your questions for better results
- **Use citations** to verify claims by clicking citation badges in the answer
- **Explore follow-ups** to dive deeper into topics
- **Create collections** to organize research by topic
- **Delete collections** when no longer needed (with confirmation)
- **Use keyboard shortcuts** for faster navigation (press `?` for help)
- **Filter search history** by tags or search terms
- **Export answers** to save or share your research

---


## 📊 Performance & Architecture

### Performance Metrics

| Metric | Value |
|--------|-------|
| **Answer Generation** | ~10-20 seconds (streaming) |
| **Source Retrieval** | ~2-5 seconds (cached) |
| **Frontend Bundle** | Optimized with Next.js 16 |
| **Mobile Ready** | ✅ WCAG compliant, 44px+ touch targets |
| **Tablet Optimized** | ✅ Responsive layouts and interactions |
| **Lighthouse Score** | 90+ |
| **Loading Feedback** | ✅ Animated progress indicators |

### Architecture Highlights

- **Edge Runtime** — Next.js Edge Functions for low-latency streaming
- **Async Pipeline** — Non-blocking I/O throughout the stack
- **Intelligent Caching** — Redis caching for search results and fetched content
- **Rate Limiting** — IP-based rate limiting (20 requests/minute)
- **Error Handling** — Comprehensive error handling with graceful fallbacks
- **Schema Isolation** — Supabase schema-qualified tables for multi-tenancy

---

## 🛡️ Security & Best Practices

- ✅ **API Rate Limiting** — 20 requests/minute per IP
- ✅ **CORS Protection** — Secure cross-origin requests
- ✅ **Environment Variables** — All secrets in environment variables
- ✅ **Input Validation** — Pydantic models for all inputs
- ✅ **Schema Isolation** — Database schema isolation for security
- ✅ **Error Sanitization** — No sensitive data in error messages
- ✅ **HTTPS Only** — All production endpoints use HTTPS

---

## 🎨 Customization

### Theme Options
- ☀️ **Light Mode** — Clean, professional interface
- 🌙 **Dark Mode** — Easy on the eyes (default)
- 🖥️ **System** — Follows OS preference

### Search Options
- **Search Provider** — Choose between Serper or Brave Search
- **Result Count** — Configurable number of sources (default: 5)
- **Fetch Depth** — Number of sources to fetch content from (default: 3)

---

## 📚 Documentation

- **[ENV_VARIABLES.md](ENV_VARIABLES.md)** — Complete environment variable reference
- **[RAILWAY_ENV_VARIABLES.md](RAILWAY_ENV_VARIABLES.md)** — Railway deployment environment variables
- **[PRODUCTION_TESTING_GUIDE.md](PRODUCTION_TESTING_GUIDE.md)** — Comprehensive production testing checklist
- **[LLM_PROMPT_IMPROVEMENTS.md](LLM_PROMPT_IMPROVEMENTS.md)** — Prompt engineering details
- **[DEPLOYMENT_SYNC_EXPLANATION.md](DEPLOYMENT_SYNC_EXPLANATION.md)** — Vercel/Railway deployment behavior
- **[DEPLOYMENT_NOT_TRIGGERING_FIX.md](DEPLOYMENT_NOT_TRIGGERING_FIX.md)** — Troubleshooting deployment issues

---

## 🏗️ Technical Highlights

This project demonstrates:

- **🤖 RAG Architecture** — Complete retrieval-augmented generation pipeline
- **⚛️ Modern React** — Next.js 16, React 19.2, Server Components, Edge Runtime
- **🐍 Python Backend** — FastAPI, async/await, Pydantic v2, LangGraph
- **🎨 Production UX** — Streaming UI, responsive design, accessibility
- **☁️ Cloud Architecture** — Supabase, Redis, Railway, Vercel
- **🔧 DevOps** — CI/CD, environment management, monitoring
- **📊 Data Engineering** — Schema design, caching strategies, rate limiting

---

## 🙏 Acknowledgments

- **[LangGraph](https://langchain-ai.github.io/langgraph/)** — RAG orchestration framework
- **[OpenAI](https://openai.com/)** — GPT-4.1-mini API
- **[Serper](https://serper.dev/)** & **[Brave Search](https://brave.com/search/api/)** — Web search APIs
- **[Supabase](https://supabase.com/)** — PostgreSQL database
- **[Upstash](https://upstash.com/)** — Redis caching
- **[Railway](https://railway.app/)** — Backend deployment
- **[Vercel](https://vercel.com/)** — Frontend hosting
- **[shadcn/ui](https://ui.shadcn.com/)** — Component library

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">



[Live Demo](https://langgraph-real-time-ai-search-engin.vercel.app/)

Made with ❤️ and ☕ by [Derril Filemon](https://github.com/derril-tech)

</div>
