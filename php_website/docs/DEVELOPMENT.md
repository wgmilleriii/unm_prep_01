# Development Guide for UNM Music Preparatory Division Documentation

## Development Environment Setup

### Prerequisites
- Git
- Markdown editor (recommended: VS Code with Markdown extensions)
- Access to private repository
- UNM network access

### Local Development Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/unm-music/unm_prep_01_private.git
   cd unm_prep_01_private
   ```

2. Configure Git:
   ```bash
   git config user.name "Your Name"
   git config user.email "your.email@unm.edu"
   ```

3. Install recommended VS Code extensions:
   - Markdown All in One
   - Markdown Preview Enhanced
   - GitLens

## Project Structure

### Directory Organization
```
unm_prep_01_private/
├── prompts/                 # AI prompt templates
│   ├── FACULTY_DEVELOPMENT/ # Faculty-related prompts
│   └── STUDENT_EVALUATION/  # Student evaluation prompts
├── docs/                    # Documentation files
├── templates/               # Document templates
└── scripts/                 # Utility scripts
```

### File Naming Conventions
- Use UPPERCASE for prompt files
- Use lowercase with hyphens for documentation files
- Include version numbers where appropriate
- Use descriptive names that indicate content

## Development Workflow

### Branch Strategy
- `main`: Production-ready documentation
- `develop`: Development branch
- `feature/*`: New features
- `bugfix/*`: Bug fixes
- `release/*`: Release preparation

### Commit Guidelines
- Use present tense ("Add feature" not "Added feature")
- Keep first line under 50 characters
- Provide detailed description if needed
- Reference issue numbers when applicable

### Pull Request Process
1. Create feature branch
2. Make changes
3. Update documentation
4. Submit PR with description
5. Address review comments
6. Merge after approval

## Documentation Standards

### Markdown Formatting
- Use ATX headers (# style)
- Include table of contents
- Use fenced code blocks
- Follow consistent spacing

### Content Guidelines
- Keep paragraphs short
- Use lists for multiple items
- Include examples where helpful
- Cross-reference related documents

## Testing and Validation

### Documentation Testing
- Verify all links work
- Check formatting consistency
- Validate markdown syntax
- Review sensitive information

### Automated Checks
- Run markdown linting
- Check for broken links
- Validate file structure
- Review access controls

## Deployment

### Staging
1. Create staging branch
2. Review changes
3. Test documentation
4. Validate formatting

### Production
1. Merge to main
2. Update version numbers
3. Generate changelog
4. Deploy updates

## Maintenance

### Regular Tasks
- Update version numbers
- Review and update links
- Clean up old branches
- Archive outdated content

### Backup Procedures
- Regular repository backups
- Document version history
- Maintain change logs
- Store sensitive data securely

## Troubleshooting

### Common Issues
- Git authentication problems
- Markdown rendering issues
- Access control conflicts
- Version control conflicts

### Support Resources
- Git documentation
- Markdown guides
- Internal wiki
- Team documentation

## Security Considerations

### Access Control
- Review permissions regularly
- Monitor access logs
- Update security policies
- Protect sensitive data

### Data Protection
- Encrypt sensitive files
- Use secure connections
- Follow UNM security guidelines
- Regular security audits

## Contact and Support

### Development Team
- Technical Lead: [Name]
- Documentation Manager: [Name]
- Security Officer: [Name]

### Resources
- Internal documentation
- Development wiki
- Team meetings
- Training sessions 