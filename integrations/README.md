# 🔌 Integrationer

Den här katalogen innehåller The Agency-integrationer och konverterade format för stödda agentiska kodverktyg.

## Stödda verktyg

- **[Claude Code](#claude-code)** — `.md`-agenter, använd repo:t direkt
- **[GitHub Copilot](#github-copilot)** — `.md`-agenter, använd repo:t direkt
- **[Antigravity](#antigravity)** — `SKILL.md` per agent i `antigravity/`
- **[Gemini CLI](#gemini-cli)** — `.md`-agentfiler i `gemini-cli/agents/`
- **[OpenCode](#opencode)** — `.md`-agentfiler i `opencode/`
- **[OpenClaw](#opencLaw)** — `SOUL.md` + `AGENTS.md` + `IDENTITY.md`-arbetsytor
- **[Cursor](#cursor)** — `.mdc`-regel-filer i `cursor/`
- **[Aider](#aider)** — `CONVENTIONS.md` i `aider/`
- **[Windsurf](#windsurf)** — `.windsurfrules` i `windsurf/`
- **[Kimi Code](#kimi-code)** — YAML-agent-specifikationer i `kimi/`
- **[Qwen Code](#qwen-code)** — projektbundna `.md` SubAgents i `.qwen/agents/`
- **[Codex](#codex)** — `.toml`-anpassade agenter i `codex/`
- **[Mistral Vibe](vibe/README.md)** — `.toml`-agenter + promptfiler genererade i `vibe/`
- **Osaurus** — `SKILL.md`-skills genererade i `osaurus/`
- **[Hermes](hermes/README.md)** — lazy-router-plugin genererad i `hermes/`

## Snabbinstallation

```bash
# Installera för alla upptäckta verktyg automatiskt
./scripts/install.sh

# Installera ett specifikt hem-bundet verktyg
./scripts/install.sh --tool antigravity
./scripts/install.sh --tool copilot
./scripts/install.sh --tool openclaw
./scripts/install.sh --tool claude-code
./scripts/install.sh --tool codex
./scripts/install.sh --tool osaurus
./scripts/install.sh --tool hermes

# Gemini CLI behöver genererade integrationsfiler från en ny klon
./scripts/convert.sh --tool gemini-cli
./scripts/install.sh --tool gemini-cli

# Qwen Code behöver också genererade SubAgent-filer från en ny klon
./scripts/convert.sh --tool qwen
./scripts/install.sh --tool qwen
```

Om du installerar OpenClaw och gateway redan körs, starta om det efter installation:

```bash
openclaw gateway restart
```

För projektbundna verktyg som OpenCode, Cursor, Aider, Windsurf och Qwen kör du installeraren från ditt målprojektssökväg enligt exemplen i de verktygsspecifika avsnitten nedan.

## Återskapa integrationsfiler

Om du lägger till eller ändrar agenter, generera om alla integrationsfiler:

```bash
./scripts/convert.sh
```

---

## Claude Code

The Agency designades från början för Claude Code. Agenter fungerar direkt utan konvertering.

```bash
cp -r <category>/*.md ~/.claude/agents/
# eller installera allt på en gång:
./scripts/install.sh --tool claude-code
```

Se [claude-code/README.md](claude-code/README.md) för detaljer.

---

## GitHub Copilot

The Agency fungerar också direkt med GitHub Copilot. Agenter kan kopieras direkt till `~/.github/agents/` och `~/.copilot/agents/` utan konvertering.

```bash
./scripts/install.sh --tool copilot
```

Se [github-copilot/README.md](github-copilot/README.md) för detaljer.

---

## Antigravity

Skills installeras i `~/.gemini/config/skills/`. Varje agent blir en separat skill med prefixet `agency-` för att undvika namnkonflikter.

```bash
./scripts/install.sh --tool antigravity
```

Se [antigravity/README.md](antigravity/README.md) för detaljer.

---

## Gemini CLI

Agenter paketeras som Gemini CLI-subagenter.
Subagenter installeras i `~/.gemini/agents/`.
Eftersom agentfilerna är genererade artefakter, kör `./scripts/convert.sh --tool gemini-cli` innan installation från en ny klon.

```bash
./scripts/convert.sh --tool gemini-cli
./scripts/install.sh --tool gemini-cli
```

Se [gemini-cli/README.md](gemini-cli/README.md) för detaljer.

---

## OpenCode

Varje agent blir en projektbunden `.md`-fil i `.opencode/agents/`.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool opencode
```

Se [opencode/README.md](opencode/README.md) för detaljer.

---

## OpenClaw

Varje agent blir ett OpenClaw-arbetsutrymme med `SOUL.md`, `AGENTS.md` och `IDENTITY.md`.

Innan installation, generera OpenClaw-arbetsutrymmena:

```bash
./scripts/convert.sh --tool openclaw
```

Sedan installera dem:

```bash
./scripts/install.sh --tool openclaw
```

Se [openclaw/README.md](openclaw/README.md) för detaljer.

---

## Cursor

Varje agent blir en `.mdc`-regel-fil. Regler är projektbundna — kör installeraren från projektroten.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool cursor
```

Se [cursor/README.md](cursor/README.md) för detaljer.

---

## Aider

Alla agenter sammanställs i en enda `CONVENTIONS.md`-fil som Aider läser automatiskt när den finns i projektroten.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool aider
```

Se [aider/README.md](aider/README.md) för detaljer.

---

## Windsurf

Alla agenter sammanställs i en enda `.windsurfrules`-fil i projektroten.

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool windsurf
```

Se [windsurf/README.md](windsurf/README.md) för detaljer.

---

## Kimi Code

Varje agent konverteras till en Kimi Code CLI-agent-specifikation (YAML-format med separata systempromptfiler). Agenter installeras i `~/.config/kimi/agents/`.

Eftersom Kimi-agentfilerna genereras från käll-Markdown, kör `./scripts/convert.sh --tool kimi` innan installation från en ny klon.

```bash
./scripts/convert.sh --tool kimi
./scripts/install.sh --tool kimi
```

### Användning

Efter installation kan du använda en agent med flaggan `--agent-file`:

```bash
kimi --agent-file ~/.config/kimi/agents/frontend-developer/agent.yaml
```

Eller i ett specifikt projekt:

```bash
cd /your/project
kimi --agent-file ~/.config/kimi/agents/frontend-developer/agent.yaml \
     --work-dir /your/project
```

Se [kimi/README.md](kimi/README.md) för detaljer.

---

## Qwen Code

Varje agent blir en projektbunden `.md`-SubAgent-fil i `.qwen/agents/`.

Från en ny klon, generera först Qwen-filerna:

```bash
./scripts/convert.sh --tool qwen
```

Sedan installera dem från projektroten:

```bash
cd /your/project && /path/to/agency-agents/scripts/install.sh --tool qwen
```

Se [qwen/README.md](qwen/README.md) för detaljer.

---

## Codex

Varje agent konverteras till en fristående Codex-anpassad agent TOML-fil och installeras i `~/.codex/agents/`.

Eftersom Codex använder genererade TOML-filer i stället för käll-Markdown direkt, kör convertern innan installation från en ny klon:

```bash
./scripts/convert.sh --tool codex
./scripts/install.sh --tool codex
```

Se [codex/README.md](codex/README.md) för detaljer.

