# Practical Report — Docker Run

## Overview

This practical was completed on the **KodeKloud Docker Run** hands-on lab. The lab consisted of 6 tasks focused on inspecting running containers, understanding port mappings, and running a container with a custom name and port mapping.

A folder of screenshots (`screenshots/`) is attached as evidence of each completed task.

## Environment

- **Platform:** KodeKloud Studio Hands-On Lab
- **Host Port Assigned:** 38282

## Tasks Completed

| # | Task | Answer / Command |
|---|------|------------------|
| 1 | Inspect the environment — how many containers are running? | `docker ps` → **1** |
| 2 | Identify the image used by the container | `docker ps` → **nginx:alpine** |
| 3 | Count the unique ports published on the container (IPv4 + IPv6 counted once) | **2** |
| 4 | Identify the ports mapped on the container side (exposed inside the container) | **3456 & 80** |
| 5 | Identify the ports published on the host | **38080 & 3456** |
| 6 | Run a `kodekloud/simple-webapp:blue` container named `blue-app`, mapping container port 8080 to host port 38282 | `docker run -d --name blue-app -p 38282:8080 kodekloud/simple-webapp:blue` |

## Key Concepts Learned

- `docker ps` — list running containers, including their port mappings under the `PORTS` column.
- **Port mapping format** `host:container` — e.g. `-p 38282:8080` maps host port 38282 to container port 8080.
- Reading port mappings such as `0.0.0.0:3456->3456/tcp` to tell apart the host-side port from the container-side port.
- A single published port appears for both IPv4 (`0.0.0.0`) and IPv6 (`:::`) but counts as one unique port.
- `docker run -d --name <name> -p <host>:<container> <image>` — run a named container in detached mode with a port mapping.

## Reflection

This practical helped me understand how Docker exposes container applications to the outside world through port mapping. Reading the `PORTS` column in `docker ps` was the key skill: I learned to distinguish the host-side port from the container-side port, and that the same port listed for IPv4 and IPv6 is still just one published port. The final task tied it all together — running `kodekloud/simple-webapp:blue` as `blue-app` with `-p 38282:8080`, where Docker pulled the image automatically before starting the container. All four validation checks (container running, correct image, container port 8080, host port 38282) passed, and all 6 tasks were completed successfully.

## Attachments

- `screenshots/` — screenshots of each completed task in the lab.
