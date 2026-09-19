# 🤝 Bidra till The Agency

Tack för att du funderar på att bidra till The Agency! Det är människor som du som gör den här samlingen av AI-agenter bättre för alla.

## 📋 Innehållsförteckning

- [Uppförandekod](#uppförandekod)
- [Hur kan jag bidra?](#hur-kan-jag-bidra)
- [Riktlinjer för agenter](#riktlinjer-för-agenter)
- [Pull request-process](#pull-request-process)
- [Stilguide](#stilguide)
- [Gemenskap](#gemenskap)

---

## 📜 Uppförandekod

Det här projektet och alla som deltar i det styrs av vår uppförandekod. Genom att delta förväntas du följa den här koden:

- **Var respektfull**: Behandla alla med respekt. Hälsosam debatt uppmuntras, men personangrepp tolereras inte.
- **Var inkluderande**: Välkomna och stödja människor från alla bakgrunder och identiteter.
- **Var samarbetsinriktad**: Det vi skapar tillsammans blir bättre än det vi skapar själva.
- **Var professionell**: Håll diskussionerna fokuserade på att förbättra agenterna och gemenskapen.

---

## 🎯 Hur kan jag bidra?

### 1. Skapa en ny agent

Har du en idé för en specialiserad agent? Toppen! Så här lägger du till en:

1. **Forka repositoryt**
2. **Välj rätt division** — eller föreslå en ny. Divisioner är topnivå-katalogerna för agenter (t.ex. `engineering/`, `security/`, `gis/`, `marketing/`, `finance/`…); bläddra bland dem för att hitta var din agent passar. Den auktoritativa listan — med etiketter, ikoner och färger — finns i [`divisions.json`](divisions.json) i repo-ts roten, så att den alltid är aktuell.

   > **Divisioner definieras i `divisions.json`** (repo-ts rot) — den enda källan till sanning för divisionsuppsättningen, validerad i CI av `scripts/check-divisions.sh`.
   > **Att föreslå en ny division** innebär: skapa katalogen, lägg till en post i `divisions.json` (etikett/ikon/färg) och lägg den i `AGENT_DIRS` i både `scripts/convert.sh` och `scripts/lint-agents.sh`. Kontrollern misslyckas om det inte stämmer överens och katalogen inte innehåller minst en agentfil.
   >
   > Observera: `strategy/` (NEXUS-playbooks/runbooks — utan frontmatter för agenter) och `integrations/` (genererats per verktyg från `convert.sh`) är **inte** divisioner och får aldrig läggas till i divisionslistorna.

3. **Skapa din agentfil** enligt mallen nedan
4. **Testa din agent** i verkliga scenarier
5. **Skicka in en pull request** med din agent

### 2. Förbättra befintliga agenter

Har du hittat ett sätt att göra en agent bättre? Bidrag välkomnas:

- Lägg till verkliga exempel och användningsfall
- Förbättra kodexempel med moderna mönster
- Uppdatera arbetsflöden baserat på nya bästa praxis
- Lägg till framgångsmetoder och mätvärden
- Rätta stavfel, förbättra tydlighet och dokumentation

### 3. Dela framgångshistorier

Har du använt agenterna framgångsrikt? Dela din historia:

- Posta i [GitHub Discussions](https://github.com/msitarzewski/agency-agents/discussions)
- Lägg till en fallstudie i README
- Skriv en bloggpost och länka den
- Skapa en videoguide

### 4. Rapportera problem

Hittade du ett problem? Låt oss veta:

- Kontrollera om problemet redan finns
- Ge tydliga reproduktionssteg
- Inkludera kontext om ditt användningsfall
- Föreslå möjliga lösningar om du har några idéer

---

## 🎨 Riktlinjer för agenter

### Agentfilens struktur

Varje agent bör följa denna struktur:

```markdown
---
name: Agent Name
description: One-line description of the agent's specialty and focus
color: colorname or "#hexcode"
emoji: 🎯
vibe: One-line personality hook — what makes this agent memorable
services:                              # optional — only if the agent requires external services
  - name: Service Name
    url: https://service-url.com
    tier: free                         # free, freemium, or paid
---

# Agent Name

## 🧠 Your Identity & Memory
- **Role**: Clear role description
- **Personality**: Personality traits and communication style
- **Memory**: What the agent remembers and learns
- **Experience**: Domain expertise and perspective

## 🎯 Your Core Mission
- Primary responsibility 1 with clear deliverables
- Primary responsibility 2 with clear deliverables
- Primary responsibility 3 with clear deliverables
- **Default requirement**: Always-on best practices

## 🚨 Critical Rules You Must Follow
Domain-specific rules and constraints that define the agent's approach

## 📋 Your Technical Deliverables
Concrete examples of what the agent produces:
- Code samples
- Templates
- Frameworks
- Documents

## 🔄 Your Workflow Process
Step-by-step process the agent follows:
1. Phase 1: Discovery and research
2. Phase 2: Planning and strategy
3. Phase 3: Execution and implementation
4. Phase 4: Review and optimization

## 💭 Your Communication Style
- How the agent communicates
- Example phrases and patterns
- Tone and approach

## 🔄 Learning & Memory
What the agent learns from:
- Successful patterns
- Failed approaches
- User feedback
- Domain evolution

## 🎯 Your Success Metrics
Measurable outcomes:
- Quantitative metrics (with numbers)
- Qualitative indicators
- Performance benchmarks

## 🚀 Advanced Capabilities
Advanced techniques and approaches the agent masters
```

### Agentstruktur

Agentfiler organiseras i två semantiska grupper som mappar till OpenClaw:s arbetsytformat och hjälper andra verktyg att analysera din agent:

#### Persona (vem agenter är)
- **Identity & Memory** — roll, personlighet, bakgrund
- **Communication Style** — ton, röst, tillvägagångssätt
- **Critical Rules** — gränser och begränsningar

#### Operations (vad agenter gör)
- **Core Mission** — primära ansvar
- **Technical Deliverables** — konkreta resultat och mallar
- **Workflow Process** — steg-för-steg-metodik
- **Success Metrics** — mätbara resultat
- **Advanced Capabilities** — specialiserade tekniker

Ingen speciell formatering krävs — håll bara personrelaterade sektioner (identitet, kommunikation, regler) separata från operationella sektioner (uppdrag, leveranser, arbetsflöde, mätvärden). Skriptet `convert.sh` använder dessa rubriker för att automatiskt dela upp agenter i verktygsspecifika format.

### Principer för agentdesign

1. **🎭 Stark personlighet**
   - Ge agenterna en tydlig röst och karaktär
   - Inte "Jag är en hjälpsam assistent" — vara specifik och minnesvärd
   - Exempel: "Jag defaultar till att hitta 3–5 problem och kräver visuell bevisning" (Evidence Collector)

2. **📋 Klara leveranser**
   - Ge konkreta kodexempel
   - Inkludera mallar och ramverk
   - Visa verkliga resultat, inte vaga beskrivningar

3. **✅ Mätbara framgångsmetoder**
   - Inkludera specifika, mätbara mål
   - Exempel: "Sidladdningstid under 3 sekunder på 3G"
   - Exempel: "10 000+ kombinerad karma över konton"

4. **🔄 Beprövade arbetsflöden**
   - Steg-för-steg-processer
   - Verkligt testade tillvägagångssätt
   - Inte teoretiska — beprövade i produktion

5. **💡 Lärande minne**
   - Vilka mönster agenterna känner igen
   - Hur de förbättras över tid
   - Vad de minns mellan sessioner

### Externa tjänster

Agenter kan vara beroende av externa tjänster (API:er, plattformar, SaaS-verktyg) när dessa tjänster är avgörande för agentens funktion. När så är fallet:

1. **Deklarera beroenden** i frontmatter med `services`-fältet
2. **Agenterna måste fungera på egen hand** — ta bort API-anropen och det bör fortfarande finnas en användbar personlighet, arbetsflöde och expertis under ytan
3. **Duplicera inte leverantörers dokumentation** — hänvisa till den, reproducera den inte. Agentfilen ska läsa som en agent, inte som en snabbstartsguide
4. **Föredra tjänster med gratisnivåer** så att bidragsgivare kan testa agenterna

Testet: *är den här agenter för användaren, eller för leverantören?* En agent som löser användarens problem med hjälp av en tjänst hör hit. En tjänsts snabbstartsguide klädd som en agent gör inte det.

### Kompatibilitet med specifika verktyg

**Qwen Code-kompatibilitet**: Agentkroppar stöder `${variable}`-mallar för dynamisk kontext (t.ex. `${project_name}`, `${task_description}`). Qwen SubAgents använder minimalt frontmatter: endast `name`, `description`, `model` och `tools` om det behövs.

**Codex-kompatibilitet**: Codex-anpassade agenter genereras som fristående TOML-filer. Codex-integrationen håller en minimal 1:1-mappning: `name` och `description` kopieras från frontmatter, och resten av agentens text konverteras automatiskt.

### Lägg till en verktygsintegration

Vill du att agency-agents ska installeras i ett nytt verktyg (ett CLI, editor eller agentruntime)? Börja med **[öppna en Diskussion](https://github.com/msitarzewski/agency-agents/discussions)** — nya integrationsplattformar behöver samordning innan implementation. 

`tools.json` i repo-ts roten är den enda källan till sanning för verktygsuppsättningen, och `scripts/check-tools.sh` (CI) misslyckas om delarna nedan inte stämmer överens. Kör den — den listar alla platser där integrationer måste uppdateras.

**Checklistan:**

1. **`tools.json`** — lägg till en post med `id`, `label`, `kebab`, `format`, `installKind`, `dest`, plus detekterings-/versions-/scope-fält. **Återanvänd en befintlig `format`** om verktygets rendering passar.
2. **`scripts/convert.sh`** — lägg till en `convert_<tool>()` (eller återanvänd en gemensam format-renderare) och koppla den till verktygslistan + `--help`.
3. **`scripts/install.sh`** — lägg till en `install_<tool>()` och registrera den i `ALL_TOOLS` + detektering/etikettering + `--help`.
4. **`.gitignore`** — lägg till en regel för ditt genererade utdata under `integrations/<tool>/`. **Det här steget krävs och förbises lätt.** Konverterade agent-/skillfiler genereras lokalt av användaren.
5. **`integrations/<tool>/README.md`** — en kort dokumentation för integrationen (varje verktyg har en; det är den enda incheckade filen i katalogen).
6. **Kör `./scripts/check-tools.sh`** — den måste passera. Den korskontrollerar `tools.json` mot `install.sh` och `convert.sh` och flaggar för allt som saknas.
7. **Kör `./scripts/test-install.sh`** — den måste passera. Den installerar i tillfälliga sandlådor (aldrig i din riktiga `$HOME`) och låser fast installerarens observerbara kontrakt: var filer landar, att `--path` går före verktygets miljövariabel, att `--division` / `--agent` / `--agents-file`-filter fungerar, att `--dry-run` inte skriver någonting, och att banor med mellanslag fungerar. CI kör detta på Linux och macOS.
8. **Kör `./scripts/test-convert-outputs.sh`** — den måste passera. Den regenererar varje verktygsutdata i en temporär katalog och kontrollerar produkten, inte syntaxen: varje agents beskrivning rundtrippas intakt, varje genererad fil kan analyseras med en riktig YAML/TOML-parser, varje verktyg producerar exakt en utdatafil per agent, och varje källfil analyseras på samma sätt som skrivbordsappen läser den. När du avsiktligt ändrat en converter rapporterar den **manifest drift** på den raden — det är förväntat. Granska ändringen, kör den igen med `--update` och lägg till den uppdaterade `scripts/convert-outputs.sha256` så att reviewers kan se räckvidden av ändringen. Manifestet innehåller en rad per agent och en per verktyg, och hashes är samma på alla plattformar (forward-slash, LF-radbrytningar), så en Windows-checkout ger samma fil. CI kör detta på varje PR.

Om din PR checkar in konverterad utdata (de genererade filerna under `integrations/<tool>/*`) kommer CI och review att begära att du tar bort den och lägger till `.gitignore`-regeln istället.

### Vad gör en bra agent?

**Bra agenter har**:
- ✅ Smal, djup specialisering
- ✅ Distinkt personlighet och röst
- ✅ Konkret kod-/mall-exempel
- ✅ Mätbara framgångsmetoder
- ✅ Steg-för-steg-arbetsflöden
- ✅ Verkligt testning och iteration

**Undvik**:
- ❌ Generisk "hjälpsam assistent"-personlighet
- ❌ Vaga "Jag hjälper dig med..."-beskrivningar
- ❌ Inga kodexempel eller leveranser
- ❌ Alltför bred omfattning (jack of all trades)
- ❌ Otestade teoretiska tillvägagångssätt

---

## 🔄 Pull request-process

### Vad som hör hemma i en PR (och vad som inte gör det)

Den snabbaste vägen till en mergad PR är **en enda markdown-fil** — en ny eller förbättrad agent. Det är den optimala storleken.

För allt utöver det finns här hur vi håller det smidigt:

#### Välkommet i en PR
- Lägg till en ny agent (en `.md`-fil)
- Förbättra en befintlig agents innehåll, exempel eller personlighet
- Rätta stavfel eller klargöra dokumentation

#### Börja med en diskussion först
- Ny verktyg, byggsystem eller CI-arbetsflöden
- Arkitektoniska ändringar (nya kataloger, nya scripts, webbplatsskapare)
- Ändringar som berör många filer i repot
- Nya integrationsformat eller plattformar

Vi älskar ambitiösa idéer — en [Discussion](https://github.com/msitarzewski/agency-agents/discussions) ger bara gemenskapen en chans att anpassa tillvägagångssättet innan koden skrivs. Det sparar tid och undviker onödiga konflikter.

#### Saker vi alltid kommer att stänga
- **Checkade in byggutdata**: Genererade filer (`_site/`, kompilerade tillgångar, konverterade agentfiler) ska aldrig checkas in. Användare kör `convert.sh` lokalt; dess utdata är gitignored. När du lägger till en ny integration, kör skriv genereringen lokalt och commit:a bara byggbara källfiler.
- **PR:er som bulkändrar befintliga agenter** utan tidigare diskussion — även välmenande omformatering kan skapa merge-konflikter för andra bidragsgivare.
- **Nästan-dubbletter i "re-skins"**: Nya agenter som är find-and-replace-kopior av en befintlig (t.ex. byta land eller plattformnamn) i stället för genuina specialister. Kör `scripts/check-agent-originality.sh` för att validera unikhet.

### Innan du skickar in

1. **Testa din agent**: Använd den i verkliga scenarier, iterera baserat på feedback
2. **Följ mallen**: Matcha strukturen i befintliga agenter
3. **Lägg till exempel**: Inkludera minst 2–3 kod-/mall-exempel
4. **Definiera mätvärden**: Inkludera tydliga, mätbara kriterier
5. **Läs igenom**: Kontrollera stavfel, formatering, tydlighet
6. **Kontrollera att den är original**: Kör `./scripts/check-agent-originality.sh path/to/your-agent.md`. Den jämför din agent mot hela rostern och flaggar nästan-dubbletter (t.ex. ett bytt land/plattformsnamn snarare än en verkligt ny expertis).
7. **Kontrollera att den fungerar i alla verktyg**: Kör `./scripts/test-convert-outputs.sh`. Den regenererar varje verktygsutdata och bekräftar att din agent överlever varje converter — beskrivningen rundtrippas intakt och varje verktygsutdata kan parsas.

Ett ord om varför dessa kontroller finns. Människor bygger genuint fantastiska saker ovanpå dessa agenter, och tusentals förlitar sig på dem varje dag i ett dussin olika verktyg. Det är fantastiskt — men den här skalan kräver kvalitetskontroller.

### Skicka in din PR

1. **Forka** repositoryt
2. **Skapa en gren**: `git checkout -b add-agent-name`
3. **Gör dina ändringar**: Lägg till din agentfil(er)
4. **Commit**: `git commit -m "Add [Agent Name] specialist"`
5. **Push**: `git push origin add-agent-name`
6. **Öppna en pull request** med:
   - Tydlig titel: "Add [Agent Name] - [Category]"
   - Beskrivning av vad agenterna gör
   - Varför den här agenterna behövs (användningsfall)
   - All testning du gjort

### PR-granskningsprocess

1. **Gemenskapsgranskning**: Andra bidragsgivare kan ge feedback
2. **Iteration**: Hantera feedback och förbättra lösningen
3. **Godkännande**: Maintainers godkänner när det är redo
4. **Merge**: Ditt bidrag blir en del av The Agency!

### PR-mall

```markdown
## Agent Information
**Agent Name**: [Name]
**Category**: [engineering/design/marketing/etc.]
**Specialty**: [One-line description]

## Motivation
[Why is this agent needed? What gap does it fill?]

## Testing
[How have you tested this agent? Real-world use cases?]

## Checklist
- [ ] Original — not a near-duplicate (ran `scripts/check-agent-originality.sh`)
- [ ] Follows agent template structure
- [ ] Includes personality and voice
- [ ] Has concrete code/template examples
- [ ] Defines success metrics
- [ ] Includes step-by-step workflow
- [ ] Proofread and formatted correctly
- [ ] Tested in real scenarios
```

---

## 📐 Stilguide

### Skrivstil

- **Var specifik**: "Minska sidladdning med 60 %" istället för "Gör det snabbare"
- **Var konkret**: "Skapa React-komponenter med TypeScript" istället för "Bygg UI"
- **Var minnesvärd**: Ge agenter personlighet, inte generisk företagsjargong
- **Var praktisk**: Inkludera riktig kod, inte pseudokod

### Formatering

- Använd **Markdown-formatering** konsekvent
- Inkludera **emojis** i sektionstitlar (gör det lättare att skanna)
- Använd **kodblock** för alla kodexempel med korrekt syntaxmarkering
- Använd **tabeller** för att jämföra alternativ eller visa mätvärden
- Använd **fet stil** för betoning, `code` för tekniska termer

### Kodexempel

```markdown
## Example Code Block

\`\`\`typescript
// Always include:
// 1. Language specification for syntax highlighting
// 2. Comments explaining key concepts
// 3. Real, runnable code (not pseudo-code)
// 4. Modern best practices

interface AgentExample {
  name: string;
  specialty: string;
  deliverables: string[];
}
\`\`\`
```

### Ton

- **Professionell men tillgänglig**: Inte alltför formell eller lättsam
- **Självsäker men inte arrogant**: "Här är det bästa tillvägagångssättet" istället för "Kanske du kan prova..."
- **Hjälpsam men inte handhållande**: Anta kompetens, ge djup
- **Personlighetsdriven**: Varje agent ska ha sin egen röst

---

## 🌟 Erkännande

Bidragsgivare som gör betydande insatser kommer att:

- Listas i README:s tacksektion
- Lyftas i release notes
- Presenteras i "Agent of the Week"-presentationer (om tillämpligt)
- Få kredit i agentfilen själv

---

## 🤔 Frågor?

- **Allmänna frågor**: [GitHub Discussions](https://github.com/msitarzewski/agency-agents/discussions)
- **Buggarapporter**: [GitHub Issues](https://github.com/msitarzewski/agency-agents/issues)
- **Funktionsförfrågningar**: [GitHub Issues](https://github.com/msitarzewski/agency-agents/issues)
- **Gemenskapschatt**: [Gå med i diskussionerna](https://github.com/msitarzewski/agency-agents/discussions)

---

## 📚 Resurser

### För nya bidragsgivare

- [README.md](README.md) - Översikt och agentkatalog
- [Exempel: Frontend Developer](engineering/engineering-frontend-developer.md) - Välstrukturerat agentexempel
- [Exempel: Reddit Community Builder](marketing/marketing-reddit-community-builder.md) - Bra personlighetsexempel
- [Exempel: Whimsy Injector](design/design-whimsy-injector.md) - Kreativt specialisterexempel

### För agentdesign

- Läs befintliga agenter för inspiration
- Studera de mönster som fungerar
- Testa dina agenter i verkliga scenarier
- Iterera baserat på feedback

---

## 🎉 Tack!

Dina bidrag gör The Agency bättre för alla. Oavsett om du:

- Lägger till en ny agent
- Förbättrar dokumentation
- Rättar buggar
- Dela framgångshistorier
- Hjälper andra bidragsgivare

**Du gör skillnad. Tack!**

---

<div align="center">

**Frågor? Idéer? Feedback?**

[Öppna ett ärende](https://github.com/msitarzewski/agency-agents/issues) • [Starta en diskussion](https://github.com/msitarzewski/agency-agents/discussions) • [Skicka in en PR](https://github.com/msitarzewski/agency-agents/pulls)

Gjord med ❤️ av gemenskapen

</div>

