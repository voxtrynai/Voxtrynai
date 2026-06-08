# VoxtrynAI Development Guide

This guide provides everything developers need to know about VoxtrynAI development workflow, tools, and best practices.

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/voxtrynai/Voxtrynai.git
cd Voxtrynai

# Install dependencies
npm install

# Start development server
npm start

# Run tests
npm test

# Build for production
npm run build
```

---

## 📋 Development Workflow

### 1. Branching Strategy

We use Git Flow branching strategy:

```
main (production)
  ↓ (via PR)
develop (development)
  ↓ (feature branch)
feature/your-feature
```

**Branch naming conventions:**
- `feature/feature-name` - New features
- `bugfix/bug-name` - Bug fixes
- `hotfix/bug-name` - Critical production fixes
- `refactor/code-area` - Refactoring
- `docs/doc-type` - Documentation updates

### 2. Creating a Feature

```bash
# Create and switch to feature branch
git checkout -b feature/amazing-feature develop

# Make your changes
# ... work work work ...

# Commit your changes
git add .
git commit -m "feat(scope): description"

# Push to remote
git push origin feature/amazing-feature

# Create Pull Request on GitHub
```

### 3. Pull Request Process

1. **Title Format:** `feat: Add amazing feature` or `fix: Resolve issue #123`
2. **Description:** Clear description of changes and why
3. **Tests:** Ensure all tests pass locally
4. **Code Review:** Wait for at least 1 approval
5. **Merge:** Use "Squash and merge" for cleaner history

### 4. Code Review Guidelines

**Reviewers look for:**
- ✅ Code follows style guide
- ✅ Tests are included and passing
- ✅ Documentation is updated
- ✅ No breaking changes (unless intended)
- ✅ Performance impact is acceptable

---

## 🧪 Testing

### Running Tests

```bash
# Run all tests
npm test

# Run tests in watch mode
npm test -- --watch

# Run tests with coverage
npm test -- --coverage

# Run specific test file
npm test -- MemoryPalace.test.js
```

### Writing Tests

```javascript
describe('MemoryPalace', () => {
  it('should save memory', () => {
    const memory = new MemoryPalace();
    memory.save({ content: 'test' });
    expect(memory.retrieve()).toBe('test');
  });
});
```

### Coverage Goals

- Minimum 70% code coverage
- 100% coverage for critical paths
- Focus on business logic, not imports

---

## 📝 Commit Messages

**Format:**
```
type(scope): subject

body

footer
```

**Type:**
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation
- `style` - Code style changes
- `refactor` - Code refactoring
- `perf` - Performance improvement
- `test` - Test changes
- `chore` - Dependency/config updates

**Example:**
```
feat(memory-palace): add persistent storage

Implement SQLite storage for memory persistence.
Users can now save and retrieve conversations.

Closes #123
```

---

## 🔍 Code Style

### JavaScript/React

```javascript
// ✅ Good
const fetchUserData = async (userId) => {
  try {
    const response = await api.get(`/users/${userId}`);
    return response.data;
  } catch (error) {
    console.error('Failed to fetch user:', error);
    throw error;
  }
};

// ❌ Avoid
function fetchUserData(userId) {
  var response = api.get('/users/' + userId);
  return response.data;
}
```

### React Components

```javascript
// ✅ Good - Functional component with hooks
const MemoryPalace = ({ userId, memories }) => {
  const [selected, setSelected] = useState(null);

  return (
    <div className="memory-palace">
      {/* JSX */}
    </div>
  );
};

// ❌ Avoid
class MemoryPalace extends React.Component {
  // Old class syntax
}
```

### Tailwind CSS

```jsx
// ✅ Good
<button className="bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg transition-colors">
  Click me
</button>

// ❌ Avoid
<button style={{backgroundColor: '#16A34A', padding: '8px 16px'}}>
  Click me
</button>
```

---

## 🐛 Debugging

### Development Tools

```bash
# Start dev server with debugging
NODE_DEBUG=* npm start

# Chrome DevTools
# Press F12 in browser during development
```

### Console Logging

```javascript
// Development
console.log('Debug info:', data);

// Avoid in production
// Use proper logging library instead
```

### React DevTools

1. Install React DevTools extension
2. Inspect components in browser
3. Check props and state
4. Use Profiler for performance

---

## 📚 Documentation

### Writing Documentation

1. **Code Comments**
   ```javascript
   /**
    * Saves a memory to the memory palace
    * @param {Object} memory - Memory object
    * @param {string} memory.content - Memory content
    * @param {number} memory.importance - Importance level (1-10)
    * @returns {Promise<void>}
    */
   async function saveMemory(memory) {
     // Implementation
   }
   ```

2. **README Updates**
   - Document new features
   - Add usage examples
   - Update API docs

3. **Inline Documentation**
   - Explain why, not what
   - Use clear language
   - Keep it concise

---

## 🔒 Environment Variables

Create `.env.local`:
```env
REACT_APP_API_URL=http://localhost:5000
REACT_APP_OPENROUTER_KEY=your_key_here
REACT_APP_BASE44_API_KEY=your_key_here
```

See `.env.example` for all variables.

---

## 🚀 Building & Deployment

### Development Build
```bash
npm start
```

### Production Build
```bash
npm run build
```

### Environment-Specific Builds
```bash
# Staging
REACT_APP_ENVIRONMENT=staging npm run build

# Production
REACT_APP_ENVIRONMENT=production npm run build
```

---

## 🔗 Useful Resources

- **React Docs:** https://react.dev
- **Tailwind CSS:** https://tailwindcss.com
- **Node.js:** https://nodejs.org
- **Git Guide:** https://git-scm.com/doc
- **GitHub Docs:** https://docs.github.com

---

## ❓ Getting Help

- 📧 Email: mdsabbirhossein35@gmail.com
- 💬 GitHub Discussions
- 🐦 Twitter: @MdHossein70485
- 📖 Documentation: [docs](https://github.com/voxtrynai/docs)

---

**Happy coding! 🎉**
