# GitCord Template

A sister repo to **[GitCord](https://github.com/evolvewithevan/gitcord)**, a bot that allows for the management of discord server channel structure via Git.

> [!WARNING]  
> Repo is currently non-operation and is for development purposes only

## Overview

This repository serves as a starter template for configuring your Discord server’s channel and category structure through Git.
To use you can either:
- **A)** Fork this repo and design your own server channel structure
- **B)** Design your own server channel structure from scratch

## Development

### Server Structure

Each category is described with a `category.yaml` file, placed in `/servermap/`, which has a subdirectory - Within, each channel being `channelname.yaml`. The bot pulls from this repo to apply channel configuration upon a `/gitcord pull` command.

### Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
   
Pull Requests are welcome and encouraged!
If you have ideas to improve the template structure or want to contribute examples, feel free to open a PR or issue.
