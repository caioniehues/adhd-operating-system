# Contributing to ADHD Operating System

First off, thank you for considering contributing to ADHD-OS! It's people like you who make ADHD-OS such a great tool for the ADHD community.

## 🤝 Code of Conduct

This project and everyone participating in it is governed by our Code of Conduct. By participating, you are expected to uphold this code. 

### Our Standards

- **Be Kind**: We're all here to help each other
- **Be Patient**: Remember that ADHD affects everyone differently
- **Be Inclusive**: Welcome all neurotypes and backgrounds
- **Be Understanding**: Not everyone has the same energy levels or availability

## 🎯 How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples**
- **Describe the behavior you observed and expected**
- **Include screenshots if possible**
- **Include your environment details** (OS, Obsidian version, etc.)

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

- **Use a clear and descriptive title**
- **Provide a detailed description of the suggested enhancement**
- **Explain why this enhancement would be useful to ADHD users**
- **List any alternative solutions you've considered**

### Your First Code Contribution

Unsure where to begin? Look for these tags in our issues:

- `good first issue` - Simple issues perfect for beginners
- `help wanted` - Issues where we need help
- `quick win` - Small tasks that can be completed quickly (great for ADHD!)

### Pull Requests

1. Fork the repo and create your branch from `main`
2. If you've added code, add tests
3. If you've changed APIs, update documentation
4. Ensure tests pass
5. Make sure your code follows our style guide
6. Issue that pull request!

## 📝 Development Process

### Setting Up Your Environment

```bash
# Clone your fork
git clone https://github.com/your-username/adhd-operating-system.git
cd adhd-operating-system

# Add upstream remote
git remote add upstream https://github.com/original/adhd-operating-system.git

# Install dependencies
npm install

# Run tests
npm test
```

### Coding Style

- Use meaningful variable names
- Comment complex logic
- Keep functions small and focused
- Follow existing patterns in the codebase

### Commit Messages

We follow conventional commits:

```
feat: add pomodoro timer
fix: correct time calculation in daily notes
docs: update setup instructions
style: format code with prettier
test: add tests for habit tracking
```

### Testing

- Write tests for new features
- Ensure all tests pass before submitting PR
- Include both unit and integration tests where appropriate

## 🧠 ADHD-Friendly Contributing Tips

### Breaking Down Tasks

1. **Start Small**: Pick one tiny thing to fix
2. **Use Timers**: Work in 25-minute chunks
3. **Document as You Go**: Write notes while the context is fresh
4. **Ask for Help**: We're here to support you!

### Managing Overwhelm

- It's okay to submit incomplete PRs with [WIP] tag
- Take breaks when needed
- Focus on one issue at a time
- Use our Discord for real-time help

### Time Management

- Set realistic deadlines for yourself
- Communicate if you need more time
- It's okay to abandon a PR if you lose interest

## 📊 Task Master Integration

We use Task Master to manage our development tasks:

```bash
# See available tasks
task-master list

# Pick up a community task
task-master next --tag=community

# Track your progress
task-master set-status --id=<task-id> --status=in-progress
```

## 🎉 Recognition

All contributors will be added to our [CONTRIBUTORS.md](CONTRIBUTORS.md) file and receive:

- 🏆 Contributor badge on Discord
- 📜 Certificate of contribution
- 💝 Our eternal gratitude!

## 📞 Getting Help

- **Discord**: Join our [Discord server](https://discord.gg/adhd-os)
- **Discussions**: Use [GitHub Discussions](https://github.com/yourusername/adhd-operating-system/discussions)
- **Office Hours**: Weekly help sessions on Discord (Thursdays 7PM EST)

## 🔄 Release Process

1. Features are developed in feature branches
2. PRs are reviewed by at least one maintainer
3. Approved PRs are merged to `develop`
4. Weekly releases from `develop` to `main`
5. Hotfixes go directly to `main` with backport to `develop`

## 📚 Additional Resources

- [Project Roadmap](https://github.com/yourusername/adhd-operating-system/projects/1)
- [Architecture Docs](docs/ARCHITECTURE.md)
- [API Documentation](docs/API.md)
- [Testing Guide](docs/TESTING.md)

---

Remember: **Your contributions matter, no matter how small!** Every bug fix, feature, or even typo correction helps make ADHD-OS better for everyone.

Thank you for being part of our community! 💜