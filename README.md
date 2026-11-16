# Akıllı Yorum Özetleyici (`yorum-ozetleyici`)

**Geliştirici:** Enes Baykal (GitHub: `enesbaykal730-bit`)

Agent Pazaryeri Geliştirici Rehberi (`spec_version 1.1`) standartlarına uygun...

## Yerel Kurulum ve Çalıştırma

### 1. Docker ile Çalıştırma
```bash
docker build -t yorum-ozetleyici .
docker run -p 8080:8080 \
  -e PLATFORM_SIGNING_SECRET="yerel-test-anahtari" \
  -e LLM_BASE_URL="https://api.openai.com/v1" \
  -e LLM_API_KEY="sk-..." \
  yorum-ozetleyici
```

### 2. Sözleşme Testlerini Çalıştırma
```bash
pip install -r requirements.txt
pytest tests/test_contract.py
```

## Entegrasyon Test Beyanı
`integrations/` klasöründeki Claude Code, Codex ve Cursor talimatları;
1. **Next.js (TypeScript)** e-ticaret şablon projesinde,
2. **Python FastAPI** backend servisinde
olmak üzere iki farklı proje tipinde denenmiş ve doğrulama testleri geçilmiştir.
