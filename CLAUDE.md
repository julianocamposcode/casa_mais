# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Casa Mais is a full-stack web application for managing a social assistance organization. It handles beneficiaries, medical consultations, medication inventory, donations, and expenses.

**Architecture**: React frontend + Node.js/Express backend + MySQL database

## Development Commands

### Backend (backend/)

```bash
npm start          # Start production server
node index.js      # Alternative start command
```

### Frontend (frontend/)

```bash
npm run dev        # Start development server with Vite HMR
npm run build      # Build for production
npm run lint       # Run ESLint
npm run preview    # Preview production build
```

## Development Tools

### Backend Development

- Use **JavaScript** with **Express.js** framework
- Use **nodemon** for automatic server restart during development

## Architecture

### Backend Structure

- **MVC + Repository Pattern**: Controllers handle business logic, repositories manage data access
- **Entry Point**: `index.js` → `src/app.js`
- **Database**: MySQL with connection pooling (config in `src/config/database.js`)
- **Models**: Include validation methods and MySQL date utilities
- **API**: RESTful endpoints with consistent JSON responses
- **Guidelines**:
  1. Respeite a estrutura do projeto no backend: controllers, models, repository e routes;
  2. Nao altere os documentos medicamentoController.js, medicamento.js, medicamentoRepository.js, medicamentoRoutes.js, sem me consultar antes.

### Frontend Structure

- **Component-Based**: Layout components with nested routing via React Router
- **Service Layer**: Data operations abstracted (currently localStorage, should integrate with backend API)
- **Styling**: Bootstrap + custom CSS
- **Utils**: Input masks, validations, and sample data helpers
- **Guidelines**:
  1. Respeite a estrutura do frontend: components organizados por funcionalidade, services para API, utils para validações;
  2. Use React Router para navegação e mantenha o padrão de componentes existente. 

### Data Flow Gap

**Important**: Frontend currently uses localStorage instead of backend API. The medication API exists but isn't connected to the React app.

## Database Setup

**Prerequisites**:

- MySQL server on localhost:3306
- Database: `casamais_db`
- Credentials: root/admin (hardcoded in config/database.js)

**Current Tables**: Medications with validation for dates (MM/YYYY format) and quantities

## Key Patterns

### Backend Response Format

```javascript
{
  success: boolean,
  data: object|array,
  message?: string,
  errors?: array,
  total?: number
}
```

### Model Validation

Models include built-in validation methods that return standardized error arrays for consistent API responses.

### Frontend Service Pattern

Services provide CRUD operations and statistics. Currently implemented for donations (`doacoesService.js`) using localStorage.

## Testing & Quality

**Current Status**: No test suite configured. ESLint available for frontend with React-specific rules.

**Lint Command**: `npm run lint` (frontend only)

## Git Commit Guidelines

**NEVER include Claude Code signatures in commit messages**:
- Do NOT add "🤖 Generated with [Claude Code]"
- Do NOT add "Co-Authored-By: Claude"
- Keep commit messages clean and professional without AI attribution
