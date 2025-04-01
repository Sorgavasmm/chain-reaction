# Chain Reaction Game - Desktop Edition

![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)

A modern implementation of the classic strategy board game "**Chain Reaction**", built as a cross-platform desktop application for a university project. Engage in strategic battles against AI or challenge your friends in online multiplayer!

## Table of Contents

* [Overview](#overview)
* [Features](#features)
* [Game Rules](#game-rules)
* [Tech Stack](#tech-stack)
* [Getting Started](#getting-started)
    * [Prerequisites](#prerequisites)
    * [Installation & Running](#installation--running)
* [Collaborators](#collaborators)
* [License](#license)

## Overview

**Chain Reaction** is a captivating turn-based strategy game where players aim to dominate the board by strategically placing orbs. When a cell reaches its critical mass, it explodes, spreading orbs to adjacent cells and converting enemy orbs, potentially triggering thrilling chain reactions.

This project brings the Chain Reaction experience to your desktop (Windows, macOS, Linux) using Electron and React, featuring both a challenging single-player mode against a Python-based AI and real-time online multiplayer battles.

## Features

* **Cross-Platform:** Runs on Windows, macOS, and Linux thanks to Electron.
* **Single Player Mode:** Test your strategic skills against an AI opponent (powered by Python, potentially using MCTS).
* **Online Multiplayer Mode:** Connect and play with friends in real-time over the network using WebSockets.
* **Interactive UI:** Sleek and responsive user interface built with React.
* **Core Game Logic:** Faithful implementation of Chain Reaction rules, including explosions and conversions.
* **Customizable Gameplay:** Options to select grid size or player colors.

## Game Rules

1.  **The Board:** The game is played on a rectangular grid (e.g., 9x6 or 6x5).
2.  **Players:** 2 to 8 players take turns (in this version, typically 2 players for online/AI modes). Each player has a distinct color.
3.  **Placing Orbs:** On your turn, you can place an orb in an empty cell or a cell that already contains orbs of your own color.
4.  **Critical Mass:** Each cell has a limit to how many orbs it can hold:
    * Corners: 2 orbs
    * Edges (not corners): 3 orbs
    * Center Cells: 4 orbs
5.  **Explosions:** When adding an orb causes a cell to reach its critical mass, it explodes!
    * The cell loses as many orbs as its critical mass (becomes empty or resets count).
    * One orb is added to each orthogonally adjacent cell (up, down, left, right).
    * If an adjacent cell receives an orb, it adopts the color of the exploding player.
6.  **Chain Reactions:** If an explosion causes an adjacent cell to reach *its* critical mass, that cell also explodes, potentially continuing the chain reaction across the board. A player's turn only ends after all chain reactions have completed.
7.  **Winning:** The last player with orbs remaining on the board wins! You eliminate opponents by converting all their orbs to your color through explosions.

## Tech Stack

* **Frontend:**
    * [Electron](https://www.electronjs.org/) - Framework for creating native applications with web technologies.
    * [React](https://reactjs.org/) - JavaScript library for building user interfaces.
    * HTML5, CSS3, JavaScript
* **Backend:**
    * [Node.js](https://nodejs.org/) - JavaScript runtime environment.
    * [Express](https://expressjs.com/) - Web application framework for Node.js.
* **Networking:**
    * [WebSockets](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API) (using libraries like `ws`) - For real-time multiplayer communication.
* **AI Opponent:**
    * [Python](https://www.python.org/) - For AI logic.
    * *Algorithm: Under Development*
* **Database:**
    * [MongoDB](https://www.mongodb.com/) - For storing user data or game state.
* **Inter-Process Communication (IPC):**
    * Node.js `child_process` / Standard Input/Output / Local HTTP - To connect Node.js backend with Python AI.

## Getting Started

Follow these instructions to get a local copy up and running for development or testing.

### Prerequisites

* [Node.js](https://nodejs.org/en/download/) (includes npm) - Ensure you have a recent version installed.
* [Python](https://www.python.org/downloads/) (version 3.x recommended) - Ensure Python and pip are installed and accessible from your PATH.
* [Git](https://git-scm.com/downloads)

### Installation & Running

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Sorgavasmm/chain-reaction.git](https://github.com/Sorgavasmm/chain-reaction.git)
    cd chain-reaction
    ```

## Collaborators

This project was developed by the following team members:

* [Selvamani](https://github.com/selva-mani-007)
* [Àrjun](https://github.com/ArjunArul55)
* [Natrajan](https://github.com/natrajanmd-579)
* [Vishal](https://github.com/dvishal2309)
* [Mohan](https://github.com/mohancrazy143)
* [Maniish Raja](https://github.com/MemoDemo-GJ/)

## License

This project is licensed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file distributed with this source code for full details.

> Copyright (C) 2025 [Selvamani](https://github.com/selva-mani-007), [Àrjun](https://github.com/ArjunArul55), [Natrajan](https://github.com/natrajanmd-579), [Vishal](https://github.com/dvishal2309), [Mohan](https://github.com/mohancrazy143) and [Maniish Raja](https://github.com/MemoDemo-GJ/)
>
> This program is free software: you can redistribute it and/or modify
> it under the terms of the GNU General Public License as published by
> the Free Software Foundation, either version 3 of the License, or
> (at your option) any later version.
>
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
> GNU General Public License for more details.
>
> You should have received a copy of the GNU General Public License
> along with this program. If not, see <https://www.gnu.org/licenses/>.

