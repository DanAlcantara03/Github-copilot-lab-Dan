---
description: Overall guidance for working with the SocOps Blazor bingo game project.
---

# SocOps Project Guidelines

## Project Overview
SocOps is a Blazor WebAssembly application implementing a social bingo game for in-person mixers. Players find people matching question prompts to get 5 in a row.

## Technology Stack
- **Framework**: .NET 10 Blazor WebAssembly
- **Styling**: Custom CSS utilities (Tailwind-like classes in `app.css`)
- **Architecture**: Component-based with services for state management
- **Persistence**: Local storage via JavaScript interop

## Development Workflow
1. **Setup**: Use `dotnet run` to start development server
2. **Build**: `dotnet build` for compilation checks
3. **Test**: Manual testing in browser (localhost:5166)
4. **Deploy**: Automatic GitHub Pages deployment on main branch

## Code Organization
- **Components**: Razor components in `Components/` folder
- **Services**: Business logic in `Services/` folder
- **Models**: Data structures in `Models/` folder
- **Data**: Static data like questions in `Data/` folder
- **Pages**: Blazor pages in `Pages/` folder

## Key Principles
- **Accessibility**: Include ARIA attributes and semantic HTML
- **Performance**: Minimize re-renders, use efficient data structures
- **Maintainability**: Clear separation of concerns, descriptive names
- **User Experience**: Smooth animations, clear feedback, responsive design

## Common Tasks
- **Add Questions**: Edit `Data/Questions.cs`
- **Modify Styling**: Update `wwwroot/css/app.css` or use utilities
- **Change Logic**: Update services in `Services/` folder
- **Add Features**: Create new components following existing patterns

## File-Specific Instructions
See `.github/instructions/` for detailed guidance on:
- CSS utilities and styling practices
- Frontend design principles
- Blazor component development patterns
- Bingo game logic implementation

## Quality Checks
- Ensure builds pass without warnings
- Test game flow end-to-end
- Verify accessibility with screen readers
- Check responsive design on different screen sizes
- Validate local storage persistence</content>
<parameter name="filePath">/workspaces/Github-copilot-lab-Dan/.github/copilot-instructions.md