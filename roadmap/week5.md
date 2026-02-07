## Week 5: Custom AI Chatbots and Knowledge Bases (RAG)

---

### Day 29: Customer Support Chatbot and RAG Architecture

#### 📚 Learning Goals
- Vector embeddings concepts
- Vector databases (Pinecone, Weaviate)
- Semantic search
- Chunking strategies
- Embedding models

#### ✅ Tasks & Checklist
- [ ] Learn vector database concepts
- [ ] Set up Pinecone account
- [ ] Learn text chunking strategies
- [ ] Generate embeddings
- [ ] Store vectors in database
- [ ] Perform semantic search
- [ ] Test retrieval quality
- [ ] Optimize chunk size

#### 🛠️ Project Work
**Project 3 Start: Custom ChatGPT for Business**

**Database Schema:**
```sql
CREATE TABLE chatbots (
    id SERIAL PRIMARY KEY,
    user_id INTEGER REFERENCES users(id),
    name VARCHAR(255),
    description TEXT,
    company_name VARCHAR(255),
    pinecone_namespace VARCHAR(255),
    website_url TEXT,
    widget_settings JSONB,
    created_at TIMESTAMP DEFAULT NOW()
);

CREATE TABLE documents (
    id SERIAL PRIMARY KEY,
    chatbot_id INTEGER REFERENCES chatbots(id),
    filename VARCHAR(500),
    content TEXT,
    vector_ids TEXT[], -- Pinecone IDs
    chunk_count INTEGER,
    uploaded_at TIMESTAMP DEFAULT NOW()
);

CREATE TABLE conversations (
    id SERIAL PRIMARY KEY,
    chatbot_id INTEGER REFERENCES chatbots(id),
    session_id VARCHAR(255),
    messages JSONB[],
    user_email VARCHAR(255),
    started_at TIMESTAMP DEFAULT NOW()
);

CREATE TABLE analytics (
    id SERIAL PRIMARY KEY,
    chatbot_id INTEGER REFERENCES chatbots(id),
    metric_name VARCHAR(100),
    metric_value JSONB,
    recorded_at TIMESTAMP DEFAULT NOW()
);
```

**Pinecone Setup:**
```python
# Setup and indexing code
import pinecone
pinecone.init(api_key="YOUR_API_KEY", environment="YOUR_ENV")
index = pinecone.Index("chatbot-index")
```

**Document Processing:**
- [ ] Upload document (PDF, TXT, DOCX)
- [ ] Extract text
- [ ] Split into chunks (500-1000 tokens)
- [ ] Generate embeddings
- [ ] Store in Pinecone
- [ ] Store metadata

#### 📝 Notes & Learnings

**Vector DB Concepts:**
- 
- 

**Chunking Strategy:**
- Chunk size: 
- Overlap: 
- Reasoning: 

**Embedding Model:**
- Model: 
- Dimensions: 
- Cost: 

**Retrieval Quality:**
- Top-k results: 
- Similarity threshold: 

#### 🔗 Resources
- Pinecone: https://www.pinecone.io
- LangChain: https://python.langchain.com

#### 🎯 End of Day Goal
Documents uploaded, chunked, embedded, and searchable

---

### Day 30: Processing and Chunking Custom Knowledge

#### 📚 Learning Goals
- Retrieval Augmented Generation (RAG)
- Prompt engineering for RAG
- Context window management
- Streaming responses
- Conversation memory

#### ✅ Tasks & Checklist
- [ ] Build RAG query pipeline
- [ ] Implement context retrieval
- [ ] Create chat endpoint
- [ ] Add streaming responses
- [ ] Implement conversation memory
- [ ] Add citation/sources
- [ ] Build chat UI
- [ ] Test chatbot quality

#### 🛠️ Project Work
**Project 3 Continue: Chat System**

**RAG Pipeline:**
1. User asks question
2. Generate embedding for question
3. Search Pinecone for relevant chunks
4. Retrieve top 3-5 chunks
5. Build prompt with context
6. Send to Claude
7. Stream response
8. Show sources

**API Endpoints:**
```python
# POST /api/chatbots 
# GET /api/chatbots/:id 
# POST /api/chatbots/:id/upload 
# POST /api/chatbots/:id/chat 
# GET /api/chatbots/:id/analytics
```

**Chat Features:**
- [ ] Retrieve relevant context
- [ ] Generate answer with citations
- [ ] Stream response
- [ ] Show source documents
- [ ] Conversation history (5 messages)
- [ ] Follow-up questions
- [ ] Multi-language support
- [ ] Fallback responses

**Frontend:**
- [ ] Chat interface
- [ ] Message list
- [ ] Input box
- [ ] Typing indicators
- [ ] Source citations
- [ ] Copy response
- [ ] Export conversation

#### 📝 Notes & Learnings

**RAG Prompt:**
```
You are a helpful assistant. Answer based on this context:
{context}

User question: {question}
Answer:
```

**Retrieval Settings:**
- Top-k: 
- Similarity threshold: 
- Max context tokens: 

**Streaming Implementation:**
```python
# Code for streaming
from fastapi.responses import StreamingResponse
async def stream_chat():
    yield "data: word\n\n"
```

**Quality Improvements:**
- 
- 

#### 🎯 End of Day Goal
Working chatbot that answers based on uploaded documents

---

### Day 31: Building the RAG Pipeline (Retrieve and Generate)

#### 📚 Learning Goals
- Embeddable chat widget
- Conversation analytics
- Lead capture
- A/B testing chatbot responses
- Performance optimization

#### ✅ Tasks & Checklist
- [ ] Create embeddable chat widget
- [ ] Add lead capture form
- [ ] Build analytics dashboard
- [ ] Track conversation metrics
- [ ] Add export conversations
- [ ] Create admin interface
- [ ] Optimize response time
- [ ] Deploy chatbot system

#### 🛠️ Project Work
**Project 3 Complete: Widget & Analytics**

**Widget Embedding:**
```html
<script>
  window.ChatbotConfig = {
    chatbotId: 'xxx',
    primaryColor: '#007bff',
    position: 'bottom-right',
    welcomeMessage: 'How can I help?'
  };
</script>
<script src="https://yourapp.com/chatbot-widget.js"></script>
```

**Widget Features:**
- [ ] Floating chat button
- [ ] Chat window
- [ ] Message history
- [ ] Typing indicator
- [ ] Email capture
- [ ] Custom branding
- [ ] Mobile responsive
- [ ] Minimize/maximize

**Analytics:**
- [ ] Total conversations
- [ ] Messages per conversation
- [ ] Average response time
- [ ] User satisfaction (thumbs up/down)
- [ ] Most asked questions
- [ ] Unanswered questions
- [ ] Lead capture rate
- [ ] Popular sources

**Admin Dashboard:**
- [ ] View all conversations
- [ ] Search conversations
- [ ] Flag for review
- [ ] Export to CSV
- [ ] Delete conversations
- [ ] Update documents
- [ ] Widget customization

**Monetization:**
- Free: 100 messages/month
- Basic: $99/month - 1000 messages
- Pro: $299/month - unlimited
- White-label: $999/month

#### 📝 Notes & Learnings

**Widget Communication:**
```javascript
// postMessage implementation
window.parent.postMessage({ type: 'CHAT_MAXIMIZE' }, '*');
```

**Analytics Queries:**
```sql
-- Popular questions
SELECT message, count(*) FROM messages GROUP BY message ORDER BY count(*) DESC LIMIT 10;
```

**Performance:**
- Average response time: 
- Optimization techniques: 

**Deployment:**
- Frontend: 
- Backend: 
- Widget CDN: 

#### 🎯 End of Day Goal
Complete AI chatbot platform with widget, analytics, and billing

---

### Day 32: Handling Conversational Memory and Context

#### 📚 Learning Goals
- Different types of memory (Buffer, Summary, Long-term)
- Session identifiers for tracking conversations
- Database storage for chat history
- Summarization of old messages for context retention

#### ✅ Tasks & Checklist
- [ ] Implement a Postgres-backed chat memory
- [ ] Build a session manager to link user messages
- [ ] Add an AI summarization step for long conversations
- [ ] Test the chatbot's ability to recall earlier user inputs

#### 🛠️ Project Work
**Project 3 Continue: Conversation Manager**
- [ ] Session-based memory logic
- [ ] Database schema for storing full chat transcripts

#### 🎯 End of Day Goal
Chatbot that can hold coherent, multi-turn conversations without losing context.

---

### Day 33: Chatbot UI - Streaming and UI/UX

#### 📚 Learning Goals
- Real-time streaming with Server-Sent Events (SSE)
- Loading states and typing indicators for AI
- Markdown rendering in chat bubbles
- Accessibility (A11y) for chat interfaces

#### ✅ Tasks & Checklist
- [ ] Implement SSE in FastAPI for streaming words
- [ ] Build a React chat bubble with streaming text effect
- [ ] Add a "Stop Generation" button
- [ ] Ensure the chat scrolls to bottom automatically

#### 🛠️ Project Work
**Project 3 Continue: Streaming Chat Interface**

#### 🎯 End of Day Goal
A premium-feeling chat UI that streams responses character-by-character.

---

### Day 34: Multi-tenant Chatbot Architecture

#### 📚 Learning Goals
- Isolating data between different customers
- Managing multiple vector index namespaces
- API Key management for chatbot access
- Resource quotas and usage tracking

#### ✅ Tasks & Checklist
- [ ] Implement Pinecone namespaces for data isolation
- [ ] Build a "Chatbot Management" dashboard for users
- [ ] Generate unique IDs for each distinct chatbot
- [ ] Implement usage limits (e.g., max 5 documents per free bot)

#### 🛠️ Project Work
**Project 3 Continue: SaaS Backend**

#### 🎯 End of Day Goal
A system that can host thousands of different chatbots, each with its own unique knowledge base.

---

### Day 35: Embedding the Chatbot on Websites

#### 📚 Learning Goals
- Building embeddable scripts (CDN delivery)
- Iframe isolation and cross-origin communication
- Customizing widget appearance via JS variables
- Lead capture and analytics integration

#### ✅ Tasks & Checklist
- [ ] Package the React chat widget into a single JS bundle
- [ ] Build a script that injects an iframe into any website
- [ ] Implement custom branding (colors, logos) in the widget
- [ ] Track "Chat Opened" and "Helpful/Not Helpful" metrics

#### 🛠️ Project Work
**Project 3 Complete: Full Support Chatbot SaaS**

#### 🏁 Week 5 Checkpoint:
- [ ] Vector Database (Pinecone) is correctly indexed with document knowledge.
- [ ] RAG pipeline (Retrieve & Generate) is providing accurate, cited answers.
- [ ] Multi-tenant architecture allows isolated chatbots for different users.
- [ ] Chat widget is embeddable on 3rd party sites via a single script.

#### 🎯 End of Day Goal
A chatbot that can be embedded on any 3rd party website with just one line of code.

[Back to index](README.md)
