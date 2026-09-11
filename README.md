# my-mcp-server

MCP server template I base new tools on

## Usage

```bash
# claude_desktop_config.json  (use ABSOLUTE paths: Claude does not
# run from the repo directory, so a bare "server.py" is not found)
# {
#   "mcpServers": {
#     "notes-box": {
#       "command": "python",
#       "args": ["/abs/path/to/my-mcp-server/server.py"],
#       "env": {"MCP_NOTES_FILE": "/abs/path/to/notes.json"}
#     }
#   }
# }
python server.py --help
```

## Highlights

- Five tools: add / get / update / delete / list notes
- Every tool carries a real docstring, so clients get descriptions
- Includes a Claude Desktop config snippet with absolute paths
- Atomic saves (temp file + os.replace) behind a write lock
- Notes path set by MCP_NOTES_FILE or --notes-file
- A missing note raises instead of returning the string 'not found'

## Getting started

```bash
pip install -r requirements.txt
```

## Project structure

```text
├── .github/
│   ├── workflows/
│   │   └── ci.yml
│   └── dependabot.yml
├── docs/
│   ├── configuration.md
│   ├── roadmap.md
│   └── usage.md
├── tests/
│   └── test_notes.py
├── .gitignore
├── CHANGELOG.md
├── CONTRIBUTING.md
├── requirements.txt
└── server.py
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## 说明

个人练习项目, 谨慎用于生产环境。
