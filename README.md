# 🚀 Bolt - Self-Hosted AI Data Agent

<div align="center">

![Bolt Logo](https://img.shields.io/badge/🚀-Bolt-blue?style=for-the-badge)
[![GitHub Stars](https://img.shields.io/github/stars/Pratik-11/Bolt?style=for-the-badge)](https://github.com/Pratik-11/Bolt/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/Pratik-11/Bolt?style=for-the-badge)](https://github.com/Pratik-11/Bolt/network/members)
[![GitHub Issues](https://img.shields.io/github/issues/Pratik-11/Bolt?style=for-the-badge)](https://github.com/Pratik-11/Bolt/issues)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

**A powerful self-hosted Gen AI agent with integrated MCP server for solving organization data-driven queries and tasks**

[Features](#-features) • [Quick Start](#-quick-start) • [Documentation](#-documentation) • [Contributing](#-contributing) • [Support](#-support)

</div>

---

## 🎯 **What is Bolt?**

Bolt is a cutting-edge **self-hosted AI data agent** that combines the power of **Ollama's local AI models** with **Snowflake's data warehouse** through the **Model Context Protocol (MCP)**. It enables organizations to ask natural language questions about their data and get intelligent, AI-generated SQL queries and insights - all while keeping everything secure and on-premises.

### 🌟 **Why Bolt?**

- 🔒 **Privacy First**: Keep your data and AI processing completely local
- 🧠 **Smart Data Queries**: Natural language to SQL conversion using AI
- 🏢 **Enterprise Ready**: Seamless Snowflake integration for organizational data
- 📊 **Real-time Insights**: Instant data analysis and visualization
- 💰 **Cost Effective**: Self-hosted solution with no external API costs
- 🔧 **Easy Setup**: One-click deployment on Google Colab

---

## ✨ **Features**

### 🤖 **AI-Powered Data Interaction**
- **Natural Language Queries**: Ask questions in plain English about your data
- **Smart SQL Generation**: AI automatically generates optimized Snowflake queries
- **Multiple Model Support**: Choose from 7B to 14B parameter models based on your needs
- **Context-Aware Responses**: Understands your data schema and relationships

### 🔗 **Seamless Integrations**
- **Snowflake Integration**: Direct connection to your Snowflake data warehouse
- **MCP Protocol**: Industry-standard Model Context Protocol implementation
- **Ollama Support**: Local hosting of Llama 2, Mistral, CodeLlama, and more
- **Google Colab Ready**: Zero-setup deployment in cloud notebooks

### 🛡️ **Security & Privacy**
- **On-Premises AI**: No data sent to external AI services
- **Credential Management**: Secure handling of database credentials
- **Environment Isolation**: Containerized execution environment
- **Access Control**: Built-in security best practices

### 📈 **Analytics & Insights**
- **Interactive Results**: Beautiful data visualization and formatting
- **Query History**: Track and reuse previous queries
- **Performance Metrics**: Monitor query execution times and results
- **Export Capabilities**: Save results in multiple formats

---

## 🚀 **Quick Start**

### **Option 1: Google Colab (Recommended)**

1. **Open in Colab**: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

2. **Upload Notebooks**: Upload `model.ipynb` and `mcp.ipynb` to your Colab

3. **Follow the Guided Setup**: 
   - Start with `model.ipynb` to set up Ollama
   - Then run `mcp.ipynb` for Snowflake integration

### **Option 2: Local Setup**

```bash
# Clone the repository
git clone https://github.com/Pratik-11/Bolt.git
cd Bolt

# Install Ollama (Linux/macOS)
curl -fsSL https://ollama.com/install.sh | sh

# Install Python dependencies
pip install snowflake-connector-python==3.0.0 python-dotenv jupyter

# Start Jupyter
jupyter notebook
```

### **Setup Your First Query**

```python
# 1. Start with model setup
# Open model.ipynb and follow the cells to:
# - Install Ollama
# - Download your preferred AI model (7B or 14B)
# - Test the model

# 2. Configure data connection  
# Open mcp.ipynb and:
# - Set up Snowflake credentials
# - Initialize MCP server
# - Test data connectivity

# 3. Ask your first question!
result = ai_with_data.execute_ai_query("Show me top 10 customers by order value")
```

---

## 📚 **Documentation**

### **Architecture Overview**

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   User Query    │───▶│  Ollama AI      │───▶│   Snowflake     │
│ (Natural Lang.) │    │  (SQL Gen.)     │    │   (Data Exec.)  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         ▲                       │                       │
         │                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Formatted     │◀───│  MCP Server     │◀───│   Query Results │
│   Results       │    │  (Orchestrator) │    │   (Raw Data)    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### **Supported Models**

| Model | Size | Memory | Use Case |
|-------|------|--------|----------|
| **Llama 2 7B** | 4-6GB | Colab Free | General purpose, fast responses |
| **Mistral 7B** | 4-6GB | Colab Free | Efficient, multilingual |
| **CodeLlama 7B** | 4-6GB | Colab Free | Code generation, SQL focused |
| **Llama 2 13B** | 8-12GB | Colab Pro | Higher quality, complex queries |
| **CodeLlama 13B** | 8-12GB | Colab Pro | Advanced code generation |

### **Environment Variables**

```bash
# Snowflake Configuration
SNOWFLAKE_USER=your_username
SNOWFLAKE_PASSWORD=your_password
SNOWFLAKE_ACCOUNT=your_account
SNOWFLAKE_DATABASE=your_database
SNOWFLAKE_WAREHOUSE=your_warehouse
```

---

## 🛠️ **Development**

### **Project Structure**

```
Bolt/
├── model.ipynb          # Ollama model setup and configuration
├── mcp.ipynb           # MCP server and Snowflake integration
├── README.md           # Project documentation
├── .gitignore         # Git ignore rules
└── requirements.txt    # Python dependencies (if local setup)
```

### **Key Components**

- **`EmbeddedMCPServer`**: Core MCP server implementation
- **`OllamaWithMCP`**: AI client with data integration
- **Snowflake Connector**: Secure database connectivity
- **Query Generator**: Natural language to SQL conversion

---

## 🤝 **Contributing**

We welcome contributions from the community! Here's how you can help:

### **Ways to Contribute**

- 🐛 **Bug Reports**: Found an issue? [Open an issue](https://github.com/Pratik-11/Bolt/issues)
- 💡 **Feature Requests**: Have an idea? [Start a discussion](https://github.com/Pratik-11/Bolt/discussions)
- 📝 **Documentation**: Improve our docs and examples
- 🧪 **Testing**: Help test new features and edge cases
- 🔧 **Code**: Submit pull requests for bug fixes and features

### **Development Setup**

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Make your changes** and test thoroughly
4. **Commit your changes**: `git commit -m 'Add amazing feature'`
5. **Push to your branch**: `git push origin feature/amazing-feature`
6. **Open a Pull Request**

### **Contribution Guidelines**

- Follow the existing code style and structure
- Add tests for new features
- Update documentation as needed
- Ensure all notebooks run successfully
- Add comments for complex logic

---

## 🧪 **Testing**

### **Manual Testing**

1. **Model Testing**: Verify AI model responses
2. **Database Testing**: Test Snowflake connectivity
3. **Integration Testing**: End-to-end query execution
4. **Performance Testing**: Monitor response times

### **Test Scenarios**

- Simple data queries (SELECT statements)
- Complex analytical queries (JOINs, aggregations)
- Error handling (invalid queries, connection issues)
- Different model sizes and types

---

## 🗺️ **Roadmap**

### **Version 1.1 (Coming Soon)**
- [ ] Support for additional databases (PostgreSQL, MySQL)
- [ ] Web-based UI interface
- [ ] Query result caching
- [ ] Enhanced error handling

### **Version 1.2 (Future)**
- [ ] Multi-tenant support
- [ ] Advanced visualization capabilities
- [ ] API endpoints for external integration
- [ ] Docker containerization

### **Version 2.0 (Vision)**
- [ ] Multi-modal AI support (text + charts)
- [ ] Real-time data streaming
- [ ] Advanced security features
- [ ] Enterprise SSO integration

---

## 👥 **Contributors**

<div align="center">

### **Core Team**

<table>
<tr>
<td align="center">
<a href="https://github.com/Pratik-11">
<img src="https://github.com/Pratik-11.png" width="100px;" alt="Pratik Singh"/>
<br />
<sub><b>Pratik Singh</b></sub>
</a>
<br />
<sub>Creator & Lead Developer</sub>
</td>
</tr>
</table>

### **Want to join this list?** 
Check out our [contributing guidelines](#-contributing) and start contributing today!

</div>

---

## 📄 **License**

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License - Feel free to use, modify, and distribute
Commercial use permitted - Build amazing products with Bolt!
```

---

## 💬 **Support & Community**

### **Get Help**

- 📖 **Documentation**: Check our comprehensive guides above
- 🐛 **Issues**: [GitHub Issues](https://github.com/Pratik-11/Bolt/issues) for bug reports
- 💬 **Discussions**: [GitHub Discussions](https://github.com/Pratik-11/Bolt/discussions) for questions
- 📧 **Email**: For private inquiries and enterprise support

### **Stay Connected**

- ⭐ **Star this repo** to show your support
- 👁️ **Watch** for updates and new releases  
- 🍴 **Fork** to start building your own version
- 📢 **Share** with your team and community

---

## 🙏 **Acknowledgments**

Special thanks to:

- **[Ollama](https://ollama.ai/)** for making local AI accessible
- **[Snowflake](https://snowflake.com/)** for their robust data platform
- **[MCP Protocol](https://modelcontextprotocol.io/)** for standardizing AI-data connections
- **[Google Colab](https://colab.research.google.com/)** for free cloud computing
- **Open Source Community** for inspiration and support

---

<div align="center">

**Made with ❤️ by [Pratik Singh](https://github.com/Pratik-11)**

**Star ⭐ this repo if you find it helpful!**

[![GitHub Stars](https://img.shields.io/github/stars/Pratik-11/Bolt?style=social)](https://github.com/Pratik-11/Bolt/stargazers)

</div>
