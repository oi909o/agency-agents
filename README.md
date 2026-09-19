# 🎭 The Agency: AI-specialister redo att förändra ditt arbetsflöde

> **En komplett AI-byrå i din hand** — från frontend-wizards till Reddit-community-ninjor, från whimsy-injectors till reality-checkers. Varje agent är en specialiserad expert med personlighet, processer och beprövade leveranser.

[![GitHub stars](https://img.shields.io/github/stars/msitarzewski/agency-agents?style=social)](https://github.com/msitarzewski/agency-agents)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://makeapullrequest.com)
[![Sponsor](https://img.shields.io/badge/Sponsor-%E2%9D%A4-pink?logo=github)](https://github.com/sponsors/msitarzewski)
[![Download the app](https://img.shields.io/github/v/release/msitarzewski/agency-agents-app?label=Download%20app&color=2563eb)](https://github.com/msitarzewski/agency-agents-app/releases/latest)

> ### 🆕 Det finns nu en app
> >
> > **[Agency Agents](https://agencyagents.app)** är en native app för **macOS, Linux & Windows** som bläddrar igenom hela rostern och installerar den i Claude Code, Cursor, Codex, Gemini, Osaurus och andra verktyg.
> >
> > **→ [Ladda ner senaste releasen](https://github.com/msitarzewski/agency-agents-app/releases/latest) · [agencyagents.app](https://agencyagents.app)**

---

## 🚀 Vad är detta?

Fött ur en Reddit-tråd och månader av iteration är **The Agency** en växande samling av noggrant formulerade AI-agentpersonligheter. Varje agent är:

- **🎯 Specialiserad**: Djup expertis inom sitt område (inte generiska promptmallar)
- **🧠 Personlighetsdriven**: Unik röst, kommunikationsstil och angreppssätt
- **📋 Leveransfokuserad**: Verklig kod, processer och mätbara resultat
- **✅ Produktionsklar**: Beprövade arbetsflöden och framgångskriterier

**Tänk på det som**: att bygga ditt drömteam, fast agenterna är AI-specialister som aldrig sover, aldrig klagar och alltid levererar.

---

## ⚡ Snabbstart

### Alternativ 1: Installera appen (rekommenderat)

Det snabbaste sättet in — inget kloning, ingen terminal. [**Agency Agents**](https://agencyagents.app) är en native skrivbordsapp (macOS · Linux · Windows) som bläddrar genom hela rostern och installerar agenter i de mest populära arbetsverktygen.

**[⬇ Ladda ner senaste versionen](https://github.com/msitarzewski/agency-agents-app/releases/latest)** — eller på en Mac:

```bash
brew install --cask msitarzewski/agency-agents/agency-agents
```

Föredrar du kommandoraden? Alternativen nedan med scripts installera samma agenter.

### Alternativ 2: Använd med Claude Code

```bash
# Installera alla agenter i din Claude Code-katalog
./scripts/install.sh --tool claude-code

# Eller kopiera manuellt en kategori om du bara vill ha en division
cp engineering/*.md ~/.claude/agents/

# Sen kan du aktivera vilken agent som helst i dina Claude Code-sessioner:
# "Hej Claude, aktivera Frontend Developer-läget och hjälp mig bygga en React-komponent"
```

### Alternativ 3: Använd som referens

Varje agentfil innehåller:
- Identitet & personlighet
- Kärnuppdrag & arbetsflöden
- Tekniska leveranser med kodexempel
- Framgångsmetoder & kommunikationsstil

Bläddra bland agenterna nedan och kopiera/anpassa de du behöver.

### Alternativ 4: Använd med andra verktyg (GitHub Copilot, Antigravity, Gemini CLI, OpenCode, OpenClaw, Cursor, Aider, Windsurf, Kimi Code, Codex, Osaurus, Hermes, Mistral Vibe)

```bash
# Steg 1 -- generera integrationsfiler för alla stödda verktyg
./scripts/convert.sh

# Steg 2 -- installera interaktivt (auto-detekterar vad du har installerat)
./scripts/install.sh

# Eller riktas ett specifikt verktyg direkt
./scripts/install.sh --tool antigravity
./scripts/install.sh --tool gemini-cli
./scripts/install.sh --tool opencode
./scripts/install.sh --tool copilot
./scripts/install.sh --tool openclaw
./scripts/install.sh --tool cursor
./scripts/install.sh --tool aider
./scripts/install.sh --tool windsurf
./scripts/install.sh --tool kimi
./scripts/install.sh --tool codex
./scripts/install.sh --tool osaurus
./scripts/install.sh --tool hermes
./scripts/install.sh --tool vibe
```

**Installera bara de team du behöver** (inte alla vill ha varje division):

```bash
./scripts/install.sh                                    # interaktiv guide: välj verktyg + team
./scripts/install.sh --tool claude-code --division engineering,security
./scripts/install.sh --tool cursor --agent frontend-developer,ui-designer
./scripts/install.sh --list teams                       # se varje team + antal agenter
./scripts/install.sh --tool opencode --division engineering --dry-run
```

> **OpenCode-notering:** OpenCodes runtime registrerar för närvarande bara ungefär 119 agenter och slutar tyst med resten ([upstream bug](https://github.com/anomalyco/opencode/issues/27988)). Att installera en delmängd fungerar bra, men var medveten om detta.

Se [Multi-Tool Integrations](#-multi-tool-integrations) för full detalj.

---

## 🤝 Bidra

Vi välkomnar bidrag! Så här kan du hjälpa till:

### Lägg till en ny agent

1. Forka repot
2. Skapa en ny agentfil i rätt kategori
3. Följ agentmallens struktur:
   - Frontmatter med namn, beskrivning, färg
   - Identity & Memory-sektion
   - Core Mission
   - Critical Rules (domänspecifika)
   - Technical Deliverables med exempel
   - Workflow Process
   - Success Metrics
4. Skicka in en PR med din agent

### Förbättra befintliga agenter

- Lägg till verkliga exempel
- Förbättra kodexempel
- Uppdatera framgångsmetoder
- Förbättra arbetsflöden

### Dela dina framgångsberättelser

Har du använt dessa agenter med framgång? Dela din historia i [Diskussioner](https://github.com/msitarzewski/agency-agents/discussions).

---

## 📖 Agentdesignfilosofi

Varje agent är designad med:

1. **🎭 Stark personlighet**: Inte generiska mallar — riktig karaktär och röst
2. **📋 Klara leveranser**: Konkret resultat, inte vaga råd
3. **✅ Framgångsmetoder**: Mätbara utfall och kvalitetsstandarder
4. **🔄 Beprövade arbetsflöden**: Steg-för-steg-processer som fungerar
5. **💡 Lärande minne**: Mönsterigenkänning och kontinuerlig förbättring

---

## 🎁 Vad gör detta speciellt?

### Till skillnad från generiska AI-prompts:
- ❌ Generiska "Fungera som utvecklare"-prompts
- ✅ Djup specialisering med personlighet och process

### Till skillnad från promptbibliotek:
- ❌ Engångsprompt-samlingar
- ✅ Omfattande agentsystem med arbetsflöden och leveranser

### Till skillnad från AI-verktyg:
- ❌ Svarta lådor du inte kan anpassa
- ✅ Transparenta, forkbara, anpassningsbara agentpersonligheter

---

## 🎨 Personlighetshöjdpunkter för agenter

> "Jag testar inte bara din kod — jag defaultar till att hitta 3–5 problem och kräver visuell bevisning för allt."
> 
> -- **Evidence Collector** (Testing Division)

> "Du marknadsför inte på Reddit — du blir en värdefull medlem i gemenskapen som råkar representera ett varumärke."
> 
> -- **Reddit Community Builder** (Marketing Division)

> "Varje lekfullt element måste tjäna ett funktionellt eller känslomässigt syfte. Designa glädje som förbättrar snarare än distraherar."
> 
> -- **Whimsy Injector** (Design Division)

> "Låt mig lägga till en firande animation som minskar uppgiftsslutförandebesvär av 40 %."
> 
> -- **Whimsy Injector** (vid UX-granskning)

---

## 📊 Statistik

- 🎭 **230+ specialiserade agenter** i varje division
- 📝 **10 000+ rader** av personlighet, processer och kodexempel
- ⏱️ **Månader av iteration** från verklig användning
- 🌟 **Beprövade i produktion**
- 💬 **50+ förfrågningar** i de första 12 timmarna på Reddit

---

## 🔌 Multi-verktygsintegrationer

The Agency fungerar nativt med Claude Code och levererar konverterings- och installationsskript så att du kan använda samma agenter i de flesta större agentiska kodverktyg.

### Stödda verktyg

- **[Claude Code](https://claude.ai/code)** — native `.md`-agenter, ingen konvertering behövs → `~/.claude/agents/`
- **[GitHub Copilot](https://github.com/copilot)** — native `.md`-agenter, ingen konvertering behövs → `~/.github/agents/` + `~/.copilot/agents/`
- **[Antigravity](https://github.com/google-gemini/antigravity)** — `SKILL.md` per agent → `~/.gemini/config/skills/`
- **[Gemini CLI](https://github.com/google-gemini/gemini-cli)** — `.md`-agentfiler → `~/.gemini/agents/`
- **[OpenCode](https://opencode.ai)** — `.md`-agentfiler → `.opencode/agents/`
- **[Cursor](https://cursor.sh)** — `.mdc`-regelfiler → `.cursor/rules/`
- **[Aider](https://aider.chat)** — en enda `CONVENTIONS.md` → `./CONVENTIONS.md`
- **[Windsurf](https://codeium.com/windsurf)** — en enda `.windsurfrules` → `./.windsurfrules`
- **[OpenClaw](https://github.com/openclaw/openclaw)** — `SOUL.md` + `AGENTS.md` + `IDENTITY.md` per agent
- **[Qwen Code](https://github.com/QwenLM/qwen-code)** — `.md` SubAgent-filer → `~/.qwen/agents/`
- **[Kimi Code](https://github.com/MoonshotAI/kimi-cli)** — YAML-agent-specifikationer → `~/.config/kimi/agents/`
- **[Codex](https://developers.openai.com/codex/overview)** — TOML-anpassade agenter → `~/.codex/agents/`
- **Osaurus** — `SKILL.md`-skills → `~/.osaurus/skills/`
- **[Hermes](integrations/hermes/README.md)** — lazy-router-plugin → `~/.hermes/plugins/`

---

### ⚡ Snabbinstallation

**Steg 1 — Generera integrationsfiler:**
```bash
./scripts/convert.sh
# Snabbare (parallell, utdataordningen kan variera): ./scripts/convert.sh --parallel
```

**Steg 2 — Installera (interaktivt, auto-detekterar dina verktyg):**
```bash
./scripts/install.sh
# Snabbare (parallell, utdataordningen kan variera): ./scripts/install.sh --no-interactive --parallel
```

Installationsprogrammet skannar ditt system efter installerade verktyg, visar en kryssruta och låter dig välja exakt vad du vill installera.

**Eller installera ett specifikt verktyg direkt:**
```bash
./scripts/install.sh --tool cursor
./scripts/install.sh --tool opencode
./scripts/install.sh --tool openclaw
./scripts/install.sh --tool antigravity
./scripts/install.sh --tool codex
./scripts/install.sh --tool osaurus
./scripts/install.sh --tool hermes
```

**Icke-interaktivt (CI/scripts):**
```bash
./scripts/install.sh --no-interactive --tool all
```

**Snabbare körningar (parallell)** — på maskiner med flera kärnor kan du använda `--parallel` så att varje verktyg processas parallellt. Utdataordningen mellan verktyg är icke-deterministisk. Det fungerar både med interaktiv och icke-interaktiv läge.

```bash
./scripts/convert.sh --parallel                    # konvertera alla verktyg i parallell
./scripts/convert.sh --parallel --jobs 8           # begränsa parallelljobb
./scripts/install.sh --no-interactive --parallel   # installera alla upptäckta verktyg parallellt
./scripts/install.sh --interactive --parallel      # välj verktyg och installera sedan parallellt
./scripts/install.sh --no-interactive --parallel --jobs 4
```

---

### Verktygsspecifika instruktioner

<details>
<summary><strong>Claude Code</strong></summary>

Agenter kopieras direkt från repot till `~/.claude/agents/` — ingen konvertering krävs.

```bash
./scripts/install.sh --tool claude-code
```

Använd sedan agenter i Claude Code:
```
Använd Frontend Developer-agenten för att granska denna komponent.
```

Se [integrations/claude-code/README.md](integrations/claude-code/README.md) för detaljer.
</details>

<details>
<summary><strong>GitHub Copilot</strong></summary>

Agenter kopieras direkt från repot till `~/.github/agents/` och `~/.copilot/agents/` — ingen konvertering krävs.

```bash
./scripts/install.sh --tool copilot
```

Använd sedan agenter i GitHub Copilot:
```
Använd Frontend Developer-agenten för att refaktorisera denna komponent.
```

Se [integrations/github-copilot/README.md](integrations/github-copilot/README.md) för detaljer.
</details>

<details>
<summary><strong>Antigravity (Gemini)</strong></summary>

Varje agent blir en skill i `~/.gemini/config/skills/agency-<slug>/`.

```bash
./scripts/install.sh --tool antigravity
```

Aktivera den i Gemini med Antigravity:
```
@agency-frontend-developer granska denna React-komponent
```

Se [integrations/antigravity/README.md](integrations/antigravity/README.md) för detaljer.
</details>

<details>
<summary><strong>Gemini CLI</strong></summary>

Installera som Gemini CLI-subagenter.
På en ny klon, generera först Gemini-agentfilerna.

```bash
./scripts/convert.sh --tool gemini-cli
./scripts/install.sh --tool gemini-cli
```

Se [integrations/gemini-cli/README.md](integrations/gemini-cli/README.md) för detaljer.
</details>

<details>
<summary><strong>OpenCode</strong></summary>

Agenter placeras i `.opencode/agents/` i projektroten (projektbunden).

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool opencode
```

Eller installera globalt:
```bash
mkdir -p ~/.config/opencode/agents
cp integrations/opencode/agents/*.md ~/.config/opencode/agents/
```

Aktivera i OpenCode:
```
@backend-architect design this API.
```

Se [integrations/opencode/README.md](integrations/opencode/README.md) för detaljer.
</details>

<details>
<summary><strong>Cursor</strong></summary>

Varje agent blir en `.mdc`-regel-fil i `.cursor/rules/` i ditt projekt.

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool cursor
```

Reglerna appliceras automatiskt när Cursor känner igen dem i projektet. Referera till dem uttryckligen:
```
Använd @security-engineer-reglerna för att granska den här koden.
```

Se [integrations/cursor/README.md](integrations/cursor/README.md) för detaljer.
</details>

<details>
<summary><strong>Aider</strong></summary>

Alla agenter sammanställs till en enda `CONVENTIONS.md`-fil som Aider läser automatiskt.

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool aider
```

Använd sedan agenter i din Aider-session:
```
Använd Frontend Developer-agenten för att refaktorisera denna komponent.
```

Se [integrations/aider/README.md](integrations/aider/README.md) för detaljer.
</details>

<details>
<summary><strong>Windsurf</strong></summary>

Alla agenter sammanställs i `.windsurfrules` i projektroten.

```bash
cd /your/project
/path/to/agency-agents/scripts/install.sh --tool windsurf
```

Referera till agenter i Windsurf Cascade:
```
Använd Reality Checker-agenten för att verifiera att detta är produktionklart.
```

Se [integrations/windsurf/README.md](integrations/windsurf/README.md) för detaljer.
</details>

<details>
<summary><strong>OpenClaw</strong></summary>

Varje agent blir ett arbetsutrymme med `SOUL.md`, `AGENTS.md` och `IDENTITY.md` i `~/.openclaw/agency-agents/`.

```bash
./scripts/convert.sh --tool openclaw
./scripts/install.sh --tool openclaw
```

Om `openclaw` CLI är installerat, registrerar installeraren varje arbetsutrymme automatiskt.
Kör `openclaw gateway restart` efter installation så att nya agenter aktiveras.

Se [integrations/openclaw/README.md](integrations/openclaw/README.md) för detaljer.

</details>

<details>
<summary><strong>Qwen Code</strong></summary>

SubAgents installeras i `.qwen/agents/` i projektroten (projektbunden).

```bash
# Konvertera och installera (kör från projektroten)
cd /your/project
./scripts/convert.sh --tool qwen
./scripts/install.sh --tool qwen
```

**Användning i Qwen Code:**
- Referera med namn: `Använd frontend-developer-agenten för att granska denna komponent`
- Eller låt Qwen auto-delegera baserat på kontext
- Hantera via `/agents`-kommandot i interaktivt läge

> 📚 [Qwen SubAgents Docs](https://qwenlm.github.io/qwen-code-docs/en/users/features/sub-agents/)

</details>

<details>
<summary><strong>Codex</strong></summary>

Varje agent blir en separat Codex-custom-agent TOML-fil och installeras i `~/.codex/agents/`.

```bash
./scripts/convert.sh --tool codex
./scripts/install.sh --tool codex
```

Se [integrations/codex/README.md](integrations/codex/README.md) för detaljer.
</details>

---

Detta är bara den svenska översättningen av huvuddokumentationen och användarvänliga guider. Teknisk konfiguration, skript, filer och programvaru-ID:n förblir på engelska för att hålla repo:t fungerande och kompatibelt med verktyg och integrationsflöden.

