# 🚀 AI Dev Tasks for Cursor 🤖

Welcome to **AI Dev Tasks**! This repository provides a collection of `.mdc` (Markdown Command) files designed to supercharge your feature development workflow within the [Cursor](https://cursor.sh/) editor. By leveraging these commands with Cursor's AI Agent, you can systematically approach building features, from ideation to implementation, with built-in checkpoints for verification.

Stop wrestling with monolithic AI requests and start guiding your AI collaborator step-by-step!

## ✨ The Core Idea

Building complex features with AI can sometimes feel like a black box. This workflow aims to bring structure, clarity, and control to the process by:

1.  **Defining Scope:** Clearly outlining what needs to be built with a Product Requirement Document (PRD).
2.  **Detailed Planning:** Breaking down the PRD into a granular, actionable task list.
3.  **Iterative Implementation:** Guiding the AI to tackle one task at a time, allowing you to review and approve each change.

This structured approach helps ensure the AI stays on track, makes it easier to debug issues, and gives you confidence in the generated code.

## Workflow: From Idea to Implemented Feature 💡➡️💻

Here's the step-by-step process using the `.mdc` files in this repository:

### 1️⃣ Create a Product Requirement Document (PRD)

First, lay out the blueprint for your feature. A PRD clarifies what you're building, for whom, and why.

You can create a lightweight PRD directly within Cursor:

1.  Ensure you have the `create-prd.mdc` file from this repository accessible.
2.  In Cursor's Agent chat, initiate PRD creation:

    ```
    Use @create-prd.mdc
    Here's the feature I want to build: [Describe your feature in detail]
    Reference these files to help you: [Optional: @file1.py @file2.ts]
    ```
    *(Pro Tip: For complex PRDs, using MAX mode in Cursor is highly recommended if your budget allows for more comprehensive generation.)*

    ![Example of initiating PRD creation](https://pbs.twimg.com/media/Go6DDlyX0AAS7JE?format=jpg&name=large)

### 2️⃣ Generate Your Task List from the PRD

With your PRD drafted (e.g., `MyFeature-PRD.md`), the next step is to generate a detailed, step-by-step implementation plan for your AI Developer.

1.  Ensure you have `generate-tasks-from-prd.mdc` accessible.
2.  In Cursor's Agent chat, use the PRD to create tasks:

    ```
    Now take @MyFeature-PRD.md and create tasks using @generate-tasks-from-prd.mdc
    ```
    *(Note: Replace `@MyFeature-PRD.md` with the actual filename of the PRD you generated in step 1.)*

    ![Example of generating tasks from PRD](https://pbs.twimg.com/media/Go6FITbWkAA-RCT?format=jpg&name=medium)

### 3️⃣ Examine Your Task List

You'll now have a well-structured task list, often with tasks and sub-tasks, ready for the AI to start working on. This provides a clear roadmap for implementation.

![Example of a generated task list](https://pbs.twimg.com/media/Go6GNuOWsAEcSDm?format=jpg&name=medium)

### 4️⃣ Instruct the AI to Work Through Tasks (and Mark Completion)

To ensure methodical progress and allow for verification, we'll use `process-task-list.mdc`. This command instructs the AI to focus on one task at a time and wait for your go-ahead before moving to the next.

1.  Create or ensure you have the `process-task-list.mdc` file accessible.
2.  In Cursor's Agent chat, tell the AI to start with the first task (e.g., `1.1`):

    ```
    Please start on task 1.1 and use @process-task-list.mdc
    ```
    *(Important: You only need to reference `@process-task-list.mdc` for the *first* task. The instructions within it guide the AI for subsequent tasks.)*

    The AI will attempt the task and then prompt you to review.

    ![Example of starting on a task with process-task-list.mdc](https://pbs.twimg.com/media/Go6I41KWcAAAlHc?format=jpg&name=medium)

### 5️⃣ Review, Approve, and Progress ✅

As the AI completes each task, you review the changes.
*   If the changes are good, simply reply with "yes" (or a similar affirmative) to instruct the AI to mark the task complete and move to the next one.
*   If changes are needed, provide feedback to the AI to correct the current task before moving on.

You'll see a satisfying list of completed items grow, providing a clear visual of your feature coming to life!

![Example of a progressing task list with completed items](https://pbs.twimg.com/media/Go6KrXZWkAA_UuX?format=jpg&name=medium)

While it's not always perfect, this method has proven to be a very reliable way to build out larger features with AI assistance.

## 🗂️ Files in this Repository

### Core Workflow Files
*   **`create-prd.mdc`**: Guides the AI in generating a Product Requirement Document for your feature.
*   **`generate-tasks.mdc`**: Takes a PRD markdown file as input and helps the AI break it down into a detailed, step-by-step implementation task list optimized for Vue.js and Nx monorepos.
*   **`process-task-list.mdc`**: Instructs the AI on how to process the generated task list, tackling one task at a time and waiting for your approval before proceeding. (This file also contains logic for the AI to mark tasks as complete).

### Specialized Task Generation Templates
Choose the appropriate template based on your deployment target:

#### Platform-Specific Templates
*   **`generate-tasks-desktop.mdc`**: Specialized for desktop applications using Tauri or Electron with native OS integration, file system access, and cross-platform compatibility.
*   **`generate-tasks-web.mdc`**: Optimized for web applications with PWA capabilities, SSR/SSG, SEO optimization, and modern web standards.
*   **`generate-tasks-mobile.mdc`**: Focused on mobile applications using Capacitor or Ionic with native device APIs, touch interactions, and app store deployment.

#### Infrastructure & Backend Templates
*   **`generate-tasks-cloud.mdc`**: Designed for cloud infrastructure and backend services with scalable APIs, database design, authentication systems, and cloud platform integration.
*   **`generate-tasks-infrastructure.mdc`**: Specialized for DevOps and infrastructure automation with CI/CD pipelines, containerization, monitoring, and Infrastructure as Code.
*   **`generate-tasks-mcp.mdc`**: Focused on Model Context Protocol (MCP) server development with tool implementation, resource management, client integration, and protocol compliance.

### How to Choose the Right Template

1. **`generate-tasks.mdc`** - Use for general Vue.js applications or when unsure
2. **`generate-tasks-desktop.mdc`** - Use when building desktop apps with native OS features
3. **`generate-tasks-web.mdc`** - Use for web applications with SEO, PWA, or performance focus
4. **`generate-tasks-mobile.mdc`** - Use for mobile applications with native device integration
5. **`generate-tasks-cloud.mdc`** - Use when building backend APIs and cloud services
6. **`generate-tasks-infrastructure.mdc`** - Use for DevOps, CI/CD, and infrastructure automation
7. **`generate-tasks-mcp.mdc`** - Use when building Model Context Protocol servers and tool integrations

### Usage with Specialized Templates

To use a specialized template, replace the standard command with:

```
Now take @MyFeature-PRD.md and create tasks using @generate-tasks-[platform].mdc
```

Examples:
- `@generate-tasks-desktop.mdc` for desktop applications
- `@generate-tasks-web.mdc` for web applications  
- `@generate-tasks-mobile.mdc` for mobile applications
- `@generate-tasks-cloud.mdc` for backend and cloud services
- `@generate-tasks-infrastructure.mdc` for DevOps and infrastructure
- `@generate-tasks-mcp.mdc` for Model Context Protocol servers

### Multi-Template Application Scenarios

For complex applications that span multiple platforms or require different specialized components, you can use multiple templates in sequence or combination:

#### **Sequential Template Application**
For applications with distinct platform targets:

1. **Multi-Platform Applications:**
   ```
   // Start with the primary platform
   Now take @MyFeature-PRD.md and create tasks using @generate-tasks-web.mdc
   
   // After completing web tasks, generate mobile tasks
   Now create additional tasks for mobile deployment using @generate-tasks-mobile.mdc and integrate with existing task list
   
   // Finally, add desktop distribution tasks
   Now create desktop deployment tasks using @generate-tasks-desktop.mdc and merge with current roadmap
   ```

2. **Full-Stack Applications with Infrastructure:**
   ```
   // Start with frontend
   Now take @MyFeature-PRD.md and create tasks using @generate-tasks-web.mdc
   
   // Add backend/API tasks
   Now create backend tasks using @generate-tasks-cloud.mdc and coordinate with frontend tasks
   
   // Add deployment infrastructure
   Now create infrastructure tasks using @generate-tasks-infrastructure.mdc for the complete system
   ```

#### **Integrated Multi-Template Approach**
For applications requiring simultaneous development across platforms:

```
Create a comprehensive task list for @MyFeature-PRD.md using:
- @generate-tasks-web.mdc for the main web application
- @generate-tasks-mobile.mdc for mobile companion app
- @generate-tasks-cloud.mdc for backend services
- @generate-tasks-infrastructure.mdc for deployment pipeline

Please integrate these into a coordinated development timeline with shared libraries and synchronized milestones.
```

#### **Template Combination Strategies**

**Shared Component Library Approach:**
- Use `generate-tasks.mdc` for core shared components
- Apply specialized templates for platform-specific implementations
- Focus on maintaining consistent APIs and design systems

**Timeline Coordination:**
- **Sequential Development:** Add 30-50% to timelines for platform integration
- **Parallel Development:** Add 20-30% but requires larger team coordination
- **Shared Library First:** Add 40-60% upfront but reduces per-platform time by 25-35%

**Recommended Multi-Template Combinations:**

1. **Enterprise Web + Mobile:**
   - `generate-tasks-web.mdc` + `generate-tasks-mobile.mdc` + `generate-tasks-cloud.mdc`
   - Timeline: +60-80% vs single platform

2. **Desktop + Web Distribution:**
   - `generate-tasks-desktop.mdc` + `generate-tasks-web.mdc` + `generate-tasks-infrastructure.mdc`
   - Timeline: +45-65% vs single platform

3. **Full-Stack MCP Integration:**
   - `generate-tasks-mcp.mdc` + `generate-tasks-web.mdc` + `generate-tasks-infrastructure.mdc`
   - Timeline: +50-70% vs single platform

4. **Complete DevOps Pipeline:**
   - Primary template + `generate-tasks-infrastructure.mdc` + `generate-tasks-cloud.mdc`
   - Timeline: +70-120% for comprehensive automation

## 🎯 Enhanced Features & Improvements

### Timeline Estimation Framework
All task generation templates now include sophisticated timeline estimation based on:
- **Complexity Factors:** UI complexity, data requirements, integration needs
- **Developer Experience:** Automatic adjustments for junior, mid-level, and senior developers
- **Platform-Specific Considerations:** Additional time for mobile testing, desktop distribution, cloud security, etc.

### Quality Gates & Checkpoints
Built-in validation milestones after every 3-4 major tasks:
- Architecture reviews and dependency validation
- Performance baselines and optimization checkpoints
- Accessibility audits and WCAG compliance verification
- Testing coverage maintenance across all libraries
- User testing and stakeholder validation points

### Technology Stack Validation
Pre-task generation checklists ensure optimal technology choices:
- Build tool selection (Vite, Webpack, etc.)
- State management strategy (Pinia, Vuex, composables)
- Testing framework configuration (Vitest, Vue Test Utils)
- UI framework decisions (Headless UI, Vuetify, custom)
- Deployment target optimization (static, SSR, desktop, mobile)

### Troubleshooting & Error Recovery
Structured guidance for common development obstacles:
- Task breakdown strategies when complexity increases
- Dependency management and parallel development approaches
- Prototyping patterns for uncertain requirements
- Escalation procedures for architectural decisions

### Success Metrics Integration
Measurable outcomes defined for each major task category:
- **Performance:** Load time, bundle size, runtime efficiency
- **Accessibility:** WCAG compliance scores, keyboard navigation coverage
- **User Experience:** Task completion metrics, error rates, satisfaction scores
- **Code Quality:** Test coverage, TypeScript compliance, linting results
- **Maintainability:** Complexity metrics, dependency health

## 🌟 Benefits

*   **Structured Development:** Enforces a clear process from idea to code with platform-specific optimizations.
*   **Step-by-Step Verification:** Allows you to review and approve AI-generated code at each small step, ensuring quality and control.
*   **Platform-Specific Optimization:** Specialized templates for desktop, web, mobile, cloud, and infrastructure ensure optimal patterns for each target.
*   **Enhanced Timeline Accuracy:** Sophisticated estimation framework accounts for complexity, developer experience, and platform-specific requirements.
*   **Built-in Quality Gates:** Automatic validation checkpoints for architecture, performance, accessibility, and testing coverage.
*   **Manages Complexity:** Breaks down large features into smaller, digestible tasks with troubleshooting guidance for complex scenarios.
*   **Improved Reliability:** Offers a more dependable approach to leveraging AI for significant development work with error recovery patterns.
*   **Technology Stack Guidance:** Pre-validated technology choices ensure optimal tool selection for each platform and use case.
*   **Success Metrics Integration:** Measurable outcomes defined for performance, accessibility, code quality, and maintainability.
*   **Clear Progress Tracking:** Provides a visual representation of completed tasks with milestone validation and quality checkpoints.

## 🛠️ How to Use

1.  **Clone or Download:** Get these `.mdc` files into your project or a central location where Cursor can access them.
2.  **Follow the Workflow:** Systematically use the `.mdc` files in Cursor's Agent chat as described in the 5-step workflow above.
3.  **Adapt and Iterate:**
    *   Feel free to modify the prompts within the `.mdc` files to better suit your specific needs or coding style.
    *   If the AI struggles with a task, try rephrasing your initial feature description or breaking down tasks even further.

## 💡 Tips for Success

*   **Choose the Right Template:** Select the specialized template that matches your deployment target for optimal task generation and platform-specific patterns.
*   **Be Specific with Context:** The more context and clear instructions you provide (both in your initial feature description and any clarifications), the better the AI's output will be.
*   **Leverage Quality Gates:** Use the built-in validation checkpoints to ensure architecture, performance, and accessibility standards are maintained throughout development.
*   **MAX Mode for PRDs:** Using MAX mode in Cursor for PRD creation (`create-prd.mdc`) can yield more thorough and higher-quality results if your budget supports it.
*   **Accurate File Tagging:** Always ensure you're accurately tagging the PRD filename (e.g., `@MyFeature-PRD.md`) and the correct specialized template when generating tasks.
*   **Use Timeline Estimates:** Reference the timeline estimation framework to set realistic expectations and plan resources effectively.
*   **Monitor Success Metrics:** Track the defined performance, accessibility, and code quality metrics throughout development to ensure project success.
*   **Follow Troubleshooting Patterns:** When tasks become complex, use the provided breakdown strategies and error recovery guidance.
*   **Technology Stack Validation:** Complete the technology checklist before task generation to ensure optimal tool selection for your specific requirements.
*   **Patience and Iteration:** AI is a powerful tool, but it's not magic. Be prepared to guide, correct, and iterate. This enhanced workflow is designed to make that iteration process more structured and efficient.

## 🤝 Contributing

Got ideas to improve these `.mdc` files or have new ones that fit this workflow? Contributions are welcome!
Please feel free to:
*   Open an issue to discuss changes or suggest new features.
*   Submit a pull request with your enhancements.

---

Happy AI-assisted developing!
