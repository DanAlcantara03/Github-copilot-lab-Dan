---
description: Blazor component development patterns and best practices for this bingo game project.
---

# Blazor Component Development

## Component Structure

### Basic Component Pattern
Use Razor syntax with `@code` block for logic. Follow this structure:

```razor
@using SocOps.Models

<!-- Markup -->
<div class="...">
    <!-- Content -->
</div>

@code {
    // Parameters
    [Parameter]
    public required Type Property { get; set; }

    // Event callbacks
    [Parameter]
    public EventCallback OnEvent { get; set; }

    // Private methods
    private void HandleEvent() => OnEvent.InvokeAsync();
}
```

### Key Patterns Used in This Project

1. **Parameter Binding**: Use `[Parameter]` for parent-to-child data flow
2. **Event Callbacks**: Use `EventCallback<T>` for child-to-parent communication
3. **CSS Utilities**: Leverage the custom CSS classes from `app.css` for styling
4. **Accessibility**: Include `aria-*` attributes and proper semantic HTML
5. **State Management**: Use services for shared state, local storage for persistence

### BingoSquare Example
- Uses conditional styling based on state (`IsMarked`, `IsWinning`)
- Implements click handling with `EventCallback`
- Includes accessibility attributes (`aria-pressed`, `aria-label`)
- Uses CSS utilities for responsive design

### BingoBoard Example
- Renders a grid of child components
- Passes data and event handlers via parameters
- Uses `aspect-square` for consistent proportions

## Services Integration

### BingoGameService
- Manages global game state
- Handles persistence with localStorage via IJSRuntime
- Provides events for UI updates (`OnStateChanged`)

### BingoLogicService
- Pure functions for game logic (no dependencies)
- Generates boards, checks wins, toggles squares
- Easy to test and reuse

## Best Practices

- Keep components focused on presentation logic
- Use services for business logic and state management
- Prefer CSS utilities over inline styles
- Include accessibility features
- Use meaningful parameter names and types
- Handle async operations properly with `await`

## Common Patterns

- **Conditional Rendering**: `@if (condition) { ... }`
- **Loops**: `@foreach (var item in items) { ... }`
- **Event Handling**: `@onclick="HandleClick"`
- **Two-way Binding**: `@bind-Value="property"` (rarely used here)
- **Child Components**: `<ChildComponent Param="value" OnEvent="HandleEvent" />`</content>
<parameter name="filePath">/workspaces/Github-copilot-lab-Dan/.github/instructions/blazor-components.instructions.md