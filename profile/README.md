# MemQL.ai - The Memory Layer for Trusted AI Systems

<p align="center">
  <img src="https://img.shields.io/badge/status-alpha-orange" alt="Status: Alpha">
  <img src="https://img.shields.io/badge/license-MIT-blue" alt="License: MIT">
  <img src="https://img.shields.io/badge/kubernetes-ready-brightgreen" alt="Kubernetes Ready">
  <img src="https://img.shields.io/badge/multi--tenant-yes-brightgreen" alt="Multi-tenant">
</p>

## 🚀 Welcome to MemQL

MemQL.ai is the persistent memory and knowledge infrastructure that enables AI agents to remember, learn, and comply. We're building the foundational layer that transforms stateless AI into intelligent systems with context, history, and governance.

### Why MemQL?

- **🧠 Persistent Memory**: Give your AI agents long-term memory that persists across conversations
- **🔗 Knowledge Graphs**: Automatically extract entities and relationships from memories
- **🔍 Semantic Search**: Find relevant memories using vector similarity and metadata filtering
- **🏢 Multi-tenant**: Built for teams and organizations with proper isolation
- **📊 Analytics**: Understand how your AI agents use and access information
- **🔒 Compliance Ready**: Built-in audit trails and governance features (coming soon)

## 🎯 Use Cases

- **AI Assistants**: Build assistants that remember user preferences and past interactions
- **Knowledge Management**: Create organizational memory that AI agents can query
- **Customer Support**: Agents that recall previous tickets and customer history
- **Research Tools**: AI that builds knowledge graphs from research documents
- **Compliance Systems**: Track AI decision-making with full audit trails

## 🛠️ Quick Start for Developers

### Install the SDK

```bash
# Python
pip install memql

# JavaScript/TypeScript
npm install @memql/sdk

# Go
go get github.com/memql/memql-go
```

### Basic Usage

```python
from memql import MemQLClient

# Initialize client
client = MemQLClient(
    api_key="your-api-key",
    organization_id="your-org-id"
)

# Store a memory
memory = client.memories.create(
    content="User prefers dark mode and uses VS Code",
    metadata={
        "user_id": "user123",
        "category": "preferences",
        "application": "ide"
    }
)

# Search memories semantically
results = client.memories.search(
    query="What IDE does the user prefer?",
    filters={"user_id": "user123"},
    limit=5
)

# Create knowledge graph relationships
entity = client.entities.create(
    name="VS Code",
    type="software",
    properties={"category": "IDE", "company": "Microsoft"}
)

# Query the knowledge graph
graph_results = client.graph.query(
    cypher="MATCH (u:User)-[:PREFERS]->(s:Software) WHERE s.category = 'IDE' RETURN u, s"
)
```

## 🏗️ Architecture Overview

MemQL.ai is built as a cloud-native, microservices platform:

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│   AI Agents     │     │   Applications  │     │     SDKs        │
└────────┬────────┘     └────────┬────────┘     └────────┬────────┘
         │                       │                         │
         └───────────────────────┴─────────────────────────┘
                                 │
                        ┌────────▼────────┐
                        │   API Gateway   │
                        │   (REST/gRPC)   │
                        └────────┬────────┘
                                 │
        ┌────────────────────────┼────────────────────────┐
        │                        │                        │
┌───────▼────────┐     ┌────────▼────────┐     ┌────────▼────────┐
│ Memory Service │     │ Entity Service  │     │ Graph Service   │
│                │     │                 │     │                 │
│ • Store/Retrieve│     │ • Extract      │     │ • Neo4j         │
│ • Vector Search │     │ • Classify     │     │ • Relationships │
│ • Weaviate     │     │ • Deduplicate  │     │ • Traversal     │
└────────┬────────┘     └────────┬────────┘     └────────┬────────┘
         │                       │                         │
         └───────────────────────┴─────────────────────────┘
                                 │
                        ┌────────▼────────┐
                        │   Event Bus     │
                        │   (Kafka)       │
                        └─────────────────┘
```

## 🚀 Getting Started

### For AI Agent Developers

1. **Sign up for an account** at [memql.ai](https://memql.ai)
2. **Create an organization** and get your API credentials
3. **Install the SDK** for your preferred language
4. **Follow our tutorials**:
   - [Building Your First Memory-Enabled Agent](https://docs.memql.ai/tutorials/first-agent)
   - [Semantic Search Best Practices](https://docs.memql.ai/tutorials/semantic-search)
   - [Knowledge Graph Patterns](https://docs.memql.ai/tutorials/knowledge-graphs)

### For Platform Contributors

1. **Fork the repository**: [github.com/memql/memql.ai](https://github.com/memql/memql.ai)
2. **Set up development environment**:
   ```bash
   git clone https://github.com/YOUR_USERNAME/memql.ai
   cd memql.ai
   make setup
   ```
3. **Read our contribution guide**: [CONTRIBUTING.md](https://github.com/memql/memql.ai/blob/main/CONTRIBUTING.md)
4. **Join our Discord**: [discord.gg/memql](https://discord.gg/memql)

## 📚 Documentation

- **[API Reference](https://docs.memql.ai/api)**: Complete API documentation
- **[SDK Guides](https://docs.memql.ai/sdks)**: Language-specific SDK documentation
- **[Architecture](https://docs.memql.ai/architecture)**: Deep dive into system design
- **[Deployment](https://docs.memql.ai/deployment)**: Self-hosting and cloud options

## 🔧 Core Services

### Memory Service
Stores and retrieves memories with vector embeddings for semantic search. Supports metadata filtering, pagination, and bulk operations.

### Entity Service
Automatically extracts entities (people, places, concepts) from memories using NLP. Handles entity resolution and deduplication.

### Graph Service
Manages relationships between entities in a Neo4j knowledge graph. Supports complex graph queries and traversals.

### Analytics Service
Tracks usage patterns, search queries, and access patterns. Provides insights into how AI agents use memory.

### Organization Service
Manages multi-tenancy, user authentication, and access control. Integrates with Keycloak for enterprise SSO.

## 🛣️ Roadmap

### Current (v0.x - Alpha)
- ✅ Core memory storage and retrieval
- ✅ Vector search with Weaviate
- ✅ Entity extraction and knowledge graphs
- ✅ Multi-tenant architecture
- ✅ REST API and SDKs

### Next (v1.0 - Beta)
- 🚧 Compliance engine with audit trails
- 🚧 Advanced graph algorithms
- 🚧 Real-time memory streaming
- 🚧 Memory versioning and rollback
- 🚧 Enhanced security features

### Future (v2.0+)
- 📋 Federated memory across organizations
- 📋 Memory marketplace
- 📋 Advanced reasoning capabilities
- 📋 AutoML for memory optimization

## 🤝 Community

- **Discord**: [discord.gg/memql](https://discord.gg/memql) - Chat with the team
- **Twitter**: [@memql_ai](https://twitter.com/memql_ai) - Latest updates
- **Blog**: [blog.memql.ai](https://blog.memql.ai) - Technical deep dives
- **Office Hours**: Thursdays 2PM PT - Live Q&A

## 🏢 Enterprise

For enterprise deployments, compliance requirements, or custom features:
- **Email**: enterprise@memql.ai
- **Schedule a demo**: [calendly.com/memql/demo](https://calendly.com/memql/demo)

### Enterprise Features
- 🔒 Advanced compliance and governance
- 🏢 On-premise deployment options
- 📊 Advanced analytics and reporting
- 🔧 Custom integrations
- 💼 SLA and dedicated support

## 📈 Status

- **Platform Status**: [status.memql.ai](https://status.memql.ai)
- **API Health**: All systems operational
- **Current Version**: v0.1.0-alpha

## 📝 License

MemQL.ai is open source under the [MIT License](LICENSE). Some enterprise features may require a commercial license.

---

<p align="center">
  Built with ❤️ by the MemQL team and contributors worldwide
</p>

<p align="center">
  <a href="https://memql.ai">Website</a> •
  <a href="https://docs.memql.ai">Documentation</a> •
  <a href="https://github.com/memql/memql.ai">GitHub</a> •
  <a href="https://discord.gg/memql">Discord</a>
</p>
