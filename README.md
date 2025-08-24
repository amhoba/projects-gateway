# project-gateway

This repository contains the **project-gateway**, which acts as the centralized entry point for all services running on the server. It leverages Traefik to route and manage incoming requests.


## Structure

```

├── gateway
│   ├── Dockerfile       # Builds the Traefik gateway container
│   └── traefik.yml      # Traefik static configuration
├── integration
│   ├── compose.py       # Integration automation script
│   ├── docker-compose.yml
│   ├── do.py            # CLI helper script
│   ├── README.md        # Integration-specific instructions
│   └── utils.py         # Shared utilities
└── README.md            # This file

```

## Overview

- **Gateway**: Built from the Dockerfile in `gateway/`, running Traefik configured via `traefik.yml`. It listens on ports 80 and 443 and automatically routes traffic to your services.
- **Integration**: Contains tooling and Docker Compose configurations to manage and test the full stack. See `integration/README.md` for details.

## Purpose

This gateway provides a unified access point, making service discovery and external routing seamless. Traefik dynamically detects and routes to containers via the Docker provider, simplifying your architecture.

## Notes

* `traefik.yml` contains static settings (logging, Docker provider, access control, dashboard, etc.) — changes require a restart.
* The gateway is lightweight and focused solely on handling request routing.

## License

MIT.
