# Introduction

Nyvalis is a lightweight and secure library for building desktop applications with Python using WebView2, inspired by [Tauri](https://github.com/tauri-apps/tauri). This document will guide you through setting up, using, and registering commands in Nyvalis.

## Installation

Make sure you have Python installed on your machine. Then, install Nyvalis:

```bash
pip install nyvalis
```

## Creating a New Project

To create a new Nyvalis project, use the command:

```bash
nyvalis new project_name
```

This will generate a new project structure with all the necessary files.

## Running the Project

To run your project in development mode, use:

```bash
nyvalis run
```

This will start the backend server and open the application in a WebView window.

## Building the Project

To create a final version of your application, use:

```bash
nyvalis build
```

This will generate the executable of your application, ready for distribution.

## Registering Python commands

You can register commands as python functions file of your project. An example of a command would be:

```python
@nyvalis.command
def example(name: str):
    return f"{name}, Hello from Python!"
```

Once registered, the frontend will be able to call it like this:

```javascript
async function example() {
    message = await invoke("example", { name });
}
```

## About

This is a personal project inspired by [Tauri](https://github.com/tauri-apps/tauri).
