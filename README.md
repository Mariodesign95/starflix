# ⭐ Starflix - by Fannub

Addon Stremio per lo streaming di Film, Serie TV e Anime in italiano.

## 📺 Provider Supportati

- **AnimeUnity** (Anime)
- **AnimeWorld** (Anime)
- **AnimeSaturn** (Anime)
- **GuardaHD** (Film)
- **GuardaSerie** (Serie TV)
- **GuardoSerie** (Film & Serie TV)
- **StreamingCommunity** (Film & Serie TV)

## 🚀 Installazione

### Deploy su HuggingFace (Consigliato)

1. Crea un nuovo Space su HuggingFace (SDK: Docker, Blank).
2. Crea un file `Dockerfile` con il seguente contenuto:
```dockerfile
FROM node:20-alpine
WORKDIR /app
RUN apk add --no-cache git
RUN git clone https://github.com/Mariodesign95/starflix.git .
RUN npm install
RUN node build.js
EXPOSE 7000
CMD ["node", "stremio_addon.js"]
```
3. Aggiungi la variabile `CF_PROXY_URL` con l'URL del tuo Cloudflare Worker.
4. Attendi il deploy e clicca su **INSTALL ADDON**.

### Esecuzione Locale

```bash
npm install
npm start
```

L'addon sarà disponibile su `http://localhost:7000`.

---

**Powered by [Fannub](https://github.com/Mariodesign95/)**
