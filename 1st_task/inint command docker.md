🔹 What is docker init?

      The docker init command auto-generates a basic Dockerfile, .dockerignore, and other configs for common frameworks (Node.js, Python, Go, etc.).

Think of it like npm init — but for Docker!

 🔧 Usage:

          docker init
🔍 What it does:

     Detects project language and framework

     Suggests a base image

     Generates:

            Dockerfile

           .dockerignore

           Optional compose.yaml

✅ Benefits:

      Great for beginners and quick setups

      Ensures you're following best practices

      Reduces human error in boilerplate

📌 Example:
     For a Node.js project:


        $ docker init
        ✔ Detected Node.js project
        ✔ Created Dockerfile
        ✔ Created .dockerignore
        ✔ Created compose.yaml