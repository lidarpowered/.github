# Lidar - Container Abuse Detection System

An enterprise-grade container abuse detection system powered by AI-driven analysis with real-time Docker container scanning. Designed specifically for Pterodactyl Panel deployments.

## Overview

Lidar is a sophisticated two-component security system:

1. **Dashboard API** - Centralized management console with hash database and admin panel for flagged content
2. **Scanner Node** - Distributed scanning agent for Pterodactyl nodes to detect abuse patterns and behavioral anomalies

## Key Features

- **AI-Powered Detection** - Leverages AI for intelligent pattern recognition and false-positive reduction
- **Real-time Container Monitoring** - Continuous scanning of Docker containers for suspicious files and processes
- **Intelligent Hash Database** - Advanced caching and classification of malicious and safe file hashes
- **Management Dashboard** - Comprehensive web UI for monitoring detections and managing audit logs
- **Production-Ready** - LRU caching, batch operations, and horizontal scalability
- **Security-Focused** - Session management, rate limiting, and strict input validation
- **Complete Audit Trail** - Comprehensive logging of all detection and management activities
- **Multi-Node Support** - Seamless integration with multiple Pterodactyl nodes

## System Architecture

```
┌──────────────────────────────────────────────────────┐
│           Pterodactyl Panel Infrastructure            │
└────────────────┬─────────────────────────────────────┘
                 │
    ┌────────────┼────────────┐
    │            │            │
┌───▼──┐    ┌───▼───┐    ┌───▼───┐
│ Node │    │ Node  │    │ Node  │
│Lidar │    │ Lidar │    │ Lidar │
└───┬──┘    └───┬───┘    └───┬───┘
    │           │           │
    └───────────┼───────────┘
                │ REST API (TLS)
       ┌────────▼──────────┐
       │  Lidar Dashboard  │
       │  & API Server     │
       │  (Node.js/Express)│
       └────────┬──────────┘
                │
       ┌────────▼──────────┐
       │  Prisma ORM       │
       │  SQLite Database  │
       └───────────────────┘
```

Made with ❤️ by Overnode Networks