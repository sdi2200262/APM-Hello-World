# APM Landing Page - Implementation PRD

**Document Version:** 1.2  
**Created:** August 2025  
**Updated:** August 2025  
**Purpose:** Technical specification for building a modern landing page and documentation platform demonstrating systematic development coordination capabilities

## Project Overview

### What We're Building

This project is a **dual-purpose web application** that serves both functional and demonstrative goals:

**1. Professional Landing Page & Documentation Platform:**
- Modern landing page showcasing Vite + React + TypeScript + Shadcn UI integration with void-like aesthetic
- Interactive UI featuring floating card design pattern with pitch-black background and glassmorphism effects
- Dynamic contributor data fetched from GitHub API via automated workflows
- **Future APM v0.4 documentation hosting** with expandable content architecture **NOT FOR THIS PROJECT**

**2. Development Methodology Demonstration:**
- **Real-world systematic workflow validation** from initial setup through final deployment
- **Visible project coordination artifacts** accessible via GitHub repository for transparency
- **Complete development lifecycle** managed entirely through systematic coordination methodology
- **Practical showcase** of specialized development coordination capabilities in actual development scenarios

### Core Value Proposition

This application demonstrates systematic development coordination's ability to **manage complex development projects effectively**, breaking down sophisticated web development into manageable, specialized components while maintaining professional quality standards and modern development practices.

### Design Philosophy & Visual Approach

The landing page implements a **void-like aesthetic** where content sections float as rounded cards against a pitch-black background. This design emphasizes **minimal visual hierarchy** with strategic use of contrast, creating an immersive experience that guides users through distinct content zones with **Apple Watch-style interactions** and **glassmorphism effects**.

## Technical Architecture

### Technology Stack (2025)

#### **Frontend Core**
- **Vite 6.3.x**: Next-generation frontend tooling with native ESM and fast HMR
  - Lightning-fast development server with Hot Module Replacement
  - Optimized production builds with Rollup
  - Native TypeScript support with zero configuration
  - Modern browser targeting (ESNext) with legacy fallback support

- **React 19.x**: Latest React with concurrent features and improved performance
  - React Fast Refresh integration via Vite
  - Automatic JSX transformation
  - Enhanced developer experience with improved error messages

- **TypeScript 5.x**: Strong typing with latest language features
  - Strict type checking enabled
  - Path mapping for clean imports (`@/components`, `@/lib`, etc.)
  - Modern ES modules with full IntelliSense support

#### **UI Framework & Styling**
- **Shadcn UI (Latest)**: Modern component system with open code approach
  - Built on Radix UI primitives for accessibility
  - Tailwind CSS integration with CSS variables theming
  - Copy-paste component architecture for full customization
  - CLI-based component installation and management

- **Tailwind CSS 4.x**: Revolutionary utility-first CSS with major architectural improvements
  - **New High-Performance Engine**: 3.5x faster full builds, 8x faster incremental builds
  - **Zero Configuration**: No more tailwind.config.js or postcss.config.js required
  - **Single Import**: Just `@import "tailwindcss"` in CSS - no @tailwind directives
  - **First-Party Vite Plugin**: `@tailwindcss/vite` for optimal performance
  - **Automatic Content Detection**: Template files discovered automatically
  - **Modern CSS Features**: Built on cascade layers, @property, and color-mix()

#### **Development & Deployment Infrastructure**
- **GitHub Actions**: Automation for build, test, and deployment workflows
  - Automated contributor data fetching from GitHub API
  - Continuous integration with build verification
  - Automated deployment to GitHub Pages

- **GitHub Pages**: Static site hosting with custom domain support
  - Automatic SSL/TLS certificates
  - Global CDN distribution
  - Integration with GitHub Actions for automated deployments

### Architecture Patterns

#### **Component Organization**
```
src/
├── components/
│   ├── ui/           # Shadcn UI components
│   ├── layout/       # Navigation, headers, footers
│   └── sections/     # Page sections (Hero, Features, Contributors)
├── lib/              # Utilities and configurations
├── hooks/            # Custom React hooks
└── assets/           # Static assets organized by type
```

#### **Asset Organization Structure**
```
website/public/
├── icons/            # IDE platform icons, GitHub Octocat
├── graphics/         # Hero network diagram, feature showcase diagrams
└── screenshots/      # APM chat interface examples
```

#### **State Management**
- **React Built-in State**: Using useState, useReducer for local component state
- **Context API**: For theme and global application state when needed
- **No external state library**: Keeping complexity minimal for demonstration purposes

#### **Data Flow**
- **Static Build Time**: Contributor data fetched during build process
- **Dynamic Updates**: GitHub Actions workflow updates contributor data
- **Client-side Rendering**: Fast interactive experience with pre-built data

## Component Development Methodology

### **Systematic 5-Stage Component Creation Process**

Each component follows a structured development approach ensuring consistency, maintainability, and Design PRD compliance:

#### **Stage 1: Base Component Foundation**
- Read Design PRD for specifications on foundational structure and requirements.
- Create minimal functional component with Shadcn UI base or standard React structure
- Implement core state management and props interface
- Establish TypeScript interfaces and type definitions
- Set up basic event handlers and component logic
- Verify component renders without errors in development environment
- Test basic functionality and interactivity

#### **Stage 2: Visual Structure Alignment**
- Read Design PRD for specifications on dimensions, positioning, spacing, and color palette.
- Apply Design PRD specifications for dimensions, positioning, and spacing
- Implement border radius consistency (20px for floating cards and header)
- Set background colors per Design PRD palette (#000000, #181818, #AE9F8A, #A6A6A6)
- Configure responsive breakpoints (mobile, md, lg, xl)
- Apply floating card width calculations (w-[calc(100%-30%)], etc.)
- Ensure proper z-index layering and positioning contexts

#### **Stage 3: Internal Layout Architecture**
- Read Design PRD for specifications on layout, grid systems, and content flow.
- Build content containers, grids, and flex layouts per Design PRD
- Implement responsive grid systems (e.g., `grid-cols-1 lg:grid-cols-2`)
- Create carousel containers, tab systems, or navigation structures
- Establish proper content flow and visual hierarchy
- Set up asymmetric layouts where specified (Features section 35%/65% split)
- Configure overflow handling and scroll behaviors

#### **Stage 4: Content Population**
- Read Design PRD for specifications on typography, imagery, and data integration.
- Add text content with proper typography (Inter/Instrumental Sans fonts)
- Integrate SVG graphics and images with proper sizing and quality settings
- Implement dynamic data binding for interactive elements
- Add placeholder content for development testing
- Connect to data sources (JSON, API responses)
- Ensure content accessibility with proper alt text and ARIA labels

#### **Stage 5: Polish & Effects**
- Read Design PRD for specifications on animation, effects, and interaction standards.
- Implement animations (1.5s fade-ins with 0.3s delay for SVGs)
- Add glassmorphism effects (backdrop-blur, white/opacity borders)
- Apply Apple Watch-style hover interactions (scale-105 with slow return)
- Implement transition timings (300ms for hovers, 500ms for carousels)
- Add drop shadows for text readability on colored backgrounds
- Optimize performance and test cross-browser compatibility
- Ensure smooth 60fps animations and interactions

## Design Implementation Specifications

### **Color Palette & Visual System**
- **Root Background**: #000000 (pitch black void)
- **Hero/About Section**: #181818 background with #A6A6A6 text (Instrumental Sans)
- **Features Section**: #AE9F8A background with white text and drop shadows (Inter)
- **Navigation**: #000000 background with white text, invisible outline effect
- **Contributors**: Individual glass cards with backdrop blur and white/opacity borders

### **Typography System**
- **Primary Font**: Inter (navigation, Features section, body text)
- **Hero Section Font**: Instrumental Sans (titles and Hero/About carousel content)
- **Logo**: Inter Bold for "APM v0.4" branding

### **Layout & Spacing Standards**
- **Border Radius**: 20px consistent across all cards and header for seamless scroll integration
- **Card Margins**: Responsive system (5%/10%/15% side margins for mobile/tablet/desktop)
- **Floating Effect**: Cards centered with generous black void margins

### **Animation & Interaction Standards**
- **SVG Fade-ins**: 1.5s duration with 0.3s delay for graphics
- **Carousel Transitions**: 500ms ease-in-out for Hero and Features sections
- **Hover Effects**: 300ms ease-out for Apple Watch-style bubble effects
- **Scale Effects**: hover:scale-105 with slow return transition

## Existing Codebase

### Current State
The project repository contains:
- **Development Coordination Structure**: Standard systematic development directories and configuration files
- **PRD Directory**: `prd/` containing this Implementation PRD and comprehensive Design PRD documents  
- **Empty Website Directory**: No existing web application code
- **Clean Slate**: Ready for complete implementation following systematic development methodology

### Repository Structure
```
/
├── apm/                          # Development coordination artifacts
│   ├── Implementation_Plan.md     # Generated by development planning
│   └── Memory/                    # Development logs and coordination records
├── prd/                          # Project requirements (reference materials)
│   ├── Implementation_PRD.md      # This document
│   └── Design_PRD.md             # UI/UX specifications (ground truth)
└── website/                      # Target directory for web application
    └── (empty - to be created)
```

## Development Setup Process

### **Project Initialization Commands (2025)**

Current industry-standard setup for modern React development with latest tooling:

#### **1. Create Vite + React + TypeScript Project**
```bash
# Create new project with React + TypeScript template
npm create vite@latest website -- --template react-ts
cd website
npm install
```

#### **2. Install and Configure Tailwind CSS v4**
```bash
# Install Tailwind CSS v4 with Vite plugin (no PostCSS config needed)
npm install tailwindcss @tailwindcss/vite

# Install Node.js types for path resolution
npm install -D @types/node
```

**Update `vite.config.ts`:**
```typescript
import path from 'path'
import react from '@vitejs/plugin-react'
import tailwindcss from '@tailwindcss/vite'
import { defineConfig } from 'vite'

export default defineConfig({
  plugins: [react(), tailwindcss()],
  resolve: {
    alias: {
      '@': path.resolve(__dirname, './src'),
    },
  },
})
```

**Update `src/index.css`:**
```css
@import "tailwindcss";

/* Custom properties for design tokens */
:root {
  --color-void: 0 0 0;
  --color-hero-bg: 24 24 24;
  --color-hero-text: 166 166 166;
  --color-features-bg: 174 159 138;
  --color-features-text: 255 255 255;
}
```

#### **3. Configure TypeScript Path Mapping**
**Update `tsconfig.json`:**
```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

**Update `tsconfig.app.json`:**
```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

#### **4. Initialize Shadcn UI**
```bash
# Initialize Shadcn UI with CLI
npx shadcn@latest init

# Configuration options:
# - Would you like to use TypeScript? → Yes
# - Which style would you like to use? → New York (or Default)
# - Which color would you like to use as base color? → Neutral/Zinc
# - Where is your global CSS file? → src/index.css
# - Would you like to use CSS variables for colors? → Yes
# - Are you using a custom tailwind prefix? → No (leave blank)
# - Where is your tailwind.config.js located? → Not applicable (v4)
# - Configure import alias for components: → @/components
# - Configure import alias for utils: → @/lib/utils
# - Are you using React Server Components? → No
```

#### **5. Add Required Shadcn UI Components**
```bash
# Core components for Design PRD implementation
npx shadcn@latest add button        # Navigation arrows, interactive elements
npx shadcn@latest add card          # Base structure for floating cards
npx shadcn@latest add navigation-menu  # Header navigation structure
npx shadcn@latest add tabs          # Features section pill tab navigation
npx shadcn@latest add carousel      # Hero section internal carousel
npx shadcn@latest add avatar        # Contributors section GitHub avatars
npx shadcn@latest add badge         # Potential use for contributor stats
```

#### **6. Verify Installation**
**Update `src/App.tsx` to test setup:**
```tsx
import { Button } from '@/components/ui/button'
import { Card } from '@/components/ui/card'

function App() {
  return (
    <div className="min-h-screen bg-black">
      <Card className="bg-[#181818] rounded-[20px] p-12 mx-auto max-w-7xl">
        <h1 className="text-3xl font-bold text-white font-['Inter']">
          Vite + React + TypeScript + Tailwind v4 + Shadcn UI
        </h1>
        <div className="flex gap-2 mt-4">
          <Button>Primary</Button>
          <Button variant="outline">Outline</Button>
          <Button variant="secondary">Secondary</Button>
        </div>
      </Card>
    </div>
  )
}

export default App
```

#### **7. Development Server**
```bash
# Start development server
npm run dev
```

## Shadcn UI Component Implementation Strategy

### **Component Selection & Customization Approach**

The Design PRD specifies a unique void-like aesthetic that requires extensive customization of standard Shadcn UI components. This section defines which components to use as base structures and how to customize them for the specific design requirements.

### **Navigation Header Component**
**Shadcn Base**: `navigation-menu` + `button`
```tsx
// Base structure with Design PRD customization
<NavigationMenu className="fixed top-0 left-0 right-0 z-50 bg-black rounded-[20px] px-8 py-4">
  <NavigationMenuList className="flex items-center justify-between max-w-7xl mx-auto">
    {/* Custom styling overrides default Shadcn appearance */}
  </NavigationMenuList>
</NavigationMenu>
```

**Required Customizations:**
- **Background**: Override to `bg-black` (invisible outline effect)
- **Border Radius**: Force `rounded-[20px]` for card alignment
- **Positioning**: Fixed positioning with proper z-index
- **Hover Effects**: Custom `hover:bg-white/10` replacing default Shadcn hover states

### **Hero Section Component**
**Shadcn Base**: `card` + `carousel` + `button`
```tsx
// Floating card with internal carousel
<Card className="bg-[#181818] rounded-[20px] p-12 my-16 mx-auto max-w-7xl w-[calc(100%-30%)]">
  <Carousel className="carousel-container overflow-hidden">
    <CarouselContent className="flex transition-transform duration-500 ease-in-out">
      {/* Custom slide content */}
    </CarouselContent>
    <CarouselPrevious className="hero-nav-arrow" />
    <CarouselNext className="hero-nav-arrow" />
  </Carousel>
</Card>
```

**Required Customizations:**
- **Card Background**: Override to exact Design PRD color `bg-[#181818]`
- **Border Radius**: Maintain `rounded-[20px]` consistency
- **Carousel Navigation**: Replace default arrows with chunky outline design
- **Typography**: Override with Instrumental Sans font family
- **Width System**: Custom responsive width calculation for floating effect

### **Features Section Component**
**Shadcn Base**: `card` + `tabs` + custom layout
```tsx
// Asymmetric floating card with pill tab navigation
<Card className="bg-[#AE9F8A] rounded-[20px] p-12 my-16 mx-auto max-w-7xl w-[calc(100%-30%)]">
  <div className="top-section mb-16">{/* IDE Integration content */}</div>
  <div className="bottom-section">
    <Tabs defaultValue="multi-agent" className="w-full">
      <TabsList className="bg-black rounded-full p-2 flex space-x-1">
        <TabsTrigger className="pill-tab" value="multi-agent">Multi-Agent Orchestration</TabsTrigger>
        {/* Additional tabs */}
      </TabsList>
      <TabsContent value="multi-agent">{/* Feature content */}</TabsContent>
    </Tabs>
  </div>
</Card>
```

**Required Customizations:**
- **Card Background**: Override to `bg-[#AE9F8A]` (warm beige)
- **Tab Navigation**: Complete restyling to pill design with "hole effect"
- **Active State**: Custom `data-[active]:bg-[#AE9F8A] data-[active]:text-black`
- **Text Color**: Override all text to white with drop shadows
- **Layout**: Custom asymmetric height distribution (35%/65%)

### **Contributors Section Component**
**Shadcn Base**: `avatar` + custom card structure
```tsx
// Individual glass cards on void background (NO Shadcn Card component)
<section className="contributors-section py-16 bg-black">
  <div className="contributors-grid max-w-7xl mx-auto w-[calc(100%-30%)]">
    <div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-6">
      <a href="https://github.com/username" className="contributor-card group cursor-pointer">
        <div className="glass-card bg-white/10 backdrop-blur-md border border-white/20 rounded-2xl p-6">
          <Avatar className="w-16 h-16 mx-auto mb-4">
            <AvatarImage src="https://github.com/username.png" />
            <AvatarFallback>UN</AvatarFallback>
          </Avatar>
          {/* Username and commit count */}
        </div>
      </a>
    </div>
  </div>
</section>
```

**Required Customizations:**
- **NO Shadcn Card**: Use custom div with glassmorphism styling
- **Avatar Borders**: Custom `border-2 border-white/30 group-hover:border-white/50`
- **Glass Effects**: Custom backdrop blur and opacity borders
- **Hover Animation**: Apple Watch-style `hover:scale-105` with slow return
- **Background**: Pure black void, not card-based

### **Component Customization Patterns**

#### **Override Strategy**
```tsx
// Pattern for overriding Shadcn defaults with Design PRD specifications
const customButtonStyles = cn(
  "default-shadcn-classes", // Keep accessibility and base functionality
  "bg-black text-white rounded-[20px]", // Override appearance
  "hover:bg-white/10 transition-all duration-300", // Custom interactions
  className // Allow additional customizations
)
```

#### **Typography Integration**
```tsx
// Font family overrides for Design PRD typography system
<h1 className={cn(
  "text-4xl font-bold", // Shadcn typography classes
  "font-['Instrumental_Sans'] text-[#A6A6A6]" // Design PRD overrides
)}>
```

#### **Color System Integration**
```tsx
// Design PRD color palette overrides
const designColors = {
  void: "#000000",
  hero: "#181818", 
  heroText: "#A6A6A6",
  features: "#AE9F8A",
  featuresText: "#FFFFFF"
}
```

### **Components NOT Used from Shadcn**

**Dialog/Modal**: Not needed for single-page landing design
**Form Components**: No forms in current design specifications  
**Table**: Not applicable to current content structure
**Sheet/Drawer**: Mobile navigation uses same header pattern
**Toast/Alert**: No notification system required
**Progress**: No loading states requiring progress indicators

### **Custom Components Required**

**GlassmorphismCard**: Contributors section glass effects not available in Shadcn
**FloatingCardWrapper**: Responsive width system with void margins
**SVGWithFadeIn**: Animation wrapper for graphics with Design PRD timing
**PillTabNavigation**: Complete custom implementation for "hole effect"
**AppleWatchHover**: Custom hover effect component for scale animations

### **Accessibility Preservation**

When customizing Shadcn components, maintain:
- **ARIA labels and roles** from base components
- **Keyboard navigation** for carousels and tab systems
- **Focus states** with custom styling that maintains visibility
- **Screen reader support** through semantic HTML structure
- **Touch targets** meeting minimum size requirements (44px)

### **Key Setup Differences in 2025**

#### **Tailwind CSS v4 Changes**
- **No `tailwind.config.js`** - Configuration handled through CSS
- **No PostCSS configuration** - Vite plugin handles everything
- **Single CSS import** - Just `@import "tailwindcss"` instead of @tailwind directives
- **Automatic content detection** - No need to specify template file paths
- **Zero configuration** - Works out of the box

#### **Shadcn UI Modern Setup**
- **Automatic dependency installation** - CLI handles all required packages
- **Path alias configuration** - Automatic setup for clean imports
- **Component customization** - Full source code access for modifications
- **TypeScript-first** - Full type safety and IntelliSense support

#### **Vite Optimization**
- **Native TypeScript** - No additional transpilation needed
- **Path resolution** - Clean imports with @ alias
- **Fast HMR** - Instant updates during development
- **Optimized builds** - Production-ready asset optimization

### Systematic Development Coordination

This project demonstrates coordinated development capabilities through:

#### **Specialized Development Focus Areas**
- **Research & Setup**: Technology stack research, project initialization, environment configuration
- **Design Implementation**: Void-like aesthetic, floating cards, glassmorphism effects, Apple Watch interactions
- **UI Development**: Component creation with Design PRD specifications, carousel mechanics, pill tab navigation
- **Visual Systems**: SVG quality preservation, animation consistency, responsive floating card patterns
- **Integration & Deployment**: GitHub Actions automation, contributor data fetching, production deployment

#### **Structured Development Process**
- **Focused Implementation Cycles**: Clear deliverables with structured development stages
- **Coordination Points**: Proper handoffs between development specializations
- **Quality Checkpoints**: User validation at implementation milestones
- **Iterative Refinement**: User feedback integration at each development stage

#### **Transparent Development Process**
- **Visible Project Artifacts**: All planning, coordination, and execution logs accessible
- **Development Trail**: Complete history of decisions and implementation choices
- **Methodology Validation**: Real-time demonstration of systematic development coordination

### Quality Standards

#### **Code Quality**
- **TypeScript Strict Mode**: Full type safety with comprehensive error checking
- **Modern React Patterns**: Functional components, hooks, and latest best practices  
- **Accessibility**: WCAG 2.1 AA compliance through Shadcn UI components
- **Performance**: Optimized bundle sizes, lazy loading, and efficient rendering

#### **Design Quality**
- **Visual Consistency**: 20px border radius maintained across all components for scroll integration
- **Animation Standards**: Consistent timing and easing functions across all interactions
- **Color Precision**: Exact color values maintained (#000000, #181818, #AE9F8A, #A6A6A6)
- **Typography Hierarchy**: Proper font usage (Inter, Instrumental Sans) with appropriate scaling

#### **Development Experience**
- **Fast Development Cycle**: Vite's instant HMR for rapid iteration
- **Comprehensive Testing**: Build verification and deployment testing
- **Professional Tooling**: ESLint, Prettier, and development workflow optimization

#### **Production Readiness**
- **Optimized Builds**: Production-ready assets with code splitting
- **Responsive Design**: Mobile-first approach with floating card adaptation
- **Cross-Browser Support**: Modern browser compatibility with graceful degradation
- **SEO Optimization**: Proper meta tags, semantic HTML, and performance optimization

### User Experience Goals

#### **Demonstration Effectiveness**
- **Clear APM Value Proposition**: Immediate understanding of APM benefits through void-like aesthetic
- **Interactive Examples**: Engaging demonstration of coordination capabilities with Apple Watch-style interactions
- **Professional Presentation**: Production-quality results showcasing APM effectiveness

#### **Technical Excellence**  
- **Modern Web Standards**: Latest development practices and technologies
- **Smooth Performance**: Fast loading, responsive interactions, optimized user experience
- **Visual Appeal**: Void-like design with floating cards reflecting professional development standards

#### **Accessibility & Usability**
- **Universal Access**: Compatible with assistive technologies
- **Intuitive Navigation**: Clear information hierarchy and user flow with glassmorphism visual cues
- **Mobile Experience**: Responsive floating card design for all device types

## Success Criteria

### **Functional Requirements**
- **Working Web Application**: Fully functional landing page with void-like aesthetic and floating card design
- **GitHub Integration**: Automated contributor data fetching with glassmorphism card display
- **Responsive Design**: Perfect rendering across desktop, tablet, and mobile devices with adaptive card margins
- **Performance**: Fast loading times and smooth Apple Watch-style interactions

### **Development Methodology Requirements**  
- **Complete Systematic Workflow**: End-to-end project coordination from setup through deployment
- **Specialized Development Coordination**: Successful handoffs between different development focus areas
- **Quality Outcomes**: Professional results validating systematic development coordination effectiveness
- **Transparent Process**: All project coordination artifacts visible and accessible for review

### **Technical Achievement Targets**
- **Modern Stack Integration**: Seamless operation of Vite + React + TypeScript + Shadcn UI with Design PRD specifications
- **Automated Deployment**: Successful GitHub Actions → GitHub Pages workflow
- **Code Quality**: Clean, maintainable, and well-documented implementation
- **User Experience**: Engaging, accessible, and professional void-like aesthetic with floating interactions

## Development Roadmap

### **Stage 1: Foundation & Environment Setup**
#### **1.1 Technology Stack Research**
- Research current best practices for Vite + React + TypeScript + Shadcn UI + Tailwind CSS v4
- Document setup procedures, compatibility issues, and recommended approaches
- Provide structured setup guidance for development environment

#### **1.2 Project Structure Setup**
- Initialize Vite + React + TypeScript project in `/website` directory
- Configure build system, TypeScript settings, and development environment
- Verify basic project structure and build capability

#### **1.3 Dependencies Installation & Configuration**
- Install and configure Tailwind CSS v4 using Vite plugin approach
- Set up Shadcn UI system with path aliases and component architecture
- Install required Shadcn UI components for Design PRD implementation (navigation-menu, card, carousel, tabs, avatar, button)
- Test complete development environment with sample components

### **Stage 2: Design Foundation & Global Styling**
#### **2.1 Global CSS Configuration**
- Review Design PRD for global styling requirements and void-like aesthetic specifications
- Establish CSS configurations based on Design PRD specifications with exact color values
- Configure Tailwind custom theme, typography, and color system following Design PRD

#### **2.2 Component Architecture Setup**
- Review Design PRD for component structure requirements and floating card patterns
- Plan component hierarchy and organization based on Design PRD specifications
- Establish naming conventions and file structure for asset organization
- Implement Shadcn UI component customization strategy for Design PRD compliance

### **Stage 3: Navigation Header Development**

#### **3.1 Header Component Creation (5-Phase Implementation)**

**Phase 1 - Base Component Foundation:**
- Create `NavigationHeader.tsx` with basic functional structure
- Implement navigation item array and basic logo text
- Set up TypeScript interfaces for props and navigation items
- Verify component renders and basic click handlers work

**Phase 2 - Visual Structure Alignment:**
```tsx
// Apply Design PRD positioning, dimensions, and colors
<header className="fixed top-0 left-0 right-0 z-50 bg-black rounded-[20px]">
  <nav className="px-8 py-4">
    {/* Apply exact spacing and positioning */}
  </nav>
</header>
```

**Phase 3 - Internal Layout Architecture:**
```tsx
// Build flex layout with proper content distribution
<nav className="flex items-center justify-between max-w-7xl mx-auto">
  <div className="text-white font-bold font-['Inter'] text-lg">APM v0.4</div>
  <div className="flex items-center space-x-8">
    {/* Navigation items with proper spacing */}
  </div>
</nav>
```

**Phase 4 - Content Population:**
- Add all navigation button texts (About, Features, Contributors, Documentation)
- Integrate GitHub Octocat SVG icon (request asset from user)
- Implement onClick handlers for scroll-to-section functionality
- Add proper TypeScript types for all interactive elements

**Phase 5 - Polish & Effects:**
```tsx
// Apply hover effects and transition animations
<button className="text-white font-['Inter'] px-4 py-2 rounded-lg transition-all duration-300 hover:bg-white/10 hover:backdrop-blur-sm">
  About
</button>
```

#### **3.2 Header Functionality Implementation**
- Implement scroll event listeners for invisible outline effect
- Create smooth scroll-to-section navigation functions
- Add carousel slide trigger for About button
- Test fixed positioning during scroll with void background integration

### **Stage 4: Hero Section Development**

#### **4.1 Hero Section Component Creation (5-Phase Implementation)**

**Phase 1 - Base Component Foundation:**
```tsx
// Create HeroSection.tsx with carousel state management
export const HeroSection = () => {
  const [currentSlide, setCurrentSlide] = useState(0);
  
  return (
    <section>
      <div className="carousel-container">
        <div className="carousel-slides">
          <div>Slide 1: Hero Content</div>
          <div>Slide 2: About Content</div>
        </div>
      </div>
      <button onClick={() => setCurrentSlide(0)}>Previous</button>
      <button onClick={() => setCurrentSlide(1)}>Next</button>
    </section>
  );
};
```

**Phase 2 - Visual Structure Alignment:**
```tsx
// Apply floating card design with responsive margins
<section className="bg-[#181818] rounded-[20px] p-12 my-16 mx-auto max-w-7xl w-[calc(100%-30%)] md:w-[calc(100%-20%)] sm:w-[calc(100%-10%)]">
  {/* Card maintains floating effect across all devices */}
</section>
```

**Phase 3 - Internal Layout Architecture:**
```tsx
// Create two-column responsive grid
<div className="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
  <div className="text-content">
    {/* Text column structure */}
  </div>
  <div className="graphic-container">
    {/* SVG column structure */}
  </div>
</div>
```

**Phase 4 - Content Population:**
```tsx
// Add Instrumental Sans typography and content
<h1 className="text-4xl lg:text-5xl font-bold font-['Instrumental_Sans'] text-[#A6A6A6] mb-4">
  Agentic Project Management
</h1>
<p className="text-lg font-['Instrumental_Sans'] text-[#A6A6A6]">
  Manage complex projects with a team of AI assistants, smoothly and efficiently.
</p>
<img src="/hero-network-diagram.svg" alt="APM Network" className="w-full h-auto" />
```

**Phase 5 - Polish & Effects:**
```tsx
// Implement animations and carousel transitions
<img src="/hero-network-diagram.svg" 
     className="w-full h-auto opacity-0 animate-fade-in-delayed"
     style="animation: fade-in-delayed 1.5s ease-out forwards; animation-delay: 300ms;" />

// Carousel slide transition
<div className="carousel-slides flex transition-transform duration-500 ease-in-out"
     style={{ transform: `translateX(-${currentSlide * 100}%)` }}>
```

#### **4.2 Carousel Navigation Implementation**
- Create chunky arrow components with outline styling (#A6A6A6 color)
- Implement conditional navigation (disable at boundaries)
- Add keyboard navigation support (arrow keys)
- Connect to header About button for external trigger

### **Stage 5: Features Section Development**

#### **5.1 Features Section Component Creation (5-Phase Implementation)**

**Phase 1 - Base Component Foundation:**
```tsx
// Create FeaturesSection.tsx with tab state
export const FeaturesSection = () => {
  const [activeTab, setActiveTab] = useState('multi-agent');
  
  const tabs = [
    { id: 'multi-agent', label: 'Multi-Agent Orchestration' },
    { id: 'implementation', label: 'Implementation Plan' },
    { id: 'memory', label: 'Dynamic Memory Bank' },
    { id: 'handover', label: 'Handover Procedure' }
  ];
  
  return (
    <section>
      <div className="top-section">{/* IDE Integration */}</div>
      <div className="bottom-section">
        {tabs.map(tab => (
          <button key={tab.id} onClick={() => setActiveTab(tab.id)}>
            {tab.label}
          </button>
        ))}
        <div>{/* Tab content */}</div>
      </div>
    </section>
  );
};
```

**Phase 2 - Visual Structure Alignment:**
```tsx
// Apply warm beige background and floating card
<section className="bg-[#AE9F8A] rounded-[20px] p-12 my-16 mx-auto max-w-7xl w-[calc(100%-30%)] md:w-[calc(100%-20%)] sm:w-[calc(100%-10%)]">
  {/* Maintain floating card consistency */}
</section>
```

**Phase 3 - Internal Layout Architecture:**
```tsx
// Create asymmetric layout (35%/65% split)
<div className="space-y-16">
  <div className="top-section"> {/* ~35% of card height */}
    <div className="grid grid-cols-1 lg:grid-cols-2 gap-8">
      <div>{/* IDE content left */}</div>
      <div>{/* Screenshot right */}</div>
    </div>
  </div>
  
  <div className="bottom-section"> {/* ~65% of card height */}
    <h2 className="text-center mb-8">{/* Section header */}</h2>
    <div className="pill-nav">{/* Tab navigation */}</div>
    <div className="feature-content">{/* Tab content */}</div>
  </div>
</div>
```

**Phase 4 - Content Population:**
```tsx
// Add IDE integration content
<h2 className="text-3xl font-bold font-['Inter'] text-white">
  Integrates Seamlessly with Your Favorite AI IDEs
</h2>
<p className="text-lg font-['Inter'] text-white">
  APM functions directly where your code lives...
</p>

// Add IDE icons
<div className="flex space-x-6">
  <img src="/icons/windsurf-icon.svg" alt="Windsurf" className="w-12 h-12" />
  <img src="/icons/cursor-icon.svg" alt="Cursor" className="w-12 h-12" />
  <img src="/icons/vscode-icon.svg" alt="VS Code" className="w-12 h-12" />
</div>

// Add feature content for each tab
{activeTab === 'multi-agent' && (
  <div className="grid grid-cols-1 lg:grid-cols-2 gap-8">
    <p className="text-white">APM uses a central orchestrator...</p>
    <img src="/graphics/multi-agent-diagram.svg" alt="Multi-Agent" />
  </div>
)}
```

**Phase 5 - Polish & Effects:**
```tsx
// Implement pill tab "hole effect"
<div className="bg-black rounded-full p-2 inline-flex">
  {tabs.map(tab => (
    <button 
      className={`px-6 py-3 rounded-full transition-all duration-300 ${
        activeTab === tab.id 
          ? 'bg-[#AE9F8A] text-black' // Hole effect
          : 'text-white hover:bg-white/10'
      }`}
    >
      {tab.label}
    </button>
  ))}
</div>

// Add drop shadows to text
<p className="text-white drop-shadow-md">
  {/* White text with shadow for readability */}
</p>

// SVG fade-in animations
<img className="opacity-0 animate-fade-in-delayed" />
```

#### **5.2 Features Section Interactivity**
- Implement smooth tab content transitions
- Add keyboard navigation for tab selection
- Create responsive behavior for pill navigation wrapping
- Test asymmetric layout on different screen sizes

### **Stage 6: Contributors Section Development**

#### **6.1 Contributors Grid Creation (5-Phase Implementation)**

**Phase 1 - Base Component Foundation:**
```tsx
// Create ContributorsSection.tsx with data structure
export const ContributorsSection = () => {
  const [contributors, setContributors] = useState([]);
  
  useEffect(() => {
    // Load contributor data from JSON
    fetch('/data/contributors.json')
      .then(res => res.json())
      .then(data => setContributors(data));
  }, []);
  
  return (
    <section className="py-16">
      <h2>Contributors</h2>
      <div className="contributors-grid">
        {contributors.map(contributor => (
          <div key={contributor.username}>
            {/* Card structure */}
          </div>
        ))}
      </div>
    </section>
  );
};
```

**Phase 2 - Visual Structure Alignment:**
```tsx
// Apply void background and section width
<section className="py-16 bg-black">
  <div className="max-w-7xl mx-auto w-[calc(100%-30%)] md:w-[calc(100%-20%)] sm:w-[calc(100%-10%)]">
    {/* Match width of floating cards above */}
  </div>
</section>
```

**Phase 3 - Internal Layout Architecture:**
```tsx
// Create responsive grid system
<div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-6">
  {contributors.map(contributor => (
    <a href={`https://github.com/${contributor.username}`} 
       target="_blank" 
       rel="noopener noreferrer"
       className="contributor-card group cursor-pointer">
      <div className="p-6">
        <div className="avatar-container mb-4 flex justify-center">
          {/* Avatar */}
        </div>
        <div className="text-center">
          {/* Username and stats */}
        </div>
      </div>
    </a>
  ))}
</div>
```

**Phase 4 - Content Population:**
```tsx
// Add GitHub avatar and user data
<img src={`https://github.com/${contributor.username}.png`} 
     alt={contributor.username}
     className="w-16 h-16 rounded-full" />

<h3 className="text-white font-['Inter'] font-semibold text-lg">
  {contributor.username}
</h3>

<p className="text-white/80 font-['Inter'] text-sm">
  <span className="font-bold">{contributor.commits}</span> commits
</p>
```

**Phase 5 - Polish & Effects:**
```tsx
// Apply glassmorphism and Apple Watch hover
<div className="glass-card bg-white/10 backdrop-blur-md border border-white/20 rounded-2xl p-6 
                transition-all duration-300 ease-out 
                hover:scale-105 hover:bg-white/15">
  
  {/* Enhanced avatar border on hover */}
  <img className="w-16 h-16 rounded-full border-2 border-white/30 
                  group-hover:border-white/50 transition-colors duration-300" />
  
  {/* Content with proper opacity hierarchy */}
  <h3 className="text-white">{/* Full opacity for primary info */}</h3>
  <p className="text-white/80">{/* Reduced opacity for secondary info */}</p>
</div>
```

#### **6.2 Glass Card Refinement**
- Test glassmorphism effects across browsers
- Ensure backdrop-filter support with fallbacks
- Validate Apple Watch-style scale animation smoothness
- Test touch interactions on mobile devices

### **Stage 7: GitHub Integration & Automation (Comprehensive Guide)**

#### **7.1 GitHub Actions Fundamentals for Beginners**

**What is GitHub Actions?**
GitHub Actions is a CI/CD (Continuous Integration/Continuous Deployment) platform that allows you to automate tasks directly in your GitHub repository. Think of it as a robot that can perform tasks for you whenever certain events happen in your repository.

**Key Concepts Explained:**
- **Workflow**: A set of automated tasks defined in a YAML file (like a recipe)
- **Job**: A group of steps that run on the same virtual computer
- **Step**: A single task within a job (like "install dependencies" or "run tests")
- **Action**: A reusable piece of code that performs a specific task
- **Event**: Something that triggers a workflow (push, pull request, schedule, etc.)
- **Runner**: The virtual computer that executes your jobs

**Basic Workflow Structure:**
```yaml
name: My Workflow Name              # What you'll see in GitHub UI
on:                                 # When this workflow should run
  push:                            # Run when code is pushed
    branches: [main]               # Only for the main branch
  workflow_dispatch:               # Allow manual trigger from GitHub UI

jobs:                              # The tasks to perform
  my-job-name:                     # Name of your job
    runs-on: ubuntu-latest         # Use latest Ubuntu virtual machine
    steps:                         # Individual tasks in order
      - name: Check out code       # Human-readable step name
        uses: actions/checkout@v3  # Use pre-built checkout action
      
      - name: Run a command        # Another step
        run: echo "Hello World"    # Shell command to execute
```

#### **7.2 Complete Contributor Data Fetching Implementation**

**Step 1: Create the Workflow File**
Create `.github/workflows/update-contributors.yml`:

```yaml
name: Update Contributors Data

# When to run this workflow
on:
  # Run every day at 2 AM UTC
  schedule:
    - cron: '0 2 * * *'
  
  # Run when pushing to main branch
  push:
    branches: [main]
    paths:
      - '.github/workflows/update-contributors.yml'
  
  # Allow manual trigger from GitHub UI
  workflow_dispatch:

# Environment variables available to all jobs
env:
  REPO_OWNER: agentic-project-management
  REPO_NAME: apm

jobs:
  fetch-contributors:
    runs-on: ubuntu-latest
    
    permissions:
      contents: write  # Allow writing to repository
    
    steps:
      # Step 1: Check out your repository code
      - name: Checkout Repository
        uses: actions/checkout@v3
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
      
      # Step 2: Set up Node.js environment
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '20'
      
      # Step 3: Create directory for data
      - name: Create Data Directory
        run: |
          mkdir -p website/public/data
      
      # Step 4: Fetch contributor data
      - name: Fetch Contributors from GitHub API
        run: |
          # Create a Node.js script to fetch data
          cat > fetch-contributors.js << 'EOF'
          const fs = require('fs');
          const https = require('https');
          
          // Configuration
          const REPO_OWNER = process.env.REPO_OWNER;
          const REPO_NAME = process.env.REPO_NAME;
          const OUTPUT_FILE = 'website/public/data/contributors.json';
          
          // GitHub API request options
          const options = {
            hostname: 'api.github.com',
            path: `/repos/${REPO_OWNER}/${REPO_NAME}/contributors`,
            headers: {
              'User-Agent': 'APM-Landing-Page-Bot',
              'Accept': 'application/vnd.github.v3+json'
            }
          };
          
          console.log(`Fetching contributors for ${REPO_OWNER}/${REPO_NAME}...`);
          
          // Make API request
          https.get(options, (res) => {
            let data = '';
            
            res.on('data', (chunk) => {
              data += chunk;
            });
            
            res.on('end', () => {
              try {
                const contributors = JSON.parse(data);
                
                // Check if we got an error response
                if (contributors.message) {
                  console.error('GitHub API Error:', contributors.message);
                  process.exit(1);
                }
                
                // Process contributor data
                const processedData = contributors
                  .filter(c => c.type === 'User') // Only real users, not bots
                  .map(contributor => ({
                    username: contributor.login,
                    avatar_url: contributor.avatar_url,
                    profile_url: contributor.html_url,
                    commits: contributor.contributions
                  }))
                  .sort((a, b) => b.commits - a.commits); // Sort by commits
                
                // Save to file
                fs.writeFileSync(OUTPUT_FILE, JSON.stringify(processedData, null, 2));
                console.log(`Successfully saved ${processedData.length} contributors to ${OUTPUT_FILE}`);
                
                // Display summary
                console.log('\nTop 5 Contributors:');
                processedData.slice(0, 5).forEach((c, i) => {
                  console.log(`${i + 1}. ${c.username}: ${c.commits} commits`);
                });
              } catch (error) {
                console.error('Error processing data:', error);
                process.exit(1);
              }
            });
          }).on('error', (err) => {
            console.error('Request failed:', err);
            process.exit(1);
          });
          EOF
          
          # Run the script
          node fetch-contributors.js
      
      # Step 5: Verify the data file was created
      - name: Verify Data File
        run: |
          if [ -f "website/public/data/contributors.json" ]; then
            echo "✅ Contributors file created successfully"
            echo "File contents preview:"
            head -20 website/public/data/contributors.json
          else
            echo "❌ Contributors file was not created"
            exit 1
          fi
      
      # Step 6: Commit and push changes
      - name: Commit Updated Data
        run: |
          git config --local user.email "github-actions[bot]@users.noreply.github.com"
          git config --local user.name "github-actions[bot]"
          
          # Check if there are changes
          if git diff --quiet website/public/data/contributors.json; then
            echo "No changes to contributors data"
          else
            git add website/public/data/contributors.json
            git commit -m "🤖 Update contributors data [skip ci]"
            git push
            echo "✅ Changes pushed to repository"
          fi
```

**Step 2: Understanding the Workflow**

This workflow does the following:
1. **Triggers**: Runs daily at 2 AM, on pushes to main, or manually
2. **Checkout**: Gets your repository code
3. **Setup**: Prepares Node.js environment
4. **Fetch**: Calls GitHub API to get contributor data
5. **Process**: Formats and sorts the data
6. **Save**: Writes to `contributors.json`
7. **Commit**: Pushes changes back to repository

**Step 3: Testing Your Workflow**

1. **Manual Trigger Test:**
   - Go to your repository on GitHub
   - Click "Actions" tab
   - Select "Update Contributors Data" workflow
   - Click "Run workflow" button
   - Select branch and click green "Run workflow" button

2. **Monitor Execution:**
   - Click on the running workflow to see live logs
   - Each step will show ✓ when complete or ✗ if failed
   - Click on any step to see detailed output

3. **Debugging Common Issues:**

```yaml
# Add debug output to any step
- name: Debug Information
  run: |
    echo "Current directory: $(pwd)"
    echo "Files in directory:"
    ls -la
    echo "GitHub Token available: ${{ secrets.GITHUB_TOKEN != '' }}"
```

#### **7.3 Deployment Workflow**

**Create `.github/workflows/deploy.yml`:**

```yaml
name: Deploy to GitHub Pages

on:
  # Deploy when contributors data is updated
  push:
    branches: [main]
    paths:
      - 'website/**'
      - '.github/workflows/deploy.yml'
  
  # Allow manual deployment
  workflow_dispatch:

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    
    permissions:
      contents: read
      pages: write
      id-token: write
    
    steps:
      # Step 1: Checkout code
      - name: Checkout Repository
        uses: actions/checkout@v3
      
      # Step 2: Setup Node.js
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '20'
          cache: 'npm'
          cache-dependency-path: website/package-lock.json
      
      # Step 3: Install dependencies
      - name: Install Dependencies
        working-directory: website
        run: |
          echo "📦 Installing dependencies..."
          npm ci  # ci is faster than install for automated environments
      
      # Step 4: Build the application
      - name: Build Application
        working-directory: website
        run: |
          echo "🔨 Building application..."
          npm run build
          echo "✅ Build complete"
      
      # Step 5: Setup GitHub Pages
      - name: Setup Pages
        uses: actions/configure-pages@v3
      
      # Step 6: Upload build artifacts
      - name: Upload Artifacts
        uses: actions/upload-pages-artifact@v2
        with:
          path: website/dist
      
      # Step 7: Deploy to GitHub Pages
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v2
        
      # Step 8: Output deployment URL
      - name: Display Deployment URL
        run: |
          echo "🚀 Deployment complete!"
          echo "🌐 Your site is live at: https://${{ github.repository_owner }}.github.io/${{ github.event.repository.name }}/"
```

#### **7.4 Troubleshooting Guide for GitHub Actions**

**Common Issues and Solutions:**

1. **Permission Denied Errors:**
```yaml
# Add permissions to your job
jobs:
  my-job:
    permissions:
      contents: write  # To push changes
      pages: write     # To deploy to Pages
```

2. **Secrets Not Working:**
- `${{ secrets.GITHUB_TOKEN }}` is automatically available
- Custom secrets: Settings → Secrets → Actions → New repository secret

3. **Workflow Not Triggering:**
- Check workflow file is in `.github/workflows/` directory
- Verify YAML syntax (use online YAML validator)
- Check branch names match your repository

4. **API Rate Limiting:**
```yaml
# Add rate limit handling
- name: Check API Rate Limit
  run: |
    curl -H "Accept: application/vnd.github.v3+json" \
         https://api.github.com/rate_limit
```

5. **Debugging Variables:**
```yaml
# Print all environment variables (careful with secrets!)
- name: Debug Environment
  run: |
    echo "Repository: ${{ github.repository }}"
    echo "Branch: ${{ github.ref }}"
    echo "Event: ${{ github.event_name }}"
```

**Best Practices for Beginners:**

1. **Start Simple**: Test with basic echo commands first
2. **Use Pre-built Actions**: Search GitHub Marketplace for existing solutions
3. **Version Your Actions**: Use specific versions (`@v3`) not `@latest`
4. **Add Status Badges**: Show workflow status in README
```markdown
![Build Status](https://github.com/USERNAME/REPO/actions/workflows/deploy.yml/badge.svg)
```

5. **Limit Trigger Conditions**: Avoid unnecessary runs
```yaml
on:
  push:
    branches: [main]
    paths-ignore:
      - '**.md'  # Don't run for markdown changes
      - 'docs/**'  # Don't run for documentation
```

### **Stage 8: Data Integration & Dynamic Content**

#### **8.1 JSON Dataset Integration**
- Create React hook for loading contributor data
- Implement error boundaries for data loading failures
- Add loading states with skeleton components
- Cache data in sessionStorage for performance

#### **8.2 Contributors Data Binding**
- Connect Contributors Section to JSON data source
- Implement fallback UI for missing data
- Add refresh mechanism for manual data updates
- Validate data integrity and handle edge cases

### **Stage 9: Content & Documentation Updates**

#### **9.1 README Content Development**
- Replace APM template content with project-specific documentation
- Create comprehensive setup guide
- Document GitHub Actions workflows
- Add troubleshooting section

#### **9.2 SEO & Meta Content**
- Implement Open Graph meta tags
- Add Twitter Card meta tags
- Create sitemap.xml
- Configure robots.txt

### **Stage 10: Deployment Setup & Production**

#### **10.1 GitHub Pages Configuration**
- Configure Vite for GitHub Pages base path
- Set up custom domain (if applicable)
- Enable GitHub Pages in repository settings
- Configure deployment branch

#### **10.2 Production Deployment & Testing**
- Execute first production deployment
- Test all interactive features in production
- Validate responsive design on real devices
- Monitor GitHub Actions deployment logs

### **Stage 11: Final Testing & Project Completion**

#### **11.1 Comprehensive Quality Assurance**
- Test all animations and transitions
- Validate accessibility with screen readers
- Check cross-browser compatibility
- Performance audit with Lighthouse

#### **11.2 Project Handover & Documentation**
- Create maintenance guide
- Document component structure
- Provide update procedures for content
- Final sign-off and approval

This Implementation PRD serves as the comprehensive technical foundation for systematic development coordination, ensuring both the web application functionality and the development methodology demonstration meet professional standards while showcasing the practical benefits of coordinated, specialized project development workflows with the void-like aesthetic and modern interaction patterns defined in the Design PRD.