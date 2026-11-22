# Bernis Nukic

I build and run hosting platforms, from the servers up.

I founded [FadeHost](https://fadehost.com) in 2011 and still run it as its only engineer. It started with game
servers and now also hosts Discord, Telegram and WhatsApp bots, web apps deployed from GitHub, managed databases and
VPS. I built the control panel, the API, the node software and the networking behind it.
[EditClips](https://editclips.online) is my other product: 170+ video, audio and image tools in the browser, with
the AI and heavier jobs running on hardware I run myself. At [Bicom Systems](https://www.bicomsystems.com) I deploy
SERVERware onto racked servers: installing over IPMI and iDRAC, setting up the network, and running the rollout with
the client from start to handover.

## What I work on

- **Multi-tenant hosting.** About 40 game server images plus runtimes for bots and apps. Free apps run sandboxed
  with gVisor, every app is isolated on the network, and each customer's servers, bots and databases share a private
  WireGuard network.
- **Fleet operations.** A controller on every node, and releases that roll out as Temporal workflows: canary first,
  health checks, automatic revert. Backups and the AI assistant run as Rust services.
- **Edge and networking.** Cloudflare in front, Workers for routing and uptime checks, a Go tunnel so customers can
  run servers on their own machines, and a custom Minecraft protocol edge that wakes a sleeping server when a player
  joins.
- **Job processing and GPU serving.** A dispatcher with backpressure, a circuit breaker and stuck-job recovery feeds
  my own GPU and CPU workers. I moved every AI workload off serverless GPUs onto that rig, which serves 15+ models. A
  Rust port took the most expensive video job from 565 ms to about 45 ms per frame.
- **Production practice.** Zero-downtime blue-green deploys, self-hosted OpenTelemetry with alerts that still reach
  me when the app is down, encrypted backups with tested restores, and a server move with about 90 seconds of frozen
  writes.
- **AI tooling.** MCP servers on both products, an AI editing agent in the EditClips editor, and an AI assistant in
  the FadeHost panel.
- **Kubernetes.** [hop](https://github.com/bernisnukic/hop) runs a Go service with Terraform, Helm, CloudNativePG
  and burn-rate SLO alerts, and its end-to-end test proves a rolling restart under load loses no requests.

## Open source

- [hop](https://github.com/bernisnukic/hop): a Go link shortener and everything needed to run it on Kubernetes
- [Headroom](https://github.com/bernisnukic/headroom): a RAM, CPU and GPU monitor for the Linux and macOS top bar,
  in Rust with gpui
- [Baseboard](https://github.com/bernisnukic/baseboard): an out-of-band management console for IPMI, iDRAC,
  Lenovo IMM2 and Supermicro BMCs
- [Airprowl](https://github.com/bernisnukic/airprowl): a Bluetooth, WiFi and sub-GHz scanner for the Linux
  terminal
- [CVE-2022-21667](https://github.com/advisories/GHSA-86ch-6w7v-v6xf): I found and reported a bug in soketi where
  one empty request, with no login needed, crashed the WebSocket server

## Tools I use most

Linux, Docker, Rust, Go, Postgres, Temporal, Prometheus, Kubernetes, Terraform, Helm, Cloudflare, TypeScript,
Next.js and Laravel.

[bernis.dev](https://bernis.dev) · [contact@bernis.dev](mailto:contact@bernis.dev)
