# 🍪 Hello Jupyter Notebook in Docker with VS Code! 🚀

Welcome to the world of Jupyter Notebooks running inside Docker, all accessible from the comfort of Visual Studio Code! This repository will guide you through setting up a basic environment where you can say "Hello, World!" in Python. It’s like baking cookies but for code—let's dive in!

## 🛠 Prerequisites

Before you get started, make sure you have the following installed on your machine:

- **Docker**: To containerize your environment. Get it [here](https://www.docker.com/get-started).
- **Visual Studio Code (VS Code)**: Your development playground. Download it [here](https://code.visualstudio.com/).
- **VS Code Extensions**:
  - **Docker**: Manage your Docker containers from within VS Code.
  - **Jupyter**: Run and edit Jupyter Notebooks directly in VS Code.

## 📄 Dockerfile Setup

Here’s the secret recipe (a.k.a. Dockerfile) for creating your Jupyter Notebook environment:

```dockerfile
# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /usr/src/app

# Install Jupyter
RUN pip install jupyter

# Expose the port Jupyter runs on
EXPOSE 8888

# Command to run Jupyter Notebook
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--allow-root", "--no-browser"]
```

## 🏗 Build and Run

Now, let’s get this environment up and running:

1. **Build the Docker Image**:  
   In your terminal, navigate to the directory containing your Dockerfile and run:

   ```bash
   docker build -t my-jupyter-notebook .
   ```

2. **Run the Docker Container**:  
   Once the image is ready, fire up the container:

   ```bash
   docker run -p 8888:8888 my-jupyter-notebook
   ```

   You'll see a URL with a token in your terminal—this is your gateway to the Jupyter Notebook.

## 💻 Access Jupyter Notebook in VS Code

1. Open **VS Code**.
2. Go to the **Docker extension** in the sidebar.
3. Find your running container, right-click, and select “Attach Visual Studio Code”.
4. Open the **Jupyter extension** in VS Code and connect to your running notebook server.

And just like that, you’ve teleported into your Jupyter environment—no sci-fi tricks involved!

## 👋 Hello, World!

In your Jupyter Notebook:

1. Create a new notebook.
2. In the first cell, type:

   ```python
   print("Hello, World!")
   ```

3. Run the cell by clicking the play button or pressing `Shift + Enter`.

Congratulations! You’ve successfully run your first Python script in a Dockerized Jupyter Notebook accessed through VS Code. Give yourself a high five—or a cookie! 🍪

## 📂 Project Structure

```
.
├── Dockerfile          # The Dockerfile for setting up the environment
├── README.md           # You're reading this fabulous file right now!
└── .gitignore          # Ignore Python cache, Docker artifacts, etc.
```

## 🌟 Contributing

If you find a better way to bake these coding cookies, feel free to fork this repo, make your changes, and submit a pull request. Let’s make this recipe even tastier together!

## 📄 License

This project is open-source, under the [MIT License](LICENSE). Go ahead, play with it, and share your creations with the world!

---

Happy coding! 🍪🚀
