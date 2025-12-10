# Contributing to Spark Resume AI

First off, thank you for considering contributing to Spark Resume AI! 🎉

This project is built to help job seekers, and your contributions make that mission possible.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)

## Code of Conduct

This project and everyone participating in it is governed by our commitment to:
- Be respectful and inclusive
- Focus on helping job seekers
- Provide constructive feedback
- Accept gracefully when others disagree

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues. When you create a bug report, include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce**
- **Provide specific examples** (code samples, screenshots, etc.)
- **Describe the behavior you observed** and what you expected
- **Include your environment details** (OS, Node.js version, browser, etc.)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion:

- **Use a clear and descriptive title**
- **Provide a detailed description** of the suggested enhancement
- **Explain why this enhancement would be useful** to job seekers
- **List any alternatives** you've considered

### Your First Code Contribution

Unsure where to begin? Look for issues labeled:
- `good first issue` - Simple issues for beginners
- `help wanted` - Issues that need community help
- `documentation` - Improvements to docs

### Pull Requests

1. Fork the repo and create your branch from `main`
2. If you've added code that should be tested, add tests
3. Ensure the test suite passes
4. Make sure your code follows our coding standards
5. Write a clear commit message

## Development Setup

```bash
# Fork and clone the repository
git clone https://github.com/YOUR-USERNAME/spark-resume-ai.git
cd spark-resume-ai

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env
# Add your GOOGLE_GENERATIVE_AI_API_KEY to .env

# Run development server
npm run dev

# Run tests
npm test
```

## Pull Request Process

1. **Update the README.md** if needed with details of changes
2. **Update the CHANGELOG.md** with your changes
3. **Ensure all tests pass** before submitting
4. **Follow the coding standards** below
5. **Write clear commit messages** (see below)
6. **Get approval** from at least one maintainer

### Commit Message Format

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

**Examples:**
```
feat(parser): add support for RTF file format

Add RTF file parsing using rtf-parser library.
This enables users to upload RTF resumes.

Closes #123
```

```
fix(ats): correct keyword matching for hyphenated terms

Previously, "full-stack" was treated as two separate keywords.
Now it's correctly matched as a single hyphenated term.

Fixes #456
```

## Coding Standards

### TypeScript

- Use TypeScript for all new code
- Prefer `interface` over `type` for object shapes
- Use explicit return types for functions
- Avoid `any` type unless absolutely necessary

### Code Style

- Use 2 spaces for indentation
- Use single quotes for strings
- Add trailing commas in objects and arrays
- Maximum line length: 100 characters
- Add JSDoc comments for public functions

### Naming Conventions

- **Files**: `kebab-case.ts` (e.g., `resume-parser.ts`)
- **Components**: `PascalCase` (e.g., `ResumeUploader`)
- **Functions**: `camelCase` (e.g., `parseResume`)
- **Constants**: `UPPER_SNAKE_CASE` (e.g., `MAX_FILE_SIZE`)

### Example

```typescript
/**
 * Parse resume file and extract text content
 * @param file - The resume file to parse
 * @returns Parsed resume text or null if parsing fails
 */
export async function parseResumeFile(file: File): Promise<string | null> {
  if (!isValidFileType(file)) {
    throw new Error('Unsupported file type');
  }

  const text = await extractText(file);
  return cleanText(text);
}
```

## Testing

- Write unit tests for new features
- Ensure tests pass before submitting PR
- Aim for at least 80% code coverage
- Test edge cases and error conditions

```bash
# Run all tests
npm test

# Run tests in watch mode
npm run test:watch

# Check coverage
npm run test:coverage
```

## Documentation

- Update README.md if you change functionality
- Add JSDoc comments for public APIs
- Include code examples for new features
- Update CHANGELOG.md with your changes

## Questions?

Feel free to:
- Open an issue with your question
- Check existing issues and discussions
- Reach out to maintainers

## Attribution

This Contributing Guide is adapted from open source projects and the [Contributor Covenant](https://www.contributor-covenant.org/).

---

**Thank you for helping job seekers! Your contributions make a real difference.** 💙
