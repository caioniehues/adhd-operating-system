# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

ADHD Operating System (ADHD-OS) is an Obsidian plugin designed specifically for individuals with ADHD. It transforms Obsidian into a comprehensive life management system with features tailored to ADHD cognitive patterns.

## Development Commands

### Setup
```bash
npm install              # Install dependencies
npm run dev             # Start development build with hot-reload
```

### Build Commands
```bash
npm run build           # Build for production
npm run build:dev       # Build for development
```

### Test Commands  
```bash
npm run test            # Run all tests
npm run test:unit       # Run unit tests only
npm run test:e2e        # Run end-to-end tests
npm run test:coverage   # Generate coverage report
```

### Code Quality
```bash
npm run lint            # Run ESLint
npm run lint:fix        # Auto-fix linting issues
npm run typecheck       # Run TypeScript type checking
npm run format          # Format code with Prettier
```

## Architecture

### Technology Stack
- **Language**: TypeScript 5.0+
- **Framework**: Obsidian Plugin API
- **Build Tool**: Vite with ESBuild
- **Testing**: Vitest + Testing Library
- **State Management**: Zustand
- **Styling**: CSS Modules + Obsidian Theme Variables

### Project Structure
```
adhd-operating-system/
├── src/
│   ├── core/               # Core functionality
│   │   ├── task-management/
│   │   ├── daily-notes/
│   │   ├── memory/
│   │   └── time-awareness/
│   ├── features/           # Feature modules
│   │   ├── inbox/
│   │   ├── focus-tools/
│   │   ├── crisis-mode/
│   │   └── analytics/
│   ├── ui/                # UI components
│   ├── utils/             # Utilities
│   └── main.ts           # Plugin entry
├── tests/                 # Test files
├── docs/                  # Documentation
└── manifest.json         # Obsidian plugin manifest
```

## Key Design Principles

### ADHD-First Development
1. **Simplicity**: Every feature must reduce, not add, cognitive load
2. **Visual Clarity**: Clear visual hierarchy and feedback
3. **Progressive Disclosure**: Show only what's needed when it's needed
4. **Forgiving UX**: Easy undo, no shame for mistakes
5. **Time Awareness**: Combat time blindness with visual cues
6. **Crisis Support**: Always provide an escape hatch for overwhelm

### Code Standards
1. **TypeScript**: Use strict mode, explicit types
2. **Error Handling**: Helpful, encouraging error messages
3. **Performance**: Optimize for large vaults (10k+ notes)
4. **Accessibility**: WCAG AA compliance minimum
5. **Testing**: Test ADHD-specific scenarios
6. **Documentation**: Clear comments for complex logic

## GitHub Actions Integration

When @claude is mentioned in issues or PRs, follow these guidelines:

### For Implementation Requests
1. Create focused, single-purpose PRs
2. Include tests for new features
3. Consider ADHD edge cases (overwhelm, time blindness)
4. Add helpful JSDoc comments
5. Update relevant documentation

### For Code Reviews
1. Check cognitive load implications
2. Verify accessibility compliance
3. Ensure error messages are helpful
4. Look for performance impacts
5. Validate ADHD-friendly UX patterns

### For Bug Fixes
1. Add regression tests
2. Consider why the bug impacts ADHD users
3. Improve error handling if relevant
4. Document the fix clearly

## Critical Features

### Must-Have for MVP
- Daily note system with ADHD templates
- Task management with auto-breakdown
- Quick capture inbox
- Time awareness tools
- Crisis mode

### Performance Requirements
- Plugin load time < 2s
- Task operations < 100ms
- Search results < 500ms
- Smooth UI animations (60fps)

## Testing Scenarios

Always test these ADHD-specific cases:
1. User in crisis/overwhelm mode
2. Many incomplete tasks (100+)
3. Rapid context switching
4. Time blindness scenarios
5. Medication reminder edge cases
6. Mobile usage patterns

## Common Patterns

### Task Creation
```typescript
// Always include ADHD-friendly fields
interface ADHDTask {
  id: string;
  title: string;
  estimatedTime: number; // with 40% buffer
  energyRequired: 'low' | 'medium' | 'high';
  interest: number; // 1-5 scale
  isQuickWin: boolean;
  deferralCount: number; // no shame counting
}
```

### Error Messages
```typescript
// Encouraging, not discouraging
throw new Error("No worries! Let's try that again. The file couldn't be saved because...");
```

### UI Patterns
- Use Obsidian's CSS variables for consistency
- Implement focus trap for modals
- Provide keyboard shortcuts for everything
- Show progress visually, not just numerically

## Task Master AI Instructions
**Import Task Master's development workflow commands and guidelines, treat as if import is in the main CLAUDE.md file.**
@./.taskmaster/CLAUDE.md