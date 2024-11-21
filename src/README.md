# Task Manager

A simple Task Manager application built with React that allows users to add, view, and delete tasks. This project provides a hands-on introduction to React components, state management, and props.

## Features

- **Add Tasks**: Users can type in a task and click "Add Task" to add it to the list.
- **View Tasks**: Display a list of all added tasks below the input field.
- **Delete Tasks**: Each task has a delete button to remove it from the list.

## Project Setup

### Prerequisites

- Node.js and npm installed on your machine.

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/task-manager.git
    cd task-manager
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

3. Start the development server:
    ```bash
    npm start
    ```

    Open [http://localhost:3000](http://localhost:3000) to view the app in the browser.

## Components

### TaskForm

Handles the input for adding new tasks.

```jsx
import React, { useState } from 'react';

function TaskForm({ addTask }) {
    const [task, setTask] = useState('');

    const handleSubmit = (e) => {
        e.preventDefault();
        if (task.trim()) {
            addTask(task);
            setTask('');
        }
    };

    return (
        <form onSubmit={handleSubmit}>
            <input
                type="text"
                value={task}
                onChange={(e) => setTask(e.target.value)}
                placeholder="Add a new task"
            />
            <button type="submit">Add Task</button>
        </form>
    );
}

export default TaskForm;
