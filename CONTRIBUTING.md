# 🤝 Contributing to MindRepo

First off, thank you for considering contributing to MindRepo! It's people like you that make open source amazing.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Workflow](#development-workflow)
- [Style Guidelines](#style-guidelines)
- [Commit Messages](#commit-messages)
- [Pull Request Process](#pull-request-process)
- [GSSoC Specific Guidelines](#gssoc-specific-guidelines)

---

## 📜 Code of Conduct

This project and everyone participating in it is governed by our commitment to:
- **Be respectful** - Treat everyone with respect
- **Be welcoming** - Create a friendly environment for newcomers
- **Be constructive** - Provide helpful feedback
- **Be inclusive** - Welcome contributors from all backgrounds

---

## 🚀 Getting Started

### Fork and Clone

1. Fork the repository by clicking the "Fork" button on GitHub
2. Clone your fork locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/Mind-repo.git
   cd Mind-repo
   ```
3. Add the upstream remote:
   ```bash
   git remote add upstream https://github.com/HariOm-Coder-Ambadnya/Mind-repo.git
   ```

### Setup Development Environment

Follow the [Getting Started](./README.md#getting-started) guide in the README to set up your local environment.

---

## 💡 How Can I Contribute?

### Reporting Bugs

Before creating a bug report:
- Check if the issue already exists
- Try the latest version to see if it's already fixed

When creating a bug report, include:
- **Clear title** - Describe the problem
- **Steps to reproduce** - Detailed steps
- **Expected behavior** - What you expected
- **Actual behavior** - What happened
- **Screenshots** - If applicable
- **Environment** - OS, browser, versions

### Suggesting Enhancements

- Use a clear, descriptive title
- Provide detailed description of the feature
- Explain why it would be useful
- Include mockups or examples if possible

### Code Contributions

#### Good First Issues

Look for issues labeled:
- `good first issue` - Easy for newcomers
- `documentation` - Documentation improvements
- `bug` - Bug fixes
- `help wanted` - Maintainer needs assistance

#### Areas for Contribution

| Area | Description | Skills Needed |
|------|-------------|---------------|
| 🎨 **UI/UX** | Improve design, add animations | React, Tailwind CSS |
| ⚙️ **Backend** | API improvements, performance | Java, Spring Boot |
| 📚 **Documentation** | README, guides, tutorials | Technical writing |
| 🧪 **Testing** | Unit tests, integration tests | JUnit, Jest |
| 🔧 **DevOps** | CI/CD, Docker improvements | Docker, GitHub Actions |

---

## 🔄 Development Workflow

### 1. Sync with Upstream

```bash
git fetch upstream
git checkout main
git merge upstream/main
```

### 2. Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/issue-description
```

**Branch naming conventions:**
- `feature/description` - New features
- `fix/description` - Bug fixes
- `docs/description` - Documentation
- `refactor/description` - Code refactoring

### 3. Make Changes

- Write clean, readable code
- Follow existing code style
- Add/update tests as needed
- Update documentation

### 4. Commit

```bash
git add .
git commit -m "feat: add new feature description"
```

### 5. Push and Create PR

```bash
git push origin feature/your-feature-name
```

Then create a Pull Request on GitHub.

---

## 🎨 Style Guidelines

### Java (Backend)

- Follow [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
- Use 4 spaces for indentation
- Maximum line length: 120 characters
- Organize imports (IDE auto-format)

**Example:**
```java
@Service
@RequiredArgsConstructor
@Slf4j
public class DecisionService {
    
    private final DecisionRepository decisionRepository;
    
    public Decision createDecision(DecisionRequest request, String userId) {
        Decision decision = Decision.builder()
            .title(request.title())
            .content(request.content())
            .status(DecisionStatus.PROPOSED)
            .createdBy(userId)
            .build();
        
        return decisionRepository.save(decision);
    }
}
```

### TypeScript/React (Frontend)

- Use 2 spaces for indentation
- Use semicolons
- Use single quotes for strings
- Maximum line length: 100 characters
- Use functional components with hooks

**Example:**
```typescript
interface ButtonProps {
  onClick: () => void;
  children: React.ReactNode;
  variant?: 'primary' | 'secondary';
}

export function Button({ onClick, children, variant = 'primary' }: ButtonProps) {
  return (
    <button
      onClick={onClick}
      className={cn(
        'px-4 py-2 rounded-lg font-medium',
        variant === 'primary' && 'bg-brand-600 text-white',
        variant === 'secondary' && 'bg-gray-200 text-gray-800'
      )}
    >
      {children}
    </button>
  );
}
```

### CSS/Tailwind

- Use Tailwind classes when possible
- Extract reusable patterns to components
- Follow mobile-first responsive design

---

## 💬 Commit Messages

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

**Types:**
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation
- `style` - Formatting (no code change)
- `refactor` - Code refactoring
- `test` - Adding tests
- `chore` - Maintenance tasks

**Examples:**
```
feat(decision): add search by tags functionality

fix(auth): resolve JWT token expiration issue

docs(readme): update installation instructions

refactor(api): simplify error handling
```

---

## 🔍 Pull Request Process

### Before Submitting

- [ ] Code follows style guidelines
- [ ] All tests pass
- [ ] Added tests for new features
- [ ] Updated documentation
- [ ] Commits follow conventional format
- [ ] Branch is up-to-date with main

### PR Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation
- [ ] Refactoring

## Screenshots (if applicable)

## Checklist
- [ ] My code follows the style guidelines
- [ ] I have performed a self-review
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or my feature works
```

### Review Process

1. Maintainers will review within 3-5 days
2. Address review comments
3. Once approved, a maintainer will merge

---

## 🌸 GSSoC Specific Guidelines

### Getting Points

- Comment on the issue you want to work on
- Wait for assignment before starting
- Include `GSSoC'25` in your PR description
- Follow the [GSSoC timeline](https://gssoc.girlscript.tech/)

### Level Guidelines

| Level | Examples | Points |
|-------|----------|--------|
| **Level 1** | Documentation fixes, typos, small UI tweaks | 10 |
| **Level 2** | New components, API endpoints, bug fixes | 25 |
| **Level 3** | Major features, architecture changes | 45 |

> **Note:** Level is assigned by maintainers based on complexity and impact.

### For GSSoC Contributors

1. **Register** on [GSSoC website](https://gssoc.girlscript.tech/)
2. **Join Discord** - Get help and connect with mentors
3. **Check Labels** - Look for `GSSoC`, `good first issue`, `Level 1/2/3`
4. **Ask Questions** - Don't hesitate to ask for clarification

---

## ❓ Need Help?

- **Discord:** Join our community server *(link coming soon)*
- **GitHub Discussions:** [Open a discussion](../../discussions)
- **Email:** [your.email@example.com](mailto:your.email@example.com)

---

## 🎉 Thank You!

Every contribution, no matter how small, helps make MindRepo better. We appreciate your time and effort!

Happy contributing! 🚀
