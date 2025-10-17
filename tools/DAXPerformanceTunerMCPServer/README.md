# DAX Performance Tuner

Transform slow DAX queries into lightning-fast optimized code using AI assistance and expert knowledge.

## ⚠️ Important Disclaimer

**Always test optimized DAX queries thoroughly before deploying to production.** While this tool performs semantic equivalence checking to verify that optimized queries return the same results as the original, this validation is **not comprehensive**. The semantic checking:
- Compares results for the specific query context tested
- May not cover all edge cases or data scenarios
- Cannot guarantee identical behavior across all possible filter contexts, user interactions, or data states

## 🎥 Watch It In Action

See the DAX Performance Tuner in action:

[![DAX Performance Tuner Demo](https://img.youtube.com/vi/7CI0oShxGkU/maxresdefault.jpg)](https://www.youtube.com/watch?v=7CI0oShxGkU)

*Click the image above to watch the demo video*

---

## ⚡ Quick Setup

### **Prerequisites**

Before you begin, install:
- ✅ **Python 3.8+** - [Download here](https://python.org/downloads/)
  - Important: Check "Add Python to PATH" during installation
- ✅ **\.NET 8.0 Runtime** - [Download here](https://dotnet.microsoft.com/en-us/download)
  - Choose ".NET 8.0 Runtime" (not SDK)

---

### **Installation Steps**

1. **Download the Distribution**
   
   **Option A: Download Pre-Packaged Zip (Recommended)**
   - Navigate to `tools\DAXPerformanceTunerMCPServer\` in the repository
   - Download the `DAXPerformanceTunerMCPServer_YYYYMMDD.zip` file
   - Extract to your preferred location
   
   **Option B: Clone Full Repository**
   - Click the green "Code" button → "Download ZIP"
   - Extract and navigate to `tools\DAXPerformanceTunerMCPServer\`
   - Use the included zip or run the files directly from this folder

2. **Run Setup**
   - Double-click `setup.bat` (or run `setup.ps1` in PowerShell)
   
   The setup will:
   - ✅ Install required Python packages
   - ✅ Generate MCP configuration in `.vscode/mcp.json`

3. **Start the MCP Server in VS Code**
   - Open VS Code in the extracted `DAXPerformanceTunerMCPServer\` folder
   - Open the `.vscode\mcp.json` file
   - Click the `Start` button over the server name

4. **Use with GitHub Copilot Chat**
   - Open Copilot Chat
   - Ask: **"Help me optimize this DAX query"**
   - The server will automatically provide optimization tools

---

## 📝 Configuration for Other MCP Clients

**For Claude Desktop:**
Add to your `claude_desktop_config.json`:
```json
{
  "mcpServers": {
    "dax-performance-tuner": {
      "command": "C:\\path\\to\\DAXPerformanceTunerMCPServer\\.venv\\Scripts\\python.exe",
      "args": ["src/server.py"]
    }
  }
}
```

**For Other MCP Clients:**
- Command: `{install_path}\.venv\Scripts\python.exe`
- Args: `["src/server.py"]`

---


## 🛠️ Tools You Get

| Tool | What It Does |
|------|--------------|
| `connect_to_dataset` | **Smart connection tool** - Auto-discovers datasets, searches desktop instances, or connects directly based on what info you provide. Works with Power BI Service workspaces AND local Desktop instances. Call with no parameters to discover desktop instances (no auth). Add `location="service"` to discover workspaces instead. |
| `prepare_query_for_optimization` | Complete baseline setup: inline measures, execute baseline, get metadata & research |
| `execute_dax_query` | Test optimization attempts with automatic baseline comparison |
| `get_session_status` | Track your optimization progress, view session history, and get intelligent next step recommendations |

## 🚀 2-Stage Optimization Workflow

**Stage 1 - Connection**: Connect to your Power BI dataset  
**Stage 2 - Comprehensive Optimization**: Complete baseline analysis → Iterative optimization → Performance validation

**What Makes It Powerful:**
- **Research-Driven**: Automatically retrieves targeted optimization articles based on query patterns
- **Evidence-Based**: Deep performance trace analysis with Formula Engine vs Storage Engine breakdown
- **Workflow-Guided**: Systematic 2-stage process ensures comprehensive optimization
- **Iterative**: Multiple optimization rounds achieve compound performance improvements
- **Semantic Validation**: Guarantees optimized queries return identical results to baseline

## 📦 What's Included

- **Pre-built `DaxExecutor.exe`** - No compilation needed, ready to use
- **ADOMD.NET DLLs** - Located in `dotnet/` folder for XMLA connectivity
- **Python MCP Server** - Complete implementation with 4 specialized tools
- **Automated Setup Scripts** - `setup.bat` and `setup.ps1` for easy installation

---

## Attribution & Credits

This project builds upon and references valuable DAX optimization knowledge from the community:

We are grateful for their contributions to the DAX community. See [ATTRIBUTION.md](ATTRIBUTION.md) for detailed third-party content attribution.

**Important**: This project uses dual licensing. See license section below for details.

## License

This project uses **dual licensing**:

### MIT License
Applies to:
- Python MCP server (`src/server.py`, `src/dax_performance_tuner/`)
- Configuration files
- Setup scripts
- Documentation (except third-party content)

### Microsoft Reciprocal License (Ms-RL)
Applies to:
- **C# DAX Executor component** (`src/dax_executor/`)
- This component contains code derived from [DAX Studio](https://github.com/DaxStudio/DaxStudio)
- See `src/dax_executor/LICENSE-MSRL.txt` for full license text

**What this means for users:**
- ✅ You can freely use, modify, and distribute this project
- ✅ Most of the project (Python components) is under permissive MIT license
- ⚠️ If you modify the C# executor component, you must share those changes under Ms-RL
- ℹ️ Ms-RL is an OSI-approved open source license that only requires reciprocal sharing of modifications to Ms-RL files

See `ATTRIBUTION.md` for complete third-party content attribution and licensing details.

---
