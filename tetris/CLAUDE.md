# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Mobile-optimized Tetris game built as a single-page React application. The entire game runs in one HTML file (`index.html`) using CDN-hosted dependencies.

## Tech Stack

- React 18 (via CDN, production build)
- Babel Standalone (for JSX transpilation in browser)
- Tailwind CSS (via CDN)
- No build process required - runs directly in browser

## Running the Game

Open `index.html` directly in a browser. No server or build step needed.

## Architecture

### Single File Structure
Everything is contained in `index.html`:
- CSS styles in `<style>` tag
- React component in `<script type="text/babel">` tag

### Code Organization (within index.html)
1. **Constants** (lines 49-83): Game configuration (`BOARD_WIDTH`, `BOARD_HEIGHT`, `CELL_SIZE`), speed options, tetromino definitions, colors, and decorative patterns
2. **Utility Functions** (lines 85-131): Board creation, piece generation, rotation logic, score formatting
3. **Tetris Component** (lines 134-722): Main game component containing all state and logic

### Key Game Logic
- `checkCollision`: Validates piece placement against board boundaries and existing blocks
- `moveDown`, `moveHorizontal`, `rotatePiece`, `hardDrop`: Piece movement functions
- `clearLines`: Removes completed rows and handles scoring
- `initializeGame`: Shared initialization for normal and random game modes
- Continuous movement: Touch/mouse hold triggers rapid horizontal movement after 100ms delay

### Visual Features
- Day/night theme based on system time (6AM-6PM = day)
- Desert background with animated walking camels
- Game over animation with falling blocks

## Git Remotes

- `origin` (test1): https://github.com/yongajjang-ops/test1.git
- `mobile-tetris`: https://github.com/yongajjang-ops/mobile-tetris.git

Push to both remotes: `git push origin main && git push mobile-tetris main`
