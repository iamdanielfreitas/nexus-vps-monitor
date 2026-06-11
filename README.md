# nexus-vps-monitor

Monitor externo de disponibilidade da nexus-vps, rodando em GitHub Actions (fora da VPS).

- A cada ~5 min checa TCP 443/80 com 3 tentativas.
- Na transição **up → down** posta 🔴 no Slack (`#alertas-infra`); na volta, 🟢.
- Credenciais em GitHub Secrets (`SLACK_BOT_TOKEN`, `SLACK_CHANNEL_ID`).
- `keepalive.yml` evita a desativação automática de schedules após 60 dias sem commits.

Teste manual: rodar o workflow **VPS Monitor** com `test_alert=true`.
