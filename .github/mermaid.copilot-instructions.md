---
applyTo: **/*.mmd
---

# Mermaid Diagram Styling Guidelines

When creating or editing Mermaid diagrams, follow Microsoft Fluent Design principles for consistency and professional appearance.

## Microsoft Design Principles

### Color Palette

Use Microsoft's official color scheme:

- **Primary Blue**: `#0078d4` (Microsoft Blue) - for primary components and emphasis
- **Secondary Colors**:
  - Light Blue: '#e1f5ff' - backgrounds for client/user-facing components
  - Orange: '#ff8c00' - server/backend components
  - Green: '#28a745' - success states, completed processes
  - Purple: '#d946ef' - AI/ML services, specialized processing
  - Red: '#dc3545' - security, authentication, errors
  - Yellow: '#ffc107' - monitoring, observability, warnings
  - Gray: '#666', '#888', '#f5f5f5' - external systems, supporting elements

### Typography

- Use clear, readable labels with proper hierarchy
- Use '<br/>' (not '\n') for multi-line text in node labels
- Keep labels concise (3-7 words preferred)
- Add context in parentheses: 'Component Name<br/>(Purpose/Details)'

### Visual Hierarchy

1. **Primary Flow**: Use solid lines with standard arrows ('-->')
2. **Secondary/Optional**: Use dotted lines ('-.->') or dashed lines ('--')
3. **Data Flow**: Use labeled arrows with descriptive text
4. **Grouping**: Use subgraphs with descriptive labels in square brackets

### Styling Classes

Define consistent 'classDef' styles:

'''mermaid
classDef client fill:#e1f5ff,stroke:#0078d4,stroke-width:2px
classDef server fill:#fff4e1,stroke:#ff8c00,stroke-width:2px
classDef ai fill:#ffe1f5,stroke:#d946ef,stroke-width:2px
classDef data fill:#f5f5f5,stroke:#666,stroke-width:1px
classDef security fill:#ffe1e1,stroke:#dc3545,stroke-width:2px
classDef monitoring fill:#fff9e1,stroke:#ffc107,stroke-width:2px
classDef external fill:#f5f5f5,stroke:#666,stroke-width:1px,stroke-dasharray:5 5
'''

### Accessibility

- Ensure sufficient contrast between fill and stroke colors
- Use stroke-width of at least 1px (2px for emphasis)
- Avoid relying solely on color to convey meaning (use labels, patterns, line styles)
- Test readability in both light and dark modes

## Diagram-Specific Guidelines

### Flowcharts

- Use 'flowchart TB' (top-bottom) or 'flowchart LR' (left-right) based on content flow
- Group related components in subgraphs
- Use decision diamonds '{Question?}' sparingly
- Show error paths with dashed lines

### Sequence Diagrams

- Use clear actor/participant names
- Add notes for important context: 'Note over A,B: Context'
- Group related interactions with 'alt', 'opt', 'loop' blocks
- Use activation boxes for async operations

### Component Diagrams

- Primary components: solid blue borders, light fills
- External systems: gray with dashed borders
- Data stores: orange tones
- Security components: red tones

## Best Practices

1. **Consistency**: Use the same styling approach across all diagrams in the project
2. **Simplicity**: Avoid over-styling; clarity is more important than decoration
3. **Hierarchy**: Use visual weight (stroke-width, colors) to show importance
4. **Whitespace**: Don't overcrowd diagrams; split complex diagrams into multiple views
5. **Labels**: Always label arrows with action verbs or data descriptions

## Example Template

'''mermaid
flowchart LR
    subgraph Client["Client Layer"]
        User["User<br/>(Browser/IDE)"]
    end
    
    subgraph Azure["Azure Services"]
        API["API Gateway<br/>(Entry Point)"]
        Service["Business Logic<br/>(Core Service)"]
    end
    
    subgraph Data["Data Layer"]
        DB["Database<br/>(Persistence)"]
    end
    
    User -->|"HTTPS Request"| API
    API -->|"Process"| Service
    Service -->|"Query"| DB
    
    classDef client fill:#e1f5ff,stroke:#0078d4,stroke-width:2px
    classDef azure fill:#fff4e1,stroke:#ff8c00,stroke-width:2px
    classDef data fill:#f5f5f5,stroke:#666,stroke-width:1px
    
    class User client
    class API,Service azure
    class DB data
'''

## Validation Checklist

Before committing a Mermaid diagram, ensure:

- [ ] Uses Microsoft color palette
- [ ] All multi-line labels use '<br/>' not '\n'
- [ ] Consistent 'classDef' styling applied
- [ ] No syntax errors (validate at mermaid.live)
- [ ] Labels are clear and concise
- [ ] Sufficient contrast for accessibility
- [ ] Follows left-to-right or top-to-bottom flow logic
