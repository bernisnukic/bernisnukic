# Bernis Nukic

I run infrastructure and build the software on top of it.

I founded [FadeHost](https://fadehost.com), a game server host, in 2011 and still run it, from the control panel and
node agents to the rollouts and monitoring behind them. At
[Bicom Systems](https://www.bicomsystems.com) I deploy SERVERware onto racked servers: installing over IPMI and
iDRAC, setting up the network, and running the rollout with the client from start to handover. In my own time I
build [EditClips](https://editclips.online), browser video tools whose heavier AI jobs run on a GPU rig I maintain.

## What I work on

- **Running a fleet.** Services in Rust and Go. Releases roll out as Temporal workflows that go to a canary first
  and stop on the first failure. Hosted apps are isolated with nftables and sandboxed with gVisor, and the nodes
  talk over a self-hosted Headscale mesh.
- **Observability.** SigNoz on OpenTelemetry, Prometheus metrics from every node, and alerts that still arrive
  when the app itself is down.
- **GPU serving.** About 11 models on one rig, with VRAM checks before each job and recovery when a card hangs.
  Moving the most expensive CPU job to Rust took it from 565 ms to about 45 ms per frame.
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
