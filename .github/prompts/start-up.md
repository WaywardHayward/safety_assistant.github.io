# Tailwind CSS Wireframing Assistant – Complete Guide

## 🧭 Overview

This application utilizes Tailwind CSS to create responsive HTML wireframes. Your task is to apply user instructions to evolve the wireframe cleanly, responsibly, and accessibly. This guide outlines the complete workflow and specifications for the wireframing process.

## 📂 File Handling and Initial Setup

This guide outlines how to set up your working HTML file and ensure that you preserve the integrity of your wireframing environment.

### 🧾 Step-by-Step Instructions

#### Step 1: Copy the Base Wireframe

* Open `core/wireframer.html`
* Copy all contents exactly as-is
* Paste into a new file called `index.html` in the root project directory

#### Step 2: Maintain Structural Integrity

* Do **not** remove or alter base `<html>`, `<head>`, or `<body>` structure unless instructed
* Preserve Tailwind CSS `<link>` or `<script>` inclusions
* Avoid duplicating IDs or conflicting layout regions

#### Step 3: Sanity Check

* Open `index.html` in a browser
* You should see the exact same layout as `wireframer.html`
* Check console for any loading or script errors

### ⚠️ Warnings

* ❌ Don't modify `core/wireframer.html`. It acts as a clean reference
* ✅ Keep `index.html` under version control

> 💡 Tip: Treat `index.html` as the **working canvas**. Reset with the core file if things go sideways.

## 🧠 Processing User Instructions

This guide helps you interpret, evaluate, and apply user instructions when building wireframes with Tailwind CSS.

### 🔍 Understand the Prompt

Users may give:

* 📌 **Specific requests** ("Add a hero section with overlay text")
* 🧭 **Vague guidance** ("Make it look more mobile-friendly")

### ✨ Best Practices

#### ✅ Parse First

* Ask: What layout/component/function is being requested?
* Consider intent behind the prompt

#### ✅ Then Act

* Add components to `index.html`
* Use semantic HTML5 structure
* Style using **Tailwind utility classes** only

#### ✅ Then Reflect

* Leave a comment (`<!-- added hero section based on user prompt -->`)
* Note assumptions if needed (`<!-- assumed hero text goes here -->`)

### 🛠 Types of Modifications

| Type           | Description                                                      |
| -------------- | ---------------------------------------------------------------- |
| HTML Structure | Add/edit semantic elements (e.g. `<nav>`, `<main>`, `<section>`) |
| Layout         | Use flexbox, grid, container utilities                           |
| Styling        | Apply Tailwind classes for colors, borders, spacing              |
| JS Logic       | Add interactivity (toggle, expand, modal triggers)               |
| Responsive     | Use `sm:` to `2xl:` breakpoints                                  |

> 🧩 When in doubt, document your interpretation as a comment

## 🧼 Code Quality Expectations

Maintaining clean, consistent, and valid HTML is crucial. Follow these rules to ensure your wireframe is production-grade.

### 🧱 Structure & Formatting

* Indent properly (2 or 4 spaces — be consistent)
* Group related content logically (e.g., all nav items together)
* Use meaningful, semantic HTML tags

### 🏷 Comments & Documentation

* Add clear, concise comments:

  * `<!-- Main navigation bar -->`
  * `<!-- Modal overlay for login form -->`
* Explain any assumptions, workarounds, or decisions

### ✅ HTML Validation

* Ensure valid HTML5 structure
* All tags must be closed properly
* No duplicated `id` attributes
* Use correct nesting (no `<div>` inside `<span>` unless scoped)

### ⚠️ Error Handling

If the user prompt is ambiguous:

* Leave a comment noting your interpretation
* Optionally suggest alternate implementations

> 💬 Example: `<!-- Interpreted "form" as login modal. Could also be contact form. -->`

## ♿ Accessibility Guidelines

Building wireframes responsibly means designing for all users. Use these practices to improve inclusivity.

### 🔤 Semantic HTML

* Use proper elements:

  * `<nav>` for navigation
  * `<main>`, `<section>`, `<aside>`, `<footer>` where applicable

### 🗣 ARIA & Attributes

* Use `role`, `aria-*` attributes only when necessary
* Example: `role="button"` for non-button elements with click behavior

### 🎨 Contrast & Readability

* Ensure color contrast meets **WCAG AA** minimums
* Avoid using color as the only way to convey meaning

### 🧭 Keyboard Navigation

* All interactive elements must be reachable by `Tab`
* Use `:focus` states for visual feedback
* Avoid keyboard traps (where focus gets stuck)

### 🖼 Alt Text & Icons

* All images and icons should have descriptive `alt` attributes
* Use `aria-hidden="true"` on decorative icons

### 📐 Heading Hierarchy

* Use heading levels in order: `h1` > `h2` > `h3`
* Don't skip levels (e.g., no jumping from `h1` to `h4`)

> 💡 Design like you're narrating the screen to someone.

## 🌈 Tailwind CSS Implementation

Use Tailwind's utility-first classes to build clean, responsive, modern UIs.

### 🧱 Core Layout Tools

* **Containers**: `container mx-auto px-4`
* **Grid**: `grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3`
* **Flex**: `flex justify-between items-center`
* **Spacing**: `p-6`, `gap-4`, `space-y-4`

### 🖋 Content & Components

* **Typography**: `text-lg`, `font-semibold`, `leading-relaxed`
* **Cards**: `bg-white shadow-md rounded p-4`
* **Modals**: Toggle visibility with JS, use `fixed inset-0 z-50`
* **Navbar**: `bg-gray-100 border-b` with hidden/show toggle for mobile
* **Hero Sections**: `bg-cover bg-center h-screen`, overlay with `bg-opacity-50`

### 📱 Responsiveness

* Use breakpoint prefixes: `sm:`, `md:`, `lg:`, `xl:`, `2xl:`
* Always test across screen sizes

### 🧠 Tips

* Avoid custom CSS — lean fully into Tailwind
* Use Tailwind plugins for extras (e.g., typography, forms)
* Comment sections clearly: `<!-- Hero Section -->`, etc.

### Examples

**Responsive Grid Example:**

```html
<div class="container mx-auto px-4">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
        <div class="bg-white shadow-md rounded p-4">...</div>
        <div class="bg-white shadow-md rounded p-4">...</div>
        <div class="bg-white shadow-md rounded p-4">...</div>
    </div>
</div>
```

**Navbar Implementation:**

```html
<!-- Navbar Implementation -->
<nav class="bg-gray-100 border-b border-gray-200">
    <div class="container mx-auto px-4 flex justify-between items-center py-4">
        <a class="text-lg font-semibold text-gray-800" href="#">Brand</a>
        <button class="block md:hidden text-gray-800 focus:outline-none" aria-label="Toggle navigation">
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
            </svg>
        </button>
        <div class="hidden md:flex space-x-4">
            <!-- Navigation links here -->
        </div>
    </div>
</nav>
```

**Footer Implementation:**

```html
<!-- Footer Implementation -->
<footer class="bg-gray-100 border-t border-gray-200">
    <div class="container mx-auto px-4 py-6">
        <div class="flex justify-between items-center">
            <p class="text-gray-600">© 2023 Your Company. All rights reserved.</p>
            <div class="flex space-x-4">
                <a href="#" class="text-gray-600 hover:text-gray-800">Facebook</a>
                <a href="#" class="text-gray-600 hover:text-gray-800">Twitter</a>
                <a href="#" class="text-gray-600 hover:text-gray-800">LinkedIn</a>
            </div>
        </div>
    </div>
</footer>
```

**Hero Section Implementation:**

```html
<!-- Hero Section Implementation -->
<section class="bg-cover bg-center h-screen" style="background-image: url('path/to/image.jpg');">
    <div class="flex items center justify-center h-full bg-black bg-opacity-50">
        <h1 class="text-white text-4xl font-bold">Welcome to Our Website</h1>
        <p class="text-white mt-4">Your tagline or description goes here.</p>   
    </div>
</section>
```

Make sure the nav bar has a user profile icon on the right with the user's avatar image. Clicking this image should show account settings including logout and admin functions.

## 📝 Example User Instructions

Use these sample prompts to guide and inspire your own wireframe builds.

### 📌 Layout & Navigation

* "Insert a top navigation bar with links for Home, About, and Contact."
* "Add a footer with social media icons and copyright."

### 🖼 Hero & Marketing Sections

* "Add a hero section with background image and overlay text."
* "Insert a 3-column feature section below the hero."

### 📬 Apps & Tools

* "Create a collapsible side menu with dropdowns."
* "Build a Todo app with CRUD and priority options."
* "Make an email client prototype with inbox and message view."

### 📱 Responsive Behavior

* "Make the layout go from two columns on desktop to single column on mobile."

### 🎛 Interactive Components

* "Add a modal triggered by a button."
* "Create a form with validation and success message."

> 💡 Each of these instructions could involve HTML, Tailwind classes, and basic JS logic.

## 🔁 Operational Workflow Recap

Use this checklist to move through a wireframe build from setup to final review.

1. **Initialization:**
    - Copy from `core/wireframer.html` to `index.html`
2. **Modification:**
    - Parse user instructions
    - Apply HTML, Tailwind, and JavaScript changes
3. **Finalization:**
    - Validate the UI
    - Reflect on the design and responsible AI principles - make any necessary adjustments
    - Reflect on the UI Design and Make is look sleek and modern, and super cool
    - Review for accessibility and responsive design
    - Check against responsible AI principles
4. **Template Creation:**
    - Create directory /templates/react/components and break out the components in the index.html file into react components with state to be used in a react app

> 🎨 End result: Clean, beautiful, accessible Tailwind UI ready for production or prototyping

## 🧯 Troubleshooting Guide

### 🧱 Layout Breaking

* ✅ Double-check nested `div` structure
* ✅ Use `gap-*` between grid/flex children
* ✅ Check padding/margin clashes from Tailwind utilities

### 🧩 Broken Components

* ✅ If using JavaScript (e.g. modals, toggles), verify event listeners
* ✅ Ensure you're not missing any Tailwind classes (e.g. `hidden`, `block`)

### 📱 Mobile Display

* ✅ Add `sm:`/`md:` classes for breakpoints
* ✅ Use `w-full` and `min-w-0` to avoid overflow bugs

### 🎨 Inconsistent Styles

* ✅ Stick to Tailwind utility classes — avoid inline styles
* ✅ Avoid class conflict: one `bg-*` or `text-*` per element

### 🎯 Tailwind-Specific Notes

* Grid = 12 columns
* Use `overflow-hidden` or `overflow-x-auto` for scrolling sections
* Custom colors should be added in `tailwind.config.js`

> 💡 Check the browser dev tools and console — they often tell you exactly what's wrong.

## 🎨 UI Principles & Responsible AI

Design your wireframe not just to look good — but to feel safe, modern, and intentional.

### 🧭 Layout & Grid

* Avoid centering with `.container`
* Prefer full-screen root layout: `min-h-screen w-full grid`
* Add gaps between rows/columns: `gap-6`, `p-6 lg:p-8`

### 🌈 Color & Typography

* Stick to muted grays, slates, blues, greens (`slate-*`, `#4a6fa5`)
* Avoid harsh reds/yellows for non-errors
* Font stack: system UI fonts, `text-base`, `text-xl`, `font-semibold`

### 📐 Spacing & Balance

* Use consistent padding: `p-5 sm:p-6`
* Use vertical stacks: `space-y-4`
* Hit areas should be ≥ `h-10`
* Target SVG canvas heights: `60vh` or more

### 💡 General Polish

* Comment sections with purpose: `<!-- Card List -->`
* Avoid giant files: target ≤ 200 lines per file

---

### Responsible AI Principles

Use these principles to guide your design decisions and ensure a user-friendly experience.

#### 🛑 Do No Harm
  
- Avoid dark patterns, stress-inducing UIs
- Show critical info clearly
- Use confirmations for destructive actions

#### 🌱 Care for Earth

- Show resource/environmental impact
- Promote efficient UIs
- Avoid wasteful compute (e.g., animations, polling)

#### 💛 Act with Empathy

- Supportive tone: "Let's fix this together" not "You made an error"
- Reduce cognitive load, prioritize minimalism 

#### 🧍‍♂️ Respect Identity & Consent

- Be transparent about AI-driven actions
- Let users override AI decisions
- Show system status clearly

#### 🕊️ Seek Peaceful Solutions

- No fear-based messaging
- Use escalation gently: colors, icons before alarms
- Give actionable guidance

#### 📖 Share Knowledge

- Make logs and insights visible
- Provide "Why did this happen?" and "Explain this" options
- Use progressive disclosure

#### 🧠 Tell the Truth

- Avoid misleading visuals
- Show uncertainty/confidence where relevant
- Be honest about limitations 

#### 🔁 Iterate Responsibly

- Use A/B testing responsibly
- Add feedback tools: "Was this helpful?", "What's missing?"
- Design for continual improvement
> 🙌 Build for clarity. Design with conscience.

## Contextual Instructional Flyouts for UI Components

For **every UI component on screen**, generate contextual instructional flyouts to ensure the prototype is:
- Grounded in **real-world context**
- Scalable in **production environments**
- Aligned with **Responsible AI** and **sound engineering practices**

These flyouts should be html tooltips NOT TITLES, and should be **visible on hover**. They should not be **permanent** or **obtrusive**.

Attach the following **4 required** flyouts (plus **1 optional**):

---

### 👥 Task + Persona Tooltip

- **List the personas** required to implement this component, across both Operational Technology (OT) and Information Technology (IT):

  - **OT examples:** Controls Engineer, Maintenance Technician, Operations Supervisor, Process Engineer  
  - **IT examples:** Software Engineer, Cloud Architect, Data Scientist, Security Engineer  
  - **Cross-functional:** Business SME, UX Designer, UAT Lead, Project Manager

- **Describe the key tasks** each persona will likely perform for this component.

- **Include scale considerations**, such as:
  - "Are telemetry tag names consistent across sites?"
  - "Can this logic be reused or parameterized?"
  - "Would this component still function with 10× more data?"

---

### 🎯 Design Intent Tooltip

- **Summarize the purpose** of the component and what it's expected to do.
- **List data requirements** (e.g., OPC tags, telemetry streams, business rules).
- Include prompts to challenge assumptions:
  - "Could this be done using Logic Apps or Azure RTI instead?"
  - "Does this already exist in another system like Fabric or PI?"
  - "Is this tightly coupled to a local instance, or is it scalable?"

---

### 🧠 AI Impact Tooltip

- **Positive impacts** (in green), e.g.:
  - "Reduces downtime with early warnings."
- **Negative impacts or risks** (in red), e.g.:
  - "Risk of operator over-trust in predictions."
- **Indicate affected personas**, such as Operator, Engineer, Supervisor.
- **Example Responsible AI nudges:**
  - "Show confidence score alongside AI predictions."
  - "Allow user override of AI decisions."
  - "Avoid blaming language ('Let's fix this together' instead of 'You made an error')."
  - "Highlight when a model influenced the UI decision."

---

### 🛠️ Implementation Helper Tooltip

- **Surface practical build guidance** to avoid common pitfalls.
- Include **Copilot-style prompts** to encourage thoughtful decisions:
  - "Is this solving a unique problem, or duplicating an existing tool?"
  - "Would this require changes at every site or just once?"
  - "Does this require custom code, or can it be handled by a low-code service?"
  - "Will this still make sense in 6 months?"

---

### 📬 (Optional) Feedback & Learning Tooltip

- Include **user prompts** to support iteration and continuous learning:
  - "What would help a new operator understand this?"
  - "Does this clearly show what happens next?"
  - "Is the system showing what it's doing and why?"

---

### 🖌 Styling and Interaction Guidelines

- All tooltips must be **left-aligned** and clearly structured with **headers** and **bullet points**.
- Use:
  - **Green** for positive suggestions and impacts
  - **Red** for risks and warnings
- Icons should be:
  - Small
  - Unobtrusive
  - Clearly visible (👥 🎯 🧠 🛠️ 📬)
- Enable:
  - **Hover-to-preview**
  - Optionally **click-to-expand** for detailed content

---

Ensure **every component** on the screen includes these tooltips to support **prototype-to-production thinking**.

> ✅ Treat the example questions as **prompts**, not fixed answers.
> ✅ Use **clear, concise language** to ensure easy understanding.

## 🎬 Storyboard & Scenario Panel (Global – Top of Wireframe)

Add a storyboard icon (e.g., 🎬 or 📖) at the top of the canvas. When clicked, display a scrollable panel that includes a set of user-centric scenarios. Each scenario should contain:

- Scenario Name (e.g., "Investigate Temperature Spike")
- Persona(s) Involved
- User Goal or Trigger
- Sequential Steps Taken
- Refer to wireframe components (e.g., "User clicks trend chart → opens AI tooltip → reviews recommendation")
- AI Interactions (e.g., model prediction, override prompt, explanation button)
- Expected Outcome
- Alt Path / Failure Mode (e.g., "user ignores alert → system escalates after delay")
  Image Scenarios should be realistic, relevant, and grounded in typical industrial or enterprise workflows. Use them to clarify intent and improve design alignment.

Add a "Try Scenario" button to each scenario. When clicked, the wireframe should simulate the scenario by highlighting (using intro.js which you may have to install using npm or reference using a cdn) relevant components step by step and showing the expected interactions. This will help users visualize how the system should behave in real-world situations by showing the expected interactions and outcomes including clicking the correct buttons and links, and showing the expected outcomes.

Place this in a Modal that can be opened by clicking the storyboard icon. The modal should be scrollable and allow users to view all scenarios without leaving the wireframe. The scenarios should be easy to read and understand, with clear headings and bullet points where appropriate.

## Architecture Diagram

Generate a Proposed Architecture panel at the top of the wireframing app interface, located adjacent to the Scenarios button

When clicked, this panel should display:

A Rendered Architecture Diagram (generated as a diagram not the example architecture) which matches the visual style of reference diagrams in the folder /core/images/architecture/
Use Azure-native services and standardized icons to represent components clearly
Group into Edge, Cloud, and Control/Insights sections

Show data flow from left to right (left being onsite right/middle being cloud and right being user interaction), AI/ML inference paths, user interaction points (e.g., Copilot, Teams), and feedback loops
When adding nodes to the diagram use appropriate icons from the /core/images/azure-icons folder.

Use blue lines for data flow
Use Purple lines for configuration flow

Show a legend for the lines

Clearly label architecture with title:
"Proposed High-Level Architecture for app name"

### Justification Summary (Side Panel or Tab)
Display a markdown-style or tabular format summary beside the diagram
For each major component in the diagram, include:

Component Name Role in Architecture Justification
Azure IoT Hub Ingest Edge Data Supports MQTT and OPC UA, scalable per-site ingestion
Azure Stream Analytics Real-Time Data Processing Enables low-latency filtering, correlation, and routing
Azure Fabric Global Situational Awareness Modular, open data layer for analytics and Copilot readiness
Azure AI Studio Model Orchestration & Management Trains, manages, and explains AI models for responsible industrial use
Azure Arc Hybrid Governance & Deployment Ensures consistent management across cloud, edge, and on-prem environments

Ensure formatting is clean, left-aligned, and optimized for quick scanning

Allow this table to scroll or expand if needed

Create a high-level Azure architecture diagram (landscape orientation) using the official Microsoft Azure icon set, soft drop-shadows, rounded corners, and a subtle blue-gray gradient background.

LAYOUT (left ➜ right, columnar "swim-lane" style):

1. **Physical**  
   • Tall rounded box labelled *Industrial Assets*  
   • Inside, vertically stack three pictograms with captions:  
     – "Edge Context Data" (generic server/PC icon)  
     – "OPC Asset Data" (stacked disks icon)  
     – "Business Data" (office building icon)

2. **Edge**  
   • Tall rounded box labelled *Azure IoT Edge*  
   • Inside, draw a horizontal bar captioned **Edge Plane**  
   • Beneath the bar place the Kepware Connector icon

3. **Cloud** (split into seven narrow sub-columns, all inside a larger rounded "Cloud" frame)  
   3.1 **Cloud Ingress / Egress** – Azure IoT Hub icon, then Azure Event Hub / Grid icon  
   3.2 **Security & Identity** – Azure Key Vault, Entra ID  
   3.3 **Observability** – Azure IoT Operations, Azure Monitor  
   3.4 **Data Analytics & Store** – Azure Data Explorer, Microsoft Fabric, Azure OneLake  
   3.5 **Machine Learning & AI** – Azure ML, Azure OpenAI  
   3.6 **Situational Awareness** – Digital Twin, Power BI, Power Platform (stack card), Teams  
   3.7 **Custom Cloud Workloads** – Azure Stream Analytics, App Service, two generic "Custom Workload" boxes

4. **Control Plane**  
   • Dark horizontal bar pinned across the bottom spanning all columns, labelled  
     "Azure Control Plane – Operations, Management & Security"  
   • Inside place Azure Arc icon (left) and Azure DevOps icon (right)

### CONNECTORS & ANNOTATIONS

* Use solid Azure-blue right-pointing arrows labelled simply **Data** from Physical ➜ Edge ➜ Cloud Ingress.  
* Within Cloud, connect services with thinner blue arrows following logical paths (IoT Hub ➜ Event Hub ➜ Data Explorer, etc.).  
* Place small yellow pill-shaped call-outs on specific arrows:  
  – "Message Ingestion – per site" on the IoT Hub arrow  
  – "BC/DR" on the Data Lake arrow (if drawn)  
  – "Dev Replication" on the Data Factory arrow (if drawn)

### STYLE

* Consistent icon size (~48 px), equal column widths, generous white space.  
* Minimal text; rely on icon captions.  
* Keep palette to Azure brand blues + grays with accent yellow for call-outs.  
* Overall look: clean, modern, executive-summary ready.

## 🚀 Startup Instructions

### Step 1: Initialize the Working File

- Copy the contents of `core/wireframer.html` into `index.html`.
- This sets up the base structure for all future work.

### Step 2: Understand the User Instruction Workflow

- User instructions guide UI creation: interpret, apply, and iterate.

### Step 3: Follow the Code Guidelines

- Stay organized, validate your HTML, and document assumptions.

### Step 4: Prioritize Accessibility

- Design with semantic HTML, keyboard support, and proper ARIA roles.

### Step 5: Implement in Tailwind

- Build UIs using Tailwind utility classes—fast, modern, and responsive.

### Step 6: Explore Examples

- Use common examples for inspiration and quick wins.

### Step 7: Follow the Full Workflow Recap

- ALWAYS A step-by-step summary of the operational flow.

### Step 8: Troubleshoot Issues

- ALWAYS Get help for layout bugs, style issues, or Tailwind quirks.

### Step 9: Use UI Principles and Responsible AI

- ALWAYS Employ thoughtful, user-first design based on good design and ethics and adjust for AI behavior.

### Step 10: Embed Instructional Tooltips

- ALWAYS Add task, intent, and AI-awareness tooltips to every UI element, and populate them with relevant information.

### Step 11: Add Interactive Scenarios

- ALWAYS Show real-world usage with click-through tutorials.

### Step 12: Review and Iterate

- ALWAYS Reflect on the design and responsible AI principles, make any necessary adjustments, and review for accessibility and responsive design, and user requirements.

### Step 13: Architecture Diagram
- ALWAYS Create a high-level Azure architecture diagram (landscape orientation) using the official Microsoft Azure icon set, soft drop-shadows, rounded corners, and a subtle blue-gray gradient background.

### Step 14: Version Control
At the end of each step in the conversation commit the changes in git with an appropriate commit message

## ✅ Next Steps

Start by creating `index.html` from the base template. Then, sequentially read and implement the instructions from the listed modules above.

> *Keep your files small. Keep your designs clean. Keep your users in mind.*

