# Persian Stremio

[![Version](https://img.shields.io/badge/version-2.5.0-blue.svg)](https://github.com/Esmaeli/stremio-ir-providers)
[![Node](https://img.shields.io/badge/node-%3E%3D24.18.0-green.svg)](https://nodejs.org)
[![License](https://img.shields.io/badge/license-ISC-blue.svg)](https://opensource.org/licenses/ISC)

**Persian Stremio** is a community-maintained Stremio addon that aggregates Iranian and international streaming sources, delivering movies, series, and live TV directly inside Stremio.

This project is a **community fork** of [stremio-ir-providers](https://github.com/MrMohebi/stremio-ir-providers) by [MrMohebi](https://github.com/MrMohebi). It continues development with additional providers, performance improvements, bug fixes, IPTV support, and ongoing maintenance.

> 🙏 Special thanks to **MrMohebi** for creating the original project and making this fork possible.

---

## ✨ Features

| Capability | Description |
|---|---|
| **Multi-Provider Search** | Search across all supported providers simultaneously |
| **Movie & Series Support** | Full support for both movies and TV series with season/episode handling |
| **Iranian Content** | Dedicated providers for Persian-dubbed and original Iranian content |
| **Quality Sorting** | Streams automatically sorted by resolution (4K → 1080p → 720p → 480p) |
| **Stream Metadata** | Quality, file size, audio type, and encoder info in stream titles |
| **IMDb ID Lookup** | Streams appear on main Stremio pages via IMDb ID integration |
| **Live TV / IPTV** | Watch live Iranian TV channels directly in Stremio |
| **Cloudflare Workers** | Deploy the entire addon as a serverless Cloudflare Worker |
| **Image Proxy** | Built-in proxy for metadata images in restricted regions |
| **Subtitles** | Integrated subtitle support via OpenSubtitles |

---

## 🎯 Supported Providers

| Provider | Type | Description |
|---|---|---|
| **Cinamatic** | Movies & Series | Persian movie and series site with dubbed and subtitled content |
| **AslMoviez** | Movies & Series | Comprehensive Persian media library with IMDb ratings and genre classification |
| **SerialBlog** | Movies & Series | Mirrors AslMoviez content |
| **F2Media** | Movies & Series | Persian movie and series site with direct download links |
| **PeepBoxTV** | Movies & Series | REST API-based provider with search and streaming details |
| **Seda va Sima - Telewebion** | Live TV | IPTV channels from the official Iranian Telewebion M3U playlist |

---

## 📺 IPTV

Watch live Iranian TV channels directly in Stremio. The **Seda va Sima - Telewebion** catalog provides a continuously updated list of live channels parsed from the official Telewebion M3U playlist. Simply select a channel to start streaming immediately.

---

## 🔧 Installation

### Install in Stremio

Paste the following URL into Stremio → Community Add-ons → **Install from URL**:

```
https://pstream.ir/manifest.json
```

### Run Locally

```sh
git clone https://github.com/Esmaeli/stremio-ir-providers.git
cd stremio-ir-providers
corepack enable
pnpm install
cp .env.example .env
# Edit .env with your provider credentials
pnpm dev
```

The addon will be available at `http://127.0.0.1:7000/manifest.json`.

---

## ⚙️ Configuration

Copy `.env.example` to `.env` and fill in the required values. Each provider requires its base URL and, where applicable, API credentials. See `.env.example` for the full list of available variables.

---

## ☁️ Deployment

### Cloudflare Workers

```sh
cp .dev.vars.example .dev.vars
# Fill in secrets
npx wrangler login
pnpm worker:deploy
```

### Docker

```sh
docker compose up -d
```

---

## 🛠️ Development

| Command | Description |
|---|---|
| `pnpm install` | Install dependencies |
| `pnpm test` | Run the full test suite |
| `pnpm dev` | Start local development server |
| `pnpm start` | Start production server |
| `pnpm worker:deploy` | Deploy to Cloudflare Workers |

### Project Structure

```
├── app.js                  # Express addon — routing, catalogs, streams
├── index.js                # Express entry point
├── cloudflare/             # Cloudflare Worker implementation
├── sources/                # Provider implementations
├── test/                   # Test suite
└── docs/                   # Documentation
```

---

## 🤝 Community

This is a **community-maintained fork**. Contributions, bug reports, and feature requests are welcome!

- **Fork Repository**: [https://github.com/Esmaeli/stremio-ir-providers](https://github.com/Esmaeli/stremio-ir-providers)
- **Upstream Original**: [https://github.com/MrMohebi/stremio-ir-providers](https://github.com/MrMohebi/stremio-ir-providers)

---

## 🙏 Credits

- **MrMohebi** — Original creator of [stremio-ir-providers](https://github.com/MrMohebi/stremio-ir-providers)
- **Esmaeli** — Community fork maintainer

This project would not exist without the original work by MrMohebi. Thank you!

---

## ⚠️ Disclaimer

This project is for **educational purposes only**. The addon indexes publicly available content from third-party sources. Users are responsible for complying with applicable laws and the terms of service of any sources they access. The maintainers do not host, store, or distribute any copyrighted content.

---

## 📄 License

ISC — See [LICENSE](LICENSE) for details.
