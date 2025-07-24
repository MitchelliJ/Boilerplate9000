# Prompt: Setup Node.js Backend and Astro Frontend

You are an expert AI assistant. Your task is to set up a new project with a Node.js backend and an Astro frontend.

Follow these instructions precisely. Assume Windows PowerShell and do not use '&&'.

## 1. Backend Setup (Node.js)

1. Create a new directory named `backend`
   ```powershell
   mkdir backend
   ```
2. Navigate into the `backend` directory
   ```powershell
   cd backend
   ```
3. Initialize a new Node.js project with default settings
   ```powershell
   npm init -y
   ```
4. Navigate back to the project root directory
   ```powershell
   cd ..
   ```

## 2. Frontend Setup (Astro)

1. From the project root, create a new directory named `frontend`
   ```powershell
   mkdir frontend
   ```
2. Run this command from the `frontend` directory:
   ```powershell
   cd frontend
   npm create astro@latest . -- --template minimal --install --no-git
   ```

   When done, strongly advice the user to setup version control :-)