# 📺 Jellyfin Media Server

## 🔗 Navegação

**[🏠 AslamSys](https://github.com/AslamSys)** → **[📚 _system](https://github.com/AslamSys/_system)** → **[📂 Entretenimento (RPi 5 8GB)](https://github.com/AslamSys/_system/blob/main/hardware/entretenimento%20-%20(raspberry-pi-5-8gb)/README.md)** → **entretenimento-media-server**

### Containers Relacionados (entretenimento)
- [entretenimento-brain](https://github.com/AslamSys/entretenimento-brain)
- [entretenimento-radarr-movies](https://github.com/AslamSys/entretenimento-radarr-movies)
- [entretenimento-sonarr-series](https://github.com/AslamSys/entretenimento-sonarr-series)
- [entretenimento-bazarr-subtitles](https://github.com/AslamSys/entretenimento-bazarr-subtitles)
- [entretenimento-streaming-aggregator](https://github.com/AslamSys/entretenimento-streaming-aggregator)

---

**Container:** `media-server`  
**Stack:** Jellyfin  
**Storage:** HD 2TB USB 3.0

---

## 📋 Propósito

Media server open-source. Organiza e transmite filmes, séries, música. Transcodificação H.265 4K.

---

## 🎯 Features

- ✅ Transcoding H.265 → H.264 (VideoCore VII)
- ✅ 4K 60fps playback
- ✅ Metadata automático (IMDb, TMDb)
- ✅ Multi-user profiles
- ✅ Chromecast support

---

## 🚀 Docker Compose

```yaml
media-server:
  image: jellyfin/jellyfin:latest
  ports:
    - "8096:8096"  # WebUI
    - "1900:1900/udp"  # DLNA
  volumes:
    - /media:/media  # HD 2TB
    - ./config:/config
    - ./cache:/cache
  devices:
    - /dev/dri:/dev/dri  # Hardware transcoding
  environment:
    - TZ=America/Sao_Paulo
  deploy:
    resources:
      limits:
        cpus: '1.0'
        memory: 1536M
```

---

## 📁 Library Structure

```yaml
/media/
  movies/
    - Cast Away (2000).mkv
    - The Terminal (2004).mkv
  series/
    - Breaking Bad/
      - Season 01/
        - S01E01.mkv
  music/
    - Artist/
      - Album/
        - Track.mp3
```

---

## 🔄 Changelog

### v1.0.0
- ✅ Jellyfin latest
- ✅ HW transcoding
- ✅ 2TB storage
