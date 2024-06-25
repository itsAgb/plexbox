# plexbox
Docker Compose Setup for VPN-Secured Media Server

This project uses Docker Compose to set up a VPN-secured media server. The included services are gluetun, deluge, jackett, radarr, sonarr, tautulli, flaresolverr, joal, and overseerr. Each service depends on gluetun for network connectivity via WireGuard.

## Prerequisites

- Docker installed on your machine.
- Docker Compose installed.

## Configuration

Make sure to replace the placeholders in the `docker-compose.yml` file with your actual information.

### Environment Variables for gluetun

- `PUID` and `PGID`: User and group IDs for managing permissions.
- `VPN_SERVICE_PROVIDER`: Set to `custom` to use a custom VPN provider.
- `VPN_TYPE`: Set to `wireguard` to use WireGuard.
- `VPN_ENDPOINT_IP`, `VPN_ENDPOINT_PORT`: The IP address and port of your VPN endpoint.
- `WIREGUARD_PUBLIC_KEY`, `WIREGUARD_PRIVATE_KEY`: The public and private keys for WireGuard.
- `WIREGUARD_ADDRESSES`: The IP address for WireGuard.

### Volume and Port Configuration

Mounted volumes allow for storing configurations and downloads on your host system. Exposed ports allow access to the various web interfaces of the services.

## Included Services

- **gluetun**: Provides VPN connectivity via WireGuard.
- **deluge**: Torrent client secured by the VPN.
- **jackett**: Proxy server for torrent indexers.
- **radarr**: Movie management tool.
- **sonarr**: TV series management tool.
- **tautulli**: Monitoring tool for Plex.
- **flaresolverr**: Server to bypass Cloudflare challenges.
- **joal**: Anonymous seedbox.
- **overseerr**: Media request management tool.

## Usage

1. Clone this repository to your local machine.
2. Replace the placeholders in the `docker-compose.yml` file with your actual information.
3. Launch the services using Docker Compose:
   ```sh
   docker-compose up -d

Make sure to fill in the placeholders (`#YOUR_IP_HERE`, `#YOUR_PORT_HERE`, `#YOUR_PUBLIC_KEY_HERE`, `#YOUR_PRIVATE_KEY_HERE`, `#YOUR_WG_ADDRESS_HERE`, etc.) with your specific configuration information before deploying the services.
