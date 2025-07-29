# 📘 Dockerfile Best Practices Summary
(Reference: Docker Official Best Practices)

✨ Key Best Practices:
Use small base images

     Use alpine or minimal base images when possible.

Leverage multi-stage builds

     Separate build and runtime environments.

Use .dockerignore

     Exclude unnecessary files from the build context.

Minimize layers

     Combine commands using && to reduce intermediate layers.

Avoid installing unnecessary packages

     Only install what you need — it reduces size and vulnerabilities.

Use explicit version tags

    Instead of latest, use pinned versions like node:18-alpine.

Keep containers stateless

    Don't store persistent data inside containers.

Use health checks

    Add HEALTHCHECK to monitor running containers.

Label your images

    Add metadata using LABEL, e.g. version, maintainer, purpose.

Use CMD or ENTRYPOINT properly

    Use ENTRYPOINT for fixed commands, and CMD for defaults that can be overridden.

