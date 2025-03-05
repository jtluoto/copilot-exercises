## Project Structure
```
/src
 ├── components  # Reusable UI components
 ├── pages       # Page components
 ├── hooks       # Custom React hooks
 ├── context     # Context API state management
 ├── styles      # Global and modular styles
 ├── assets      # Static assets (images, fonts, etc.)
 ├── utils       # Helper functions
 ├── App.jsx     # Main app component
 ├── main.jsx    # Entry point
```

## Development Guidelines
### Coding Standards
- Use functional components and hooks.
- Follow the DRY (Don't Repeat Yourself) principle.
- Use ES6+ syntax where applicable.

### Styling
- Use CSS Modules for styling.

### State Management
- Use `useState` and `useReducer` for local state.
- Use Context API for global state management.

### API Calls
- Use `fetch` for API requests.
- Store API calls in a separate service folder.
- Implement error handling and loading states.

## Running Tests
Run tests using:
```sh
npm test
```
Ensure unit and integration tests cover critical components.

## Additional Notes
- Use `.env` files for environment-specific configurations.
