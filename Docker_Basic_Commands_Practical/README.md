# Practical Report — Docker Basic Commands

## Overview

This practical was completed on the **KodeKloud Docker Basic Commands** hands-on lab. The lab consisted of 17 tasks covering the fundamental Docker commands used to inspect, run, manage, and clean up containers and images.

A folder of screenshots (`screenshots/`) is attached as evidence of each completed task.

## Environment

- **Platform:** KodeKloud Studio Hands-On Lab
- **Docker Version:** 25.0.5

## Tasks Completed

| # | Task | Command Used |
|---|------|--------------|
| 1 | Find the Docker Server Engine version | `docker --version` |
| 2 | Count running containers | `docker ps` |
| 3 | Count available images | `docker images` |
| 4 | Run a container using the `redis` image | `docker run -d redis` |
| 5 | Stop the created container | `docker stop <id>` |
| 6 | Count running containers after stopping | `docker ps` |
| 7 | Count running containers (after creating a few) | `docker ps` |
| 8 | Count all containers (running + stopped) | `docker ps -a` |
| 9 | Find the image used by the `nginx-1` container | `docker ps` |
| 10 | Find the container name created from the `ubuntu` image | `docker ps` |
| 11 | Find the ID of the stopped `alpine` container | `docker ps -a` |
| 12 | Find the state of the stopped `alpine` container | `docker ps -a` |
| 13 | Delete all containers (running + stopped) | `docker rm -f $(docker ps -aq)` |
| 14 | Delete the `ubuntu` image | `docker rmi ubuntu` |
| 15 | Pull the `nginx:1.14-alpine` image | `docker pull nginx:1.14-alpine` |
| 16 | Run a container named `webapp` from `nginx:1.14-alpine` | `docker run -d --name webapp nginx:1.14-alpine` |
| 17 | Cleanup — delete all images on the host | `docker rmi $(docker images -q)` |

## Key Commands Learned

- `docker --version` — check the installed Docker version
- `docker ps` / `docker ps -a` — list running / all containers
- `docker images` — list available images
- `docker run -d <image>` — run a container in detached mode
- `docker stop <id>` — stop a running container
- `docker rm` / `docker rmi` — remove containers / images
- `docker pull <image>` — download an image without running it

## Reflection

This practical gave me hands-on experience with the core Docker workflow: checking the engine, listing and inspecting containers and images, running containers in detached mode, and cleaning up the host. I learned to read the output of `docker ps` and `docker ps -a` to tell the difference between running and exited containers, and saw why detached mode (`-d`) keeps the terminal free. I also ran into and fixed small mistakes (e.g. stopping a container by name vs. ID), which helped me understand how Docker identifies containers. All 17 tasks were completed successfully.

## Attachments

- `screenshots/` — screenshots of each completed task in the lab.
