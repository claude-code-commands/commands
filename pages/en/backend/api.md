---
description: Generate REST API endpoints with validation and error handling
allowed-tools: Read, Edit, Write, Bash(npm:*, yarn:*)
---

## Your task

Generate REST API endpoints with proper validation, error handling, and documentation following RESTful principles.

### API Development Process

1. **Design API Structure**: Define routes, methods, and data flow
2. **Create Route Handlers**: Implement controller functions for each endpoint
3. **Add Validation**: Implement input validation using appropriate libraries
4. **Error Handling**: Create comprehensive error handling middleware
5. **Add Documentation**: Generate OpenAPI/Swagger documentation
6. **Create Tests**: Write unit and integration tests for all endpoints

### Implementation Guidelines

- Follow RESTful naming conventions
- Use appropriate HTTP status codes
- Implement proper authentication and authorization
- Add rate limiting and security headers
- Use middleware for cross-cutting concerns
- Follow the project's existing patterns and conventions

### Example API Structure

```javascript
// routes/users.js
const express = require('express');
const { body, validationResult } = require('express-validator');
const router = express.Router();

// GET /api/users
router.get('/', async (req, res) => {
  try {
    const users = await User.find({});
    res.json({ success: true, data: users });
  } catch (error) {
    res.status(500).json({ success: false, error: error.message });
  }
});

// POST /api/users
router.post('/', [
  body('email').isEmail().normalizeEmail(),
  body('name').isLength({ min: 2 }).trim(),
], async (req, res) => {
  const errors = validationResult(req);
  if (!errors.isEmpty()) {
    return res.status(400).json({ success: false, errors: errors.array() });
  }
  
  try {
    const user = new User(req.body);
    await user.save();
    res.status(201).json({ success: true, data: user });
  } catch (error) {
    res.status(500).json({ success: false, error: error.message });
  }
});

module.exports = router;
```

This command helps create consistent, secure, and well-documented API endpoints that follow industry best practices.