# task-01-http-server

const express = require("express");

const app = express();
const PORT = 3000;

// Route 1: Home
app.get("/", (req, res) => {
  res.json({
    message: "Welcome to my HTTP Server",
    status: "success"
  });
});

// Route 2: About
app.get("/about", (req, res) => {
  res.json({
    project: "Task 01 - HTTP Server and Routing",
    technology: "Node.js and Express"
  });
});

// Route 3: Users
app.get("/users", (req, res) => {
  res.json({
    users: [
      { id: 1, name: "Aman" },
      { id: 2, name: "Rahul" }
    ]
  });
});

// 404 handler for unknown routes
app.use((req, res) => {
  res.status(404).json({
    error: "Route not found",
    status: 404
  });
});

// Start the server
app.listen(PORT, () => {
  console.log(`Server running at http://localhost:${PORT}`);
});
