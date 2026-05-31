# OpenSkynet — Termux Install (Pantheon Edition)

## Prerequisites (run once)
```bash
pkg update -y && pkg install python rust git -y
pip install uv
```

## Install
```bash
git clone https://github.com/kevinleestites2-dev/OpenSkynet.git ~/OpenSkynet
cd ~/OpenSkynet
uv tool install --force .
```

## Configure
```bash
source ~/OpenSkynet/pantheon.env
mkdir -p $SEDIMAN_DATA_DIR
cp ~/OpenSkynet/SOUL.md $SEDIMAN_DATA_DIR/SOUL.md
cp ~/OpenSkynet/CONTEXT.md $SEDIMAN_DATA_DIR/CONTEXT.md
```

## Launch
```bash
source ~/OpenSkynet/pantheon.env && sediman
```

## Verify Ollama bridge is active first
```bash
curl https://naval-measures-mat-modern.trycloudflare.com/api/tags
```
If that returns models, the brain is live. If not, restart cloudflared on Termux first.

## Notes
- Brain = Ollama llama3 via tunnel — $0 cost
- Skills auto-saved to ~/.sediman-pantheon/skills/
- Cron jobs survive restarts
- Telegram reporting wired via TELEGRAM_BOT_TOKEN env var
