# Final stage: serve via Node.js
FROM node:22-alpine

# Set working directory
WORKDIR /app

# Install only the serve package to serve the static files
RUN npm install -g serve

# Show globally installed npm packages (for debugging)
RUN npm list -g --depth=0

# Show where npm and node are installed
RUN which npm
RUN which node

# Copy the built dist directory from the GitHub Action's build step
COPY ./dist /app/dist

# Expose the default port for the server
EXPOSE 3000

# Start the app using serve
CMD ["serve", "-s", "/app/dist", "-l", "3000"]
