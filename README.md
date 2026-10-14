# schematize-observability

> **Sistema que você não enxerga, você não opera.** A dona da observabilidade da casa: OpenTelemetry
> como padrão (SDK + Collector, OTLP, semantic conventions), os três sinais mais profiling contínuo
> correlacionados por `trace_id`, cardinalidade e amostragem, SLO com alertas multi-window
> multi-burn-rate e runbook, dashboards como código, healthchecks e a stack self-hosted de referência.

Pacote de **skill normativa para [Claude Code](https://claude.com/claude-code)**.
Parte do catálogo **schematize skills**.

## Por que ela existe

O tema vivia em quatro lugares com versões diferentes (base, infra, front e linguagens) e sem dono.
Faltavam o padrão OTel de ponta a ponta, amostragem que nunca perde erro, orçamento de cardinalidade,
burn-rate, redaction no Collector e o piso de ambiente (telemetria de hml nunca vai para prd).

## Instalar

### Pelo app schematize (recomendado)

```bash
schematize install observability    # requer o CLI schematize instalado
```

### Manual

```bash
git clone https://github.com/schematizeme/skill-observability.git /tmp/skill-observability
bash /tmp/skill-observability/install.sh .        # instala em .claude/ do projeto atual
```

## O que tem dentro

- **SKILL.md** — o contrato: 13 pisos inegociáveis + o mapa de references + fronteiras.
- **references/** — `padrao-otel`, `logs`, `metricas`, `amostragem-profiling`, `slo-alertas`,
  `healthchecks`, `stack-referencia`, `ambientes`, `front-llm`, `stack-versoes` (anexo volátil com data).
- **scripts/** — `check-otel-collector.sh` e `check-alertas.mjs`, gates com `*.test.sh` (casos
  vermelhos plantados, sem rede).
- **assets/** — Collector de referência, regras de SLO multi-burn-rate, convenção de log JSON,
  exemplos mínimos de instrumentação por linguagem do rol (Go, Rust, Elixir, C#, Zig, Ruby), `CLAUDE.md`.

## Comandos

| Comando | O que faz |
|---|---|
| `/obs-help` | lista os comandos |
| `/obs-load` | carrega o corpo normativo e passa a aplicá-lo |
| `/obs-review` | revisa um serviço e roda os gates |
| `/obs-instrument` | instrumenta um serviço no padrão |
| `/obs-slo` | define SLO/error budget e gera burn-rate |
| `/obs-alerts` | audita/escreve alertas |
| `/obs-dashboard` | dashboard como código |
| `/obs-claude` | cria/mescla o `CLAUDE.md` sempre-on |
| `/obs-cc` · `/obs-handoff` | context compact / handoff no archive |

## Versão

**v0.1.0** — changelog em `CHANGELOG.md`.

## Regra de ouro

Se caiu e você foi olhar o dashboard, ele já tinha que estar lá — e o alerta, apontando o runbook.

MIT.
