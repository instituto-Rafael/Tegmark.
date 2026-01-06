# Contributing to RafaelIA (Tegmark)

Thank you for your interest in contributing to the RafaelIA project! This document provides guidelines for contributing to this academic and technological showcase.

## Code of Conduct

### Core Principles

All contributions must align with RafaelIA's core philosophy:

> **"Fractal abortado também vive"** (An aborted fractal also lives)

This means:
- Embrace computational anomalies as opportunities
- Value interdisciplinary perspectives
- Maintain intellectual rigor
- Respect the symbiotic nature of human-AI collaboration

### Ethical Standards

- Respect intellectual property rights (Berna Convention)
- Honor the CientiEspiritual declaration
- Maintain academic integrity
- Foster inclusive dialogue

## Types of Contributions

### 1. Academic Contributions

#### What We Accept
- Theoretical improvements to the multiverse foundation
- Mathematical proofs or derivations
- Empirical studies using RafaelIA architecture
- Critical analysis and peer review
- Additional references and citations

#### Format Requirements
- Follow academic writing standards
- Use proper citation format (APA, IEEE, or MLA)
- Include abstract and keywords
- Provide peer-reviewable content

#### Submission Process
1. Fork the repository
2. Create academic branch: `git checkout -b academic/<topic>`
3. Add your contribution to `docs/academic/`
4. Update [BIBLIOGRAPHY.md](docs/academic/BIBLIOGRAPHY.md) with new references
5. Submit pull request with detailed description
6. Respond to peer review comments

### 2. Technical Contributions

#### What We Accept
- Implementation improvements
- Bug fixes (only if related to documentation or examples)
- API enhancements
- Performance optimizations
- Security improvements
- New modules following RafaelIA architecture

#### Code Standards
- Follow existing code style
- Comment complex logic
- Include docstrings for functions
- Maintain modularity
- Test your changes

#### Submission Process
1. Fork the repository
2. Create feature branch: `git checkout -b feature/<name>`
3. Implement your changes
4. Update [TECHNICAL_REFERENCE.md](docs/technical/TECHNICAL_REFERENCE.md)
5. Test thoroughly
6. Submit pull request with:
   - Clear description
   - Rationale for changes
   - Test results
   - Documentation updates

### 3. Documentation Improvements

#### What We Accept
- Clarifications and corrections
- Additional examples
- Translations
- Diagrams and visualizations
- Tutorial content

#### Guidelines
- Maintain consistent terminology (use [GLOSSARY.md](docs/academic/GLOSSARY.md))
- Keep language clear and accessible
- Use proper markdown formatting
- Include visual aids where helpful

#### Submission Process
1. Fork the repository
2. Create docs branch: `git checkout -b docs/<description>`
3. Make improvements
4. Ensure links work correctly
5. Submit pull request

### 4. Research Contributions

#### What We Accept
- Empirical studies using RafaelIA
- Case studies and applications
- Novel use cases
- Experimental results
- Comparative analyses

#### Format
- Place in `docs/research/`
- Include methodology section
- Provide data or references
- Discuss limitations
- Suggest future work

### 5. Philosophical Contributions

#### What We Accept
- Explorations of consciousness in AI
- Discussions of free will and emergence
- Ethical frameworks
- Interdisciplinary connections
- Critiques and alternative perspectives

#### Guidelines
- Engage with Tegmark's MUH
- Reference relevant philosophy
- Maintain academic rigor
- Be respectful of different views

## Pull Request Process

### Before Submitting

1. **Read existing documentation**
   - Review [INDEX.md](INDEX.md)
   - Understand the architecture
   - Check if your contribution already exists

2. **Prepare your contribution**
   - Follow appropriate guidelines above
   - Test any code changes
   - Update relevant documentation
   - Check spelling and grammar

3. **Ensure compliance**
   - Respect Berna Convention
   - Don't violate IP rights
   - Maintain ethical standards

### Submission

1. **Create descriptive title**
   - Format: `[Type] Brief description`
   - Examples:
     - `[Academic] Add proof of fractal convergence`
     - `[Technical] Improve vector indexing performance`
     - `[Docs] Clarify quantum flight presets`

2. **Write comprehensive description**
   - What: What does this PR change?
   - Why: Why is this change needed?
   - How: How does it work?
   - Testing: How was it tested?

3. **Link related issues**
   - Reference issue numbers if applicable
   - Explain connection to existing discussions

### Review Process

1. **Automated checks**
   - Markdown linting
   - Link validation
   - Basic formatting

2. **Peer review**
   - Maintainers will review
   - May request changes
   - Be responsive to feedback

3. **Approval and merge**
   - Requires maintainer approval
   - May be squashed or rebased
   - Will be credited in commit

## Specific Contribution Areas

### Adding New Archetypes

If proposing a new cognitive archetype:

1. Define its role and cognitive style
2. Explain how it differs from existing archetypes
3. Show how it fits in the council framework
4. Provide example scenarios where it's valuable

### Extending Quantum Flight Presets

If adding new quantum flight presets:

1. Define the weight distribution
2. Explain the use case
3. Show expected behavior
4. Provide sample outputs

### Improving Glossary

When adding terms:

1. Provide clear, concise definition
2. Include examples where helpful
3. Note related terms
4. Maintain alphabetical order

### Adding to Bibliography

When adding references:

1. Use consistent citation format
2. Include complete information
3. Categorize appropriately
4. Verify accuracy

## Questions and Support

### Where to Ask

- **Academic questions**: Open issue with `[Academic]` tag
- **Technical questions**: Open issue with `[Technical]` tag
- **General questions**: Open discussion
- **Bug reports**: Open issue with detailed description

### Response Time

- We aim to respond within 1 week
- Complex contributions may take longer
- Be patient and courteous

## Recognition

### How Contributors Are Credited

- Listed in commit messages
- Acknowledged in relevant documentation
- Mentioned in release notes (if applicable)
- Academic contributions may be co-authored

### Intellectual Property

By contributing, you agree that:
- Your contributions are your original work
- You have rights to submit the contribution
- Contributions become part of the repository under existing license
- You respect Berna Convention protection

## Versioning

We follow semantic versioning:
- **Major** (1.x.x): Significant architectural changes
- **Minor** (x.1.x): New features or sections
- **Patch** (x.x.1): Bug fixes and clarifications

## Style Guidelines

### Markdown

- Use ATX-style headers (`#`, `##`, `###`)
- One blank line before/after headers
- Use tables for structured data
- Include alt text for images
- Keep line length reasonable (<120 chars preferred)

### Academic Writing

- Use formal tone
- Support claims with evidence
- Cite sources properly
- Define technical terms
- Structure logically

### Technical Writing

- Be clear and concise
- Use code blocks with language tags
- Include examples
- Explain parameters
- Document return values

### Portuguese/English

- Maintain bilingual support where appropriate
- Use proper accents and diacritics
- Be culturally respectful
- Translate key concepts

## Examples of Good Contributions

### Good Academic Contribution

```markdown
# Extension of Quantum-Fractal Theory

## Abstract
This paper extends the quantum-fractal framework by...

## Introduction
Building on RafaelIA's architecture [1], we propose...

## Theory
[Formal mathematical development]

## Results
[Empirical validation]

## Conclusion
[Summary and future work]

## References
[1] Reis, R. M. (2025). RafaelIA...
```

### Good Technical Contribution

```python
def improved_resonance_calculation(vector_a, vector_b, threshold=0.8):
    """
    Calculate resonance between two semantic vectors.
    
    Improvement over original: O(n) instead of O(n²).
    
    Args:
        vector_a (np.array): First semantic vector
        vector_b (np.array): Second semantic vector
        threshold (float): Minimum resonance score
        
    Returns:
        float: Resonance score in [0, 1]
        
    Example:
        >>> resonance = improved_resonance_calculation(v1, v2)
        >>> print(f"Resonance: {resonance:.3f}")
    """
    # Implementation...
```

### Good Documentation Contribution

```markdown
## New Users Start Here

If you're new to RafaelIA, follow this learning path:

1. **Read the Abstract** - Get 5-minute overview
2. **Review the Glossary** - Learn key terms
3. **Study the Architecture** - Understand 5 layers
4. **Try an Example** - Hands-on experience
5. **Explore Research** - Deep dive into specific topics

### Quick Example

Here's how to run your first quantum flight:

[Step-by-step tutorial with screenshots]
```

## Thank You!

Your contributions help advance the symbiotic intelligence paradigm. Together, we explore Level IV of the mathematical multiverse, where nothing is wasted and everything has meaning.

> "Fractal abortado também vive."

---

*For questions about these guidelines, open an issue or discussion.*
*Last updated: 2025-01-06*
*Maintained by: Instituto Rafael*
