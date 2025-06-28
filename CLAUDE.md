# Othello Game Application

## Tech Stack

- Framework: React Router v7
- Runtime: Cloudflare Workers
- Database: SQLite (D1)
- Testing: Vitest (unit), Playwright (e2e)
- Language: TypeScript

## Project Structure

- `othello-app/`: React Router v7 application
- `othello-app/routes/`: Page components and API routes
- `othello-app/components/`: Reusable UI components
- `othello-app/lib/`: Game logic and utilities
- `othello-app/db/`: Database schema and queries
- `tests/`: Vitest unit tests
- `e2e/`: Playwright end-to-end tests

## Commands

- `npm run dev`: Start development server
- `npm run build`: Build for production
- `npm run test`: Run unit tests
- `npm run test:e2e`: Run e2e tests
- `npm run deploy`: Deploy to Cloudflare Workers
- `npm run db:migrate`: Run database migrations

## Code Style

- Use TypeScript for all new code
- Function components with hooks
- Arrow functions for components
- Descriptive variable names for game state
- Separate game logic from UI components

## Game Rules

- 8x8 board with initial 4 pieces in center
- Players alternate turns (black starts first)
- Valid moves must flank opponent pieces
- Game ends when no valid moves remain
- Winner has most pieces on board

## Architecture Guidelines

- Game state managed with React context
- Board represented as 8x8 number array (0=empty, 1=black, 2=white)
- Game logic functions pure and testable
- Database stores game history and player stats
- Real-time updates via WebSocket (future feature)

## Database Schema

- `games`: id, board_state, current_player, status, created_at
- `moves`: id, game_id, player, row, col, timestamp
- `players`: id, name, wins, losses, created_at

## Testing Strategy

- Unit tests for game logic functions
- Component tests for UI interactions
- E2E tests for complete game flows
- Test invalid moves and edge cases
