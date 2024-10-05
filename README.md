# Vue 3 Todo App with Atomic Design and Tailwind CSS

This project is a Vue 3 todo application built using the Atomic Design Pattern and styled with Tailwind CSS. It allows users to add, toggle, and view todo items.

## Features

- Add new todo items
- Toggle todo item completion status
- Responsive design
- Dark mode toggle

## Project Setup

1. Clone the repository
2. Install dependencies:

```bash
npm install
```

3. Run the development server:

```bash
npm run dev
```

4. Build for production:

```bash
npm run build
```

5. Preview the production build:

```bash
npm run preview
```

## Project Structure

The project follows the Atomic Design pattern:

- `src/components/atoms`: Basic building blocks (Button, Input, TodoItem)
- `src/components/molecules`: Combinations of atoms (AddTodoForm)
- `src/components/organisms`: Combinations of molecules and/or atoms (TodoList)
- `src/components/templates`: Page layouts (MainTemplate)
- `src/components/pages`: Full pages composed of organisms and templates (TodoPage)

## Technologies Used

- Vue 3
- TypeScript
- Vite
- Tailwind CSS

## License

This project is open source and available under the [MIT License](LICENSE).