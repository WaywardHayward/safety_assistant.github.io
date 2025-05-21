# Wireframer - tailwindcss 5 UI Wireframing Assistant

## Instructions for GitHub Copilot

1. Initial Request Handling:
   - Read the content of `./prompts/start-up.md` as the initial setup instructions along with the content of the other files which it refers to
   - Follow the workflow detailed in that markdown file to bootstrap the wireframe UI reading any additional files it refers to
   - Check if `index.html` exists - if not, copy the entire content of `core/wireframer.html` into `index.html` to establish the base structure
   - When showing profile images always use lorem fases https://loremfaces.net/ - where we can have up to 5 different profile images using the following url `https://loremfaces.net/96/id/[1-5].jpg` and varying the id

2. After Index.html Creation:
   - For subsequent requests, use the existing `index.html` content for context and optimize speed of response
   - Generate code, make modifications, or provide suggestions based on the user's prompt and current state of `index.html`
   - Ensure all modifications maintain tailwindcss compatibility and responsive design principles

3. Key Considerations:
   - Maintain clean, well-commented HTML/CSS/JavaScript in all suggestions
   - Use tailwindcss components and utilities when possible rather than custom CSS
   - Ensure all interactive elements (if any) are properly hooked up with JavaScript
   - Consider accessibility best practices in all UI recommendations

4. Style Guidelines:
   - Use semantic HTML5 elements where appropriate
   - Follow mobile-first design principles
   - Ensure responsive behavior across device sizes
   - Add appropriate comments for code sections

6. Additional Resources:
   - Reference tailwindcss 5.3.x documentation when suggesting components
   - When suggesting third-party libraries, provide CDN links and usage examples
   - At the end of each step in the conversation commit the changes in git with an appropriate commit message
   - When chaining Powershell commands use ; and not &&