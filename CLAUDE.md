# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a hub repository for Aloe.Utils utility libraries that serves as both a collection point and template for related repositories. The repository manages multiple .NET utility libraries focused on common programming tasks, text processing, Japanese language utilities, and Windows-specific operations.

## Project Architecture

- **Hub Structure**: This repository links to 15+ separate utility libraries, each maintained in their own repositories
- **Template Repository**: Serves as a template for creating new utility libraries in the Aloe.Utils ecosystem
- **.NET 9.0 Target**: All utilities target .NET 9.0 and are published as NuGet packages
- **Library Categories**:
  - Core utilities (CommandLine, Configuration, SafeIO)
  - Text processing (Text, Json)
  - Drawing operations (Drawing, Drawing.Wpf)
  - Japanese language support (Wafu.* libraries)
  - Windows-specific utilities (Win32.ScCommand)

## Development Commands

### Build Commands
```bash
# Build a specific project (from src directory)
dotnet build .\Aloe.Utils.Template\Aloe.Utils.Template.csproj -c Release

# Publish application
dotnet publish .\Aloe.Utils.Template\Aloe.Utils.Template.csproj -c Release -r win-x64 -o .\publish\AloeUtilsTemplate

# Create NuGet package
dotnet pack .\Aloe.Utils.Template\Aloe.Utils.Template.csproj -c Release -o .\publish
```

### Utility Scripts
```bash
# Clean build artifacts and temporary files (from src directory)
.\_clean_workdirs.cmd

# Build, publish, and package (from src directory) 
.\_publish.cmd
```

## Code Standards

### Implementation Standards
- Use dependency injection pattern with appropriate interfaces
- Implement proper async/await patterns for I/O operations
- Include comprehensive error handling with structured logging
- Follow MVVM pattern where applicable
- Use `ILogger<T>` for all logging operations

### Naming Conventions
- Classes: PascalCase
- Methods: PascalCase  
- Variables: camelCase
- Constants: UPPER_CASE
- Interfaces: I prefix (IPascalCase)

### Code Style
- Indentation: 4 spaces
- Line length: 120 characters maximum
- Use XML documentation comments for public APIs
- Include proper exception handling with specific exception types

## Knowledge Management

The project uses structured documentation in `.cursor/rules/` directory for maintaining consistency:
- Reference `./doc` directory for accumulated knowledge
- Document new implementation patterns and decisions
- Maintain implementation consistency across utilities

## Repository Structure

Each utility library follows a consistent structure with separate repositories linked from the main README. When working with a specific utility, check if it exists as a separate repository or if it's being developed as part of the template structure in `src/`.