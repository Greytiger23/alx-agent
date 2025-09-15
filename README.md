# ALX Code Review Agent

A sophisticated AI-powered code review agent built with TypeScript that provides comprehensive, constructive feedback on code changes in your repository. This agent leverages Google's Gemini 2.5 Flash model to deliver expert-level code reviews with a focus on best practices, maintainability, and collaborative development.

## 🚀 What This Agent Does

The ALX Code Review Agent is designed to act as an expert code reviewer with years of experience in software engineering. It automatically analyzes code changes in your repository and provides detailed, actionable feedback across multiple dimensions:

### Core Functionality
- **Automated Code Analysis**: Scans git diffs to identify all changed files in a specified directory
- **Intelligent Review**: Provides comprehensive feedback on code quality, structure, and best practices
- **Contextual Understanding**: Analyzes code changes within the context of your entire codebase
- **Streaming Output**: Delivers real-time feedback as the analysis progresses

### Review Focus Areas

The agent evaluates code across 8 critical dimensions:

1. **Correctness** - Identifies bugs, logic errors, edge cases, and potential regressions
2. **Clarity** - Assesses code readability, naming conventions, and structural clarity
3. **Maintainability** - Evaluates code complexity, duplication, and coupling
4. **Consistency** - Ensures adherence to existing codebase conventions and patterns
5. **Performance** - Identifies inefficiencies and potential bottlenecks
6. **Security** - Detects vulnerabilities, injection risks, and unsafe operations
7. **Testing** - Reviews test coverage and test quality
8. **Scalability & Robustness** - Assesses error handling and scalability considerations

## 🛠️ Tools and Technologies

### Core Dependencies

- **AI SDK (`ai`)** - Framework for building AI applications with streaming capabilities
- **Google AI SDK (`@ai-sdk/google`)** - Integration with Google's Gemini models
- **Simple Git (`simple-git`)** - Git operations and diff analysis
- **Zod (`zod`)** - Runtime type validation and schema definition
- **TypeScript** - Type-safe development environment
- **Bun** - Fast JavaScript runtime and package manager

### AI Model
- **Google Gemini 2.5 Flash** - Advanced language model optimized for code understanding and analysis

### Custom Tools

#### `getFileChangesInDirectoryTool`
A specialized tool that:
- Analyzes git diffs in a specified directory
- Extracts file changes and modifications
- Filters out excluded files (dist, bun.lock, etc.)
- Returns structured diff data for AI analysis

**Input Schema:**
```typescript
{
  rootDir: string // The root directory to analyze
}
```

**Output:**
```typescript
{
  file: string,    // File path
  diff: string     // Git diff content
}[]
```

## 📁 Project Structure

```
my-agent/
├── index.ts          # Main agent entry point
├── prompts.ts        # System prompts and AI instructions
├── tools.ts          # Custom tools and utilities
├── package.json      # Dependencies and project configuration
├── tsconfig.json     # TypeScript configuration
├── bun.lock         # Dependency lock file
├── .gitignore       # Git ignore rules
└── README.md        # Project documentation
```

## 🎯 Agent Personality & Approach

The agent is designed with a specific personality that emphasizes:

- **Professional & Collaborative** - Maintains a respectful, team-oriented approach
- **Educational** - Provides teaching moments and explains the "why" behind suggestions
- **Constructive** - Focuses on actionable improvements rather than criticism
- **Empathetic** - Considers the author's intent and experience level

### Review Style
- Uses clear, jargon-free language
- Provides specific improvement suggestions
- Acknowledges well-written code
- Distinguishes between critical issues and minor nitpicks
- Explains the reasoning behind each recommendation

## 🚦 Usage

The agent is configured to review code changes with a simple command:

```typescript
await codeReviewAgent(
  "Review the code changes in '../my-agent' directory, make your reviews and suggestions file by file"
);
```

### Key Features:
- **Step Limiting**: Configured with a maximum of 10 steps to ensure efficient processing
- **Streaming Output**: Real-time feedback delivery
- **Directory-Specific**: Can target specific directories for focused reviews
- **Git Integration**: Automatically detects and analyzes git changes

## 🔧 Configuration

### Excluded Files
The agent automatically excludes certain files from review:
- `dist/` - Build output directories
- `bun.lock` - Dependency lock files

### Model Configuration
- **Model**: Google Gemini 2.5 Flash
- **Max Steps**: 10
- **Streaming**: Enabled for real-time output

## 🎯 Benefits

1. **Consistent Reviews** - Provides standardized, high-quality code reviews
2. **Time Savings** - Automates the initial review process
3. **Learning Tool** - Helps developers improve their coding skills
4. **Quality Assurance** - Catches issues before they reach production
5. **Best Practices** - Enforces coding standards and conventions
6. **Scalability** - Can handle large codebases efficiently

## 🔮 Future Enhancements

Potential areas for expansion:
- Integration with popular code hosting platforms (GitHub, GitLab)
- Custom rule configuration
- Multi-language support optimization
- Integration with CI/CD pipelines
- Collaborative review workflows
- Historical analysis and trend reporting

---

*This agent represents a modern approach to automated code review, combining the power of advanced AI models with practical software engineering expertise to enhance code quality and developer productivity.*