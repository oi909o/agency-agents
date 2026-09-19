# Svensk översättning – projektstatus

## Huvudprojekt

Det här är huvudprojektet för den svenska Agency Agents-upplevelsen:

- Repository: `oi909o/agency-agents`
- Arbetsgren: `fortsatt-svensk-oversattning`
- Utgångspunkt: `svenska-oversattning`
- Bascommit: `ecda0fa7bfa4011010acab71bd9c6a20eb5b1d4a`

Mobilprojektet `oi909o/agency-agents-mobile` är pausat och ska inte driva arbetet just nu.

## Vad som redan är gjort

Följande dokument är delvis eller huvudsakligen översatta till svenska:

- `README.md`
- `CONTRIBUTING.md`
- `examples/README.md`
- `integrations/README.md`

Den svenska README:n säger uttryckligen att teknisk konfiguration, skript, filnamn och programvaru-ID:n behålls på engelska för kompatibilitet.

## Vad som inte är färdigt

De flesta faktiska agentdefinitionerna är fortfarande på engelska. Det gäller bland annat:

- `engineering/`
- `design/`
- `marketing/`
- `product/`
- `project-management/`
- `testing/`
- `security/`
- `support/`
- `specialized/`
- övriga agentdivisioner

Exempel på ännu oöversatta agentfiler vid återställningen:

- `engineering/engineering-frontend-developer.md`
- `engineering/engineering-backend-architect.md`
- `engineering/engineering-mobile-app-builder.md`
- `design/design-ux-researcher.md`
- `product/product-manager.md`
- `research/research-synthesist.md`

## Översättningsprinciper

1. Behåll filnamn, mappar, frontmatter-nycklar och agenternas tekniska ID:n på engelska.
2. Översätt agentens synliga namn, beskrivning, personlighet, arbetsflöden, leveranser och exempel till naturlig svenska.
3. Behåll kod, API-namn, kommandon, klassnamn, biblioteksnamn och andra tekniska symboler oförändrade.
4. Behåll rubrikstrukturen så att `scripts/convert.sh` och `scripts/lint-agents.sh` fortsätter att fungera.
5. Behåll obligatoriska frontmatterfält: `name`, `description` och `color`.
6. Översätt inte tekniska verktygsnamn som React, TypeScript, GitHub Copilot, Claude Code, OpenAPI eller Kubernetes.
7. Använd konsekvent, professionell svenska och behåll agenternas personlighet — översätt inte till stel direktöversättning.

## Arbetsordning

Nästa arbetsbatch bör vara kärnupplevelsen:

1. `engineering/engineering-frontend-developer.md`
2. `engineering/engineering-backend-architect.md`
3. `design/design-ux-researcher.md`
4. `product/product-manager.md`
5. `testing/testing-reality-checker.md`

Efter varje batch ska följande kontroller köras:

```bash
./scripts/lint-agents.sh
./scripts/check-divisions.sh
./scripts/test-convert-outputs.sh
```

Genererade filer under `integrations/` ska inte checkas in som översättningskällor. De återskapas med:

```bash
./scripts/convert.sh
```

## Definition of done

Den svenska versionen är klar först när:

- huvuddokumentationen är genomgången och språkligt konsekvent,
- alla agentfiler i samtliga divisioner är översatta eller uttryckligen granskade,
- tekniska namn och integrationsformat fortfarande fungerar,
- frontmatter och konverteringsskript passerar valideringen,
- ingen svensk agent har kvar oavsiktliga engelska instruktioner eller exempel.

Mobilappen återupptas först när den här källan är stabil.
