# Estonia Legal Research MCP Server (`ee-legal-mcp`)

**[Eesti](#lang-et) | [English Documentation](#english-documentation)**

---

<a id="lang-et"></a>
## Õiguslik MCP-server Eesti seadusandluse ja kohtupraktika jaoks (`ee-legal-mcp`) — Eesti

### Selle hoidla kohta

See hoidla sisaldab Model Context Protocol (MCP) serverit, mis ühendab teie AI-rakenduse (Claude Desktop, Cursor, Windsurf, VS Code / Copilot, Cline või Antigravity) otse Riigi Teatajaga (`riigiteataja.ee`) ning Eesti kohtute lahenditega (4 maakohut, 2 halduskohut, Tallinna ja Tartu ringkonnakohtud ning Riigikohus `riigikohus.ee`).

### Kiire paigaldamine (AI-rakenduse valik)

1. **Allalaadimine:** Klõpsake üleval paremal **`<> Code` -> `Download ZIP`** ja pakkige kaust arvutis lahti.
2. **Käivitamine:** Topeltklõpsake **`Click_Here_To_Install_Windows.bat`** (Windows) või **`Click_Here_To_Install_Mac.command`** (macOS).
3. **AI-kliendi valimine:** Märkige kasutatavad AI-programmid (Claude, Cursor, Windsurf, VS Code, Antigravity), klõpsake paigalda ja taaskäivitage oma AI-rakendus.

**Turvamärkus:** Paigaldustööriist töötab ainult lugemisrežiimis (read-only) ega puuduta teie arvutis olevaid isiklikke faile.

### Kohtuastmed ja ametlikud allikad

| Kohtuaste | Hõlmatud kohtud |
|:---|:---|
| **I aste (4 Maakohut ja 2 Halduskohut)** | 4 Maakohtud (Harju, Tartu, Viru, Pärnu County Courts) & 2 Halduskohtud (Tallinn & Tartu Administrative Courts) |
| **II aste (Tallinna ja Tartu Ringkonnakohus)** | 2 Ringkonnakohtud (Tallinna Ringkonnakohus & Tartu Ringkonnakohus — Circuit Courts of Appeal) |
| **III aste (Riigikohus)** | Riigikohus (Supreme Court of Estonia — Civil, Criminal, Administrative & Constitutional Review Chambers) |

- **Riigi Teataja Open API (riigiteataja.ee):** [https://www.riigiteataja.ee](https://www.riigiteataja.ee) (`riigiteataja.ee`, `riigikogu.ee`)
- **Riigi Teataja Kohtulahendid (riigiteataja.ee — All County, Administrative, Circuit & Supreme Court Judgments):** [https://www.riigiteataja.ee/kohtulahendid/](https://www.riigiteataja.ee/kohtulahendid/) (`riigikohus.ee`, `riigiteataja.ee`, `kohus.ee`)

---

<a id="english-documentation"></a>
## English Documentation

Model Context Protocol (MCP) server providing live, read-only access to **Estonia (EE)** legislation, official gazettes, multi-tier judicial decisions (First Instance, Regional/Cantonal/Appellate, and Supreme/Constitutional courts, including HTML and PDF full-text extraction), and statutory citation verification across all major AI clients (**ChatGPT Desktop, OpenAI Codex CLI, Claude Desktop, Claude Code CLI, Cursor, Windsurf, VS Code / GitHub Copilot / Cline / Roo Code, Google Antigravity / Gemini CLI, Perplexity, and Continue.dev**).

---

### Interactive Desktop Setup (Select Your AI Assistant)

This package includes a graphical installer for legal practitioners and non-technical users that lets you select which AI application(s) you use:

1. **Download:** Click **`<> Code`** at the top right of this repository, select **`Download ZIP`**, and extract the folder to your computer.
2. **Run the Setup Utility:**
   - **Windows:** Double-click `Click_Here_To_Install_Windows.bat`
   - **macOS:** Double-click `Click_Here_To_Install_Mac.command`
3. **Select Your AI Client(s) & Connect:** Check the box(es) for the AI assistant(s) installed on your computer (**ChatGPT Desktop & OpenAI Codex CLI**, **Claude Desktop & Claude Code CLI**, **Cursor**, **Windsurf**, **VS Code / GitHub Copilot / Cline / Roo Code**, **Google Antigravity / Gemini CLI**, or **Perplexity / Continue.dev**), click **Install to Selected AI Clients**, and restart your selected AI application.

**System Integrity Note:** The setup utility operates strictly in read-only mode with respect to your personal files and documents. It installs an isolated Python runtime inside the extracted folder and registers the server entry only in the AI client configuration files you select.

---

### Multi-Tier Judicial Hierarchy & Live Indexed National Archives

This server performs live queries across the full judicial hierarchy and official legal archives of **Estonia**, extracting full text from both HTML pages and official court/gazette PDF judgments:

| Judicial Tier | Covered Courts & Tribunals |
|:---|:---|
| **Tier 1 — First Instance** | 4 Maakohtud (Harju, Tartu, Viru, Pärnu County Courts) & 2 Halduskohtud (Tallinn & Tartu Administrative Courts) |
| **Tier 2 — Regional / Cantonal / Appellate** | 2 Ringkonnakohtud (Tallinna Ringkonnakohus & Tartu Ringkonnakohus — Circuit Courts of Appeal) |
| **Tier 3 — Supreme & Constitutional** | Riigikohus (Supreme Court of Estonia — Civil, Criminal, Administrative & Constitutional Review Chambers) |

#### Official Portals & Live Indexed Domains

- **National Legislation & Official Gazette:** Riigi Teataja Open API (riigiteataja.ee) — [https://www.riigiteataja.ee](https://www.riigiteataja.ee)
  - *Indexed Legislation Domains:* `riigiteataja.ee`, `riigikogu.ee`
- **Court Decisions & Jurisprudence Archives:** Riigi Teataja Kohtulahendid (riigiteataja.ee — All County, Administrative, Circuit & Supreme Court Judgments) — [https://www.riigiteataja.ee/kohtulahendid/](https://www.riigiteataja.ee/kohtulahendid/)
  - *Indexed Judicial & Open Case Law Domains:* `riigikohus.ee`, `riigiteataja.ee`, `kohus.ee`

---

### Available MCP Tools

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, decrees, and official gazette publications in Estonia. |
| `search_case_law` | Searches national jurisprudence and open judicial archives for Estonia. |
| `search_tiered_court_decisions` | Filters case law specifically by judicial instance (`first_instance`, `appellate_regional`, `supreme_constitutional`) or specific regional/cantonal/district court. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and supported regional court filters for Estonia. |
| `get_legal_document_markdown` | Retrieves full statutory or judicial texts (both HTML and official `.pdf` court judgments) and converts them into clean Markdown. |
| `verify_citation` | Validates statutory and case law citations against official registries. |

---

<details>
<summary><b>Manual Configuration for Developers (Optional)</b></summary>

```json
{
  "mcpServers": {
    "ee-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/ee-legal-mcp/archive/refs/heads/main.zip",
        "ee-legal-mcp"
      ]
    }
  }
}
```
</details>
