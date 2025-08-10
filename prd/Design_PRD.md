# APM Landing Page - Design PRD

**Document Version:** 1.1  
**Created:** August 2025  
**Last Updated:** August 2025  
**Purpose:** Comprehensive design specification for APM landing page and documentation platform user interface

## Design Overview

### **Design Philosophy**
Modern dark theme landing page featuring a **"void-like" aesthetic** where content sections float as rounded cards against a pitch-black background. The design emphasizes **minimal visual hierarchy** with strategic use of contrast, creating an immersive experience that guides users through distinct content zones. The floating card pattern creates **visual separation** while maintaining design cohesion across sections.

### **Visual Hierarchy & Layout Strategy**
- **Pitch-black void background** creates seamless header integration and floating card contrast
- **Floating card pattern** with consistent rounded corners for all content sections
- **Strategic scroll mechanics** where header outline becomes invisible against void, then aligns perfectly with card edges
- **Two-column layouts** within cards for content organization and visual balance

### **Target User Experience**
Immersive, professional presentation showcasing APM methodology through **visual storytelling**. Users navigate through distinct floating content zones, each with specialized color palettes and interactive elements, creating a journey-like experience that demonstrates systematic project management capabilities.

### **Responsive Design Approach**
**Mobile-first floating aesthetic** maintained across all device sizes. Cards remain centered with proportional side margins, preserving the void-like theme while ensuring optimal readability and interaction on all devices.

---

## Global Design System & Styling

### **General Design Description**
Modern dark theme landing page featuring a **"void-like" aesthetic** where content sections float as rounded cards against a pitch-black background. The design emphasizes **minimal visual hierarchy** with strategic use of contrast, creating an immersive experience that guides users through distinct content zones. The floating card pattern creates **visual separation** while maintaining design cohesion across sections.

### **Color Palette**
**Primary Background:**
- Root Background: `#000000` (pitch black void)
- Creates seamless header integration and floating card contrast

**Section-Specific Palettes:**
- **Hero/About Section**: `#181818` background, `#A6A6A6` text (muted, professional)
- **Features Section**: `#AE9F8A` background (warm beige), `#FFFFFF` text with drop shadow
- **Navigation**: `#000000` background, `#FFFFFF` text (invisible outline effect)
- **Contributors Section**: Glass/glossy finish cards (to be refined collaboratively)

**Semantic Colors:**
- Interactive elements: `#FFFFFF` (buttons, navigation links)
- Accent graphics: SVG-based mesh gradients for technical diagrams

### **Typography System**
**Primary Font Family:** Inter
- Navigation: Inter Regular (400)
- Logo: Inter Bold (700) for "APM v0.4"
- Body text: Inter Regular throughout most sections

**Hero Section Font:** Instrumental Sans
- Titles and subtitles in Hero/About carousel sections
- Creates visual distinction for primary content area

**Hierarchy:**
- H1: Hero titles (Instrumental Sans, large scale)
- H2: Section headers (Inter Bold)
- Body: Inter Regular with appropriate line-height for readability

### **Spacing & Layout Grid**
**Card Design Pattern:**
- **Border radius**: `20px` (consistent across all cards AND header for seamless scroll integration)
- **Card width**: Centered with generous black void margins on sides
- **Mobile responsive**: Maintains floating card effect with minimal side spacing

**Layout Structure:**
- **Desktop**: Cards centered with substantial side margins (~15-20% each side)
- **Tablet**: Reduced side margins (~10-12% each side) 
- **Mobile**: Minimal side margins (~5-8% each side) maintaining floating aesthetic
- Header outline perfectly matches card border radius for scroll transition effect

**Spacing Scale:**
- Base unit: `8px` or `16px` system for consistent spacing
- Section gaps: Large vertical spacing between floating cards
- Content padding: Generous internal card spacing

### **Component Architecture (Tailwind CSS v4)**
**Design Tokens Structure:**
```css
/* Tailwind CSS v4 custom properties */
@import "tailwindcss";

:root {
  /* Custom color palette */
  --color-void: 0 0 0; /* #000000 */
  --color-hero-bg: 24 24 24; /* #181818 */
  --color-hero-text: 166 166 166; /* #A6A6A6 */
  --color-features-bg: 174 159 138; /* #AE9F8A */
  --color-features-text: 255 255 255; /* #FFFFFF */
  
  /* Typography */
  --font-primary: 'Inter', system-ui, sans-serif;
  --font-hero: 'Instrumental Sans', system-ui, sans-serif;
  
  /* Spacing and layout */
  --border-radius-card: 20px; /* Matches header for scroll integration */
}
```

**Tailwind Utility Classes Pattern:**
**Card Component Pattern:**
- Border radius: `rounded-[20px]` (consistent header-card integration)
- Background colors: `bg-black`, `bg-[#181818]`, `bg-[#AE9F8A]`
- Text colors: `text-white`, `text-[#A6A6A6]`
- Layout: `mx-auto`, `max-w-7xl`, `w-[calc(100%-30%)]` (responsive margins)
- Spacing: `p-12`, `my-16` for consistent card spacing
- Perfect header-card integration on scroll

### **Global CSS Configurations (Tailwind CSS v4)**
**Base Styles:**
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

body {
  font-family: 'Inter', system-ui, sans-serif;
}
```

**Tailwind Utility Class Patterns:**
```html
<!-- Floating card pattern -->
<div class="bg-[#181818] rounded-[20px] p-12 my-16 mx-auto max-w-7xl w-[calc(100%-30%)] md:w-[calc(100%-20%)] lg:w-[calc(100%-15%)]">
  <!-- Card content -->
</div>

<!-- Features section white text with drop shadow -->
<p class="text-white drop-shadow-md">Content with shadow</p>

<!-- Header matching card border radius -->
<header class="bg-black rounded-[20px] text-white">
  <!-- Header content -->
</header>

<!-- Responsive card margins -->
<!-- Mobile: w-[calc(100%-10%)] -->
<!-- Tablet: w-[calc(100%-20%)] --> 
<!-- Desktop: w-[calc(100%-30%)] -->
```

**Key Tailwind Classes:**
- **Backgrounds**: `bg-black`, `bg-[#181818]`, `bg-[#AE9F8A]`
- **Text Colors**: `text-white`, `text-[#A6A6A6]`
- **Border Radius**: `rounded-[20px]` (consistent across all cards and header)
- **Spacing**: `p-12`, `my-16`, `mx-auto`
- **Responsive Width**: `w-[calc(100%-30%)]` with responsive variants
- **Typography**: `font-['Inter']`, `font-['Instrumental_Sans']`
- **Effects**: `drop-shadow-md` for Features section text

### **Interactions & Animations**
**Scroll Behavior:**
- Header outline visibility changes on scroll position (invisible against void, visible over cards)
- Features section full-height expansion on scroll
- Smooth transitions between content states
- Header outline perfectly aligns with card edges during scroll transitions

**Carousel Interactions:**
- Hero/About section directional navigation
- Smooth slide transitions maintaining card aesthetics

**Hover States:**
- Navigation links with subtle hover effects
- Interactive elements maintaining accessibility

**Animation Considerations:**
- Second About slide: Typing animation for chat conversation
- Token output animation for AI responses
- Smooth transitions preserving floating aesthetic

**Scroll Integration Mechanics:**
- Header `border-radius: 20px` exactly matches card corners
- On scroll, header outline becomes invisible against void background
- When positioned over cards, header outline perfectly aligns with card edges
- Creates seamless floating effect transition

---

## Navigation Header Component

### **General Design Description**
**Fixed-position floating header** that remains at the top of viewport while content scrolls beneath. Features **invisible outline effect** - header blends seamlessly into black void background, only becoming visually distinct when positioned over floating cards. Clean, minimal navigation with strategic scroll-to-section functionality and external GitHub integration.

### **Components Needed**
- **Logo/Brand**: "APM v0.4" text (Inter Bold)
- **Navigation Links**: 4 buttons ("About", "Features", "Contributors", "Documentation")
- **External Link**: GitHub Octocat icon
- **Container**: Fixed header wrapper with 20px border radius matching cards

### **Structure & Layout**
**Positioning & Behavior:**
```html
<!-- Fixed header with card-matching border radius -->
<header class="fixed top-0 left-0 right-0 z-50 bg-black rounded-[20px] px-8 py-4">
  <nav class="flex items-center justify-between max-w-7xl mx-auto">
    <!-- Logo -->
    <div class="text-white font-bold font-['Inter'] text-lg">APM v0.4</div>
    
    <!-- Navigation -->
    <div class="flex items-center space-x-8">
      <button class="nav-link">About</button>
      <button class="nav-link">Features</button>
      <button class="nav-link">Contributors</button>
      <button class="nav-link">Documentation</button>
      <a href="https://github.com/agentic-project-management" class="nav-link">
        <!-- GitHub Octocat SVG -->
      </a>
    </div>
  </nav>
</header>
```

**Layout Specifications:**
- **Position**: `fixed top-0` (stays at viewport top)
- **Z-index**: `z-50` (above all content)
- **Border Radius**: `rounded-[20px]` (matches floating cards exactly)
- **Spacing**: `px-8 py-4` internal padding, `space-x-8` between nav items

### **Color Palette**
- **Background**: `bg-black` (invisible against void background)
- **Logo Text**: `text-white font-bold` (Inter Bold, white)
- **Navigation Text**: `text-white` (Inter Regular, white)
- **Hover States**: `hover:bg-white/10` (subtle white glow effect)

### **CSS Configurations (Tailwind)**
**Primary Hover Effect (Subtle Background Glow):**
```html
<button class="text-white font-['Inter'] px-4 py-2 rounded-lg transition-all duration-300 hover:bg-white/10 hover:backdrop-blur-sm">
  About
</button>
```

**Fallback Hover Effect (Animated Underline):**
```html
<button class="text-white font-['Inter'] relative group px-4 py-2">
  About
  <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-white transition-all duration-300 group-hover:w-full"></span>
</button>
```

**Complete Navigation Classes:**
- **Logo**: `text-white font-bold font-['Inter'] text-lg`
- **Navigation Container**: `flex items-center space-x-8`
- **Nav Links**: `text-white font-['Inter'] px-4 py-2 rounded-lg transition-all duration-300 hover:bg-white/10 hover:backdrop-blur-sm`

### **Functionality & Interactivity**

**Scroll Behaviors:**
- **About Button**: `scrollTo(hero-section)` + `carousel.slideTo(1)` (switches to first about slide)
- **Features Button**: `scrollTo(features-section)` (positions entire section in view)
- **Contributors Button**: `scrollTo(contributors-section)` (scrolls to contributors area)
- **Documentation Button**: **No functionality** (dummy button with same hover effects)
- **GitHub Icon**: `window.open('https://github.com/agentic-project-management')` (external link)

**Invisible Outline Mechanics:**
- Header background matches void (`bg-black`) creating seamless integration
- Header becomes visually distinct only when overlaying floating cards
- 20px border radius aligns perfectly with card corners during scroll transitions

**Hover Effects:**
- **Primary**: Subtle background glow with backdrop blur effect
- **Fallback**: Animated underline expanding from left to right
- **Timing**: `transition-all duration-300` for smooth interactions

### **Component Connections**
- **Hero Section Integration**: About button triggers carousel slide change
- **Section Navigation**: Smooth scroll-to-section functionality for Features and Contributors
- **External Integration**: Direct GitHub repository linking via Octocat icon
- **Scroll Context**: Header remains fixed while content scrolls beneath, maintaining consistent navigation access

---

## Hero Section Component

### **General Design Description**
**Primary floating card** featuring Instrumental Sans typography with integrated **network diagram SVG graphic**. The card acts as a **fixed container** with **internal carousel functionality** - content slides horizontally while the card dimensions and position remain constant. Professional presentation with **slightly delayed fade-in graphic animations** on page load for optimal visual impact.

### **Components Needed**
- **Title**: "Agentic Project Management" (Instrumental Sans, large scale)
- **Subtitle**: "Manage complex projects..." (Instrumental Sans, smaller scale)
- **SVG Network Diagram**: High-quality mesh gradient technical illustration
- **Carousel Container**: Internal slide mechanism with fixed card boundaries
- **Navigation Controls**: Chunky, minimal directional arrows (conditionally visible)

### **Structure & Layout**
```html
<section class="bg-[#181818] rounded-[20px] p-12 my-16 mx-auto max-w-7xl w-[calc(100%-30%)]">
  <!-- Fixed card container -->
  <div class="carousel-container overflow-hidden">
    <!-- Sliding content wrapper -->
    <div class="carousel-slides flex transition-transform duration-500 ease-in-out">
      
      <!-- Slide 1: Hero Content -->
      <div class="slide w-full flex-shrink-0">
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
          <!-- Left: Text Content -->
          <div class="text-content">
            <h1 class="text-4xl lg:text-5xl font-bold font-['Instrumental_Sans'] text-[#A6A6A6] mb-4">
              Agentic Project Management
            </h1>
            <p class="text-lg font-['Instrumental_Sans'] text-[#A6A6A6]">
              Manage complex projects with a team of AI assistants, smoothly and efficiently.
            </p>
          </div>
          
          <!-- Right: SVG Graphic -->
          <div class="graphic-container">
            <img src="/hero-network-diagram.svg" 
                 alt="APM Network Diagram" 
                 class="w-full h-auto opacity-0 animate-fade-in-delayed"
                 style="image-rendering: -webkit-optimize-contrast; image-rendering: crisp-edges;" />
          </div>
        </div>
      </div>
      
      <!-- Slide 2: About Content -->
      <div class="slide w-full flex-shrink-0">
        <!-- Chat conversation layout (to be detailed) -->
      </div>
      
    </div>
  </div>
  
  <!-- Conditional Navigation -->
  <div class="carousel-nav flex justify-between items-center mt-8">
    <button class="hero-nav-arrow" disabled>
      <svg class="w-5 h-5" viewBox="0 0 20 20" fill="currentColor">
        <path fill-rule="evenodd" d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z" clip-rule="evenodd" />
      </svg>
    </button>
    <button class="hero-nav-arrow">
      <svg class="w-5 h-5" viewBox="0 0 20 20" fill="currentColor">
        <path fill-rule="evenodd" d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z" clip-rule="evenodd" />
      </svg>
    </button>
  </div>
</section>
```

**Container Specifications:**
- **Card**: `bg-[#181818] rounded-[20px] p-12` (matches global card pattern)
- **Layout**: `grid grid-cols-1 lg:grid-cols-2 gap-8` (responsive two-column)
- **Carousel**: `overflow-hidden` container with `flex` sliding mechanism

### **Color Palette**
- **Background**: `bg-[#181818]` (Hero section card background)
- **Text Colors**: `text-[#A6A6A6]` (title, subtitle, navigation arrows)
- **Navigation Arrows**: `text-[#A6A6A6]` with outline hover effects

### **CSS Configurations (Tailwind)**
**SVG Quality Preservation:**
```html
<img src="/hero-network-diagram.svg" 
     alt="APM Network Diagram" 
     class="w-full h-auto opacity-0 animate-fade-in-delayed"
     style="image-rendering: -webkit-optimize-contrast; image-rendering: crisp-edges;" />
```

**Animation Specifications:**
```css
/* Slightly delayed fade-in for SVG */
@keyframes fade-in-delayed {
  0% { opacity: 0; transform: translateY(20px); }
  20% { opacity: 0; transform: translateY(20px); } /* Delay */
  100% { opacity: 1; transform: translateY(0); }
}

.animate-fade-in-delayed {
  animation: fade-in-delayed 1.5s ease-out forwards;
}
```

**Carousel Transition (Basic Slide):**
```css
.carousel-slides {
  transition: transform 500ms ease-in-out;
  /* TODO: Consider experimenting with motion blur or other motion-related animations for enhanced transitions */
}
```

**Navigation Arrow Styling (Chunky & Minimal):**
```html
<button class="hero-nav-arrow w-10 h-10 rounded-full border-2 border-[#A6A6A6] text-[#A6A6A6] flex items-center justify-center transition-all duration-300 hover:border-white hover:text-white focus:border-white focus:text-white disabled:opacity-30 disabled:cursor-not-allowed">
  <!-- Arrow SVG -->
</button>
```

**Typography Classes:**
- **Title**: `text-4xl lg:text-5xl font-bold font-['Instrumental_Sans'] text-[#A6A6A6]`
- **Subtitle**: `text-lg font-['Instrumental_Sans'] text-[#A6A6A6]`

### **Functionality & Interactivity**

**Carousel Mechanics:**
- **Internal Sliding**: Content slides within fixed card boundaries
- **Smooth Transitions**: Basic horizontal slide with `ease-in-out` timing
- **Conditional Navigation**: Arrows appear/disappear based on slide availability
- **Navigation Integration**: About button from header triggers slide transition

**SVG Animation Behavior:**
- **Timing**: Slightly delayed start (0.3s) for full animation visibility
- **Quality**: Vector preservation with crisp rendering for all screen densities
- **Performance**: Optimized loading and smooth fade-in presentation

**Navigation Arrow Behavior:**
- **Style**: Chunky outline design with small physical footprint
- **Hover/Focus**: Border and text color transition to white
- **Disabled State**: Reduced opacity when no navigation available
- **Theme Consistency**: Matches Hero section color palette (#A6A6A6)

### **Component Connections**
- **Header Integration**: About button triggers carousel slide navigation
- **Fixed Container**: Card dimensions remain constant during content transitions
- **Responsive Layout**: Two-column design adapts to single column on mobile while maintaining carousel functionality

---

## Features Section Component

### **General Design Description**
**Large floating card** with warm beige background (#AE9F8A) featuring **asymmetric two-part layout**. Top section (~35% height) showcases IDE integration with icons and screenshot. Bottom section (~65% height) contains **interactive pill tab navigation** with feature-specific content slides. All transitions maintain consistency with Hero section mechanics for cohesive user experience. Active pill tabs create **"hole" effect** showing section background through navigation menu.

### **Components Needed**
**Top Half (IDE Integration - Smaller):**
- Header: "Integrates Seamlessly with Your Favorite AI IDEs"
- Descriptive text with white drop shadow
- Three IDE SVG icons (Windsurf, Cursor, VS Code)
- APM chat screenshot (SVG prioritized, CSS artificial screenshot fallback)

**Bottom Half (Feature Showcase - Larger):**
- Section header: "Explore APM's core features that offer solutions to fundamental LLM challenges"
- Pill tab navigation with 4 tabs (Multi-Agent Orchestration, Implementation Plan, Dynamic Memory Bank, Handover Procedure)
- Sliding content container with two-column layouts per tab
- Four unique SVG graphics with fade-in animations (one per tab)

### **Structure & Layout**
```html
<section class="bg-[#AE9F8A] rounded-[20px] p-12 my-16 mx-auto max-w-7xl w-[calc(100%-30%)] md:w-[calc(100%-20%)] sm:w-[calc(100%-10%)]">
  
  <!-- Top Half: IDE Integration (~35% height) -->
  <div class="top-section mb-16">
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
      <!-- Left: Content -->
      <div class="text-content">
        <h2 class="text-3xl lg:text-4xl font-bold font-['Inter'] text-white drop-shadow-md mb-4">
          Integrates Seamlessly with Your Favorite AI IDEs
        </h2>
        <p class="text-lg font-['Inter'] text-white drop-shadow-sm mb-6">
          APM functions directly where your code lives to minimize error margins, reduce context drift and streamline multi-agent execution.
        </p>
        <!-- IDE Icons -->
        <div class="flex space-x-6">
          <img src="/icons/windsurf-icon.svg" alt="Windsurf" class="w-12 h-12 opacity-90" />
          <img src="/icons/cursor-icon.svg" alt="Cursor" class="w-12 h-12 opacity-90" />
          <img src="/icons/vscode-icon.svg" alt="VS Code" class="w-12 h-12 opacity-90" />
        </div>
      </div>
      
      <!-- Right: Screenshot -->
      <div class="screenshot-container">
        <!-- Primary: SVG Screenshot -->
        <img src="/screenshots/apm-chat-screenshot.svg" 
             alt="APM Chat Interface" 
             class="w-full h-auto rounded-lg"
             style="image-rendering: -webkit-optimize-contrast; image-rendering: crisp-edges;" />
        
        <!-- Fallback: CSS Artificial Screenshot -->
        <!-- <div class="artificial-screenshot bg-gray-800 rounded-lg p-4 text-green-400 font-mono text-sm">
          Styled chat interface fallback
        </div> -->
      </div>
    </div>
  </div>
  
  <!-- Bottom Half: Feature Showcase (~65% height) -->
  <div class="bottom-section">
    <h2 class="text-3xl lg:text-4xl font-bold font-['Inter'] text-white drop-shadow-md text-center mb-8">
      Explore APM's core features that offer solutions to fundamental LLM challenges.
    </h2>
    
    <!-- Pill Tab Navigation -->
    <div class="pill-nav flex justify-center mb-12">
      <div class="bg-black rounded-full p-2 flex flex-wrap sm:flex-nowrap gap-1">
        <button class="pill-tab px-4 sm:px-6 py-3 rounded-full text-white font-['Inter'] text-xs sm:text-sm transition-all duration-300 hover:bg-white/10 data-[active]:bg-[#AE9F8A] data-[active]:text-black" data-active>
          Multi-Agent Orchestration
        </button>
        <button class="pill-tab px-4 sm:px-6 py-3 rounded-full text-white font-['Inter'] text-xs sm:text-sm transition-all duration-300 hover:bg-white/10">
          Implementation Plan
        </button>
        <button class="pill-tab px-4 sm:px-6 py-3 rounded-full text-white font-['Inter'] text-xs sm:text-sm transition-all duration-300 hover:bg-white/10">
          Dynamic Memory Bank
        </button>
        <button class="pill-tab px-4 sm:px-6 py-3 rounded-full text-white font-['Inter'] text-xs sm:text-sm transition-all duration-300 hover:bg-white/10">
          Handover Procedure
        </button>
      </div>
    </div>
    
    <!-- Sliding Content Container -->
    <div class="feature-carousel overflow-hidden">
      <div class="feature-slides flex transition-transform duration-500 ease-in-out">
        
        <!-- Feature Slide 1: Multi-Agent Orchestration -->
        <div class="feature-slide w-full flex-shrink-0">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
            <!-- Left: Description -->
            <div class="text-content order-1">
              <p class="text-lg font-['Inter'] text-white drop-shadow-sm">
                APM uses a central orchestrator Agent that manages multiple Specialized Agents in order to share the project workload, regulating model hallucinations.
              </p>
            </div>
            
            <!-- Right: Graphic with Animation -->
            <div class="graphic-container order-2 lg:order-2">
              <img src="/graphics/multi-agent-diagram.svg" 
                   alt="Multi-Agent Architecture" 
                   class="w-full h-auto opacity-0 animate-fade-in-delayed"
                   style="image-rendering: crisp-edges;" />
            </div>
          </div>
        </div>
        
        <!-- Feature Slide 2: Implementation Plan -->
        <div class="feature-slide w-full flex-shrink-0">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
            <div class="text-content order-1">
              <p class="text-lg font-['Inter'] text-white drop-shadow-sm">
                [Implementation Plan description text]
              </p>
            </div>
            <div class="graphic-container order-2">
              <img src="/graphics/implementation-plan-diagram.svg" 
                   alt="Implementation Plan" 
                   class="w-full h-auto opacity-0 animate-fade-in-delayed"
                   style="image-rendering: crisp-edges;" />
            </div>
          </div>
        </div>
        
        <!-- Feature Slide 3: Dynamic Memory Bank -->
        <div class="feature-slide w-full flex-shrink-0">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
            <div class="text-content order-1">
              <p class="text-lg font-['Inter'] text-white drop-shadow-sm">
                [Dynamic Memory Bank description text]
              </p>
            </div>
            <div class="graphic-container order-2">
              <img src="/graphics/dynamic-memory-diagram.svg" 
                   alt="Dynamic Memory Bank" 
                   class="w-full h-auto opacity-0 animate-fade-in-delayed"
                   style="image-rendering: crisp-edges;" />
            </div>
          </div>
        </div>
        
        <!-- Feature Slide 4: Handover Procedure -->
        <div class="feature-slide w-full flex-shrink-0">
          <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
            <div class="text-content order-1">
              <p class="text-lg font-['Inter'] text-white drop-shadow-sm">
                [Handover Procedure description text]
              </p>
            </div>
            <div class="graphic-container order-2">
              <img src="/graphics/handover-procedure-diagram.svg" 
                   alt="Handover Procedure" 
                   class="w-full h-auto opacity-0 animate-fade-in-delayed"
                   style="image-rendering: crisp-edges;" />
            </div>
          </div>
        </div>
        
      </div>
    </div>
  </div>
</section>
```

### **Color Palette**
- **Background**: `bg-[#AE9F8A]` (warm beige Features section background)
- **Text**: `text-white drop-shadow-md` (white text with drop shadow for readability)
- **Pill Navigation**: `bg-black` container with individual pill styling
- **Active Pill**: `bg-[#AE9F8A] text-black` ("hole" effect showing section background)
- **Inactive Pills**: `text-white hover:bg-white/10` (subtle hover glow)

### **CSS Configurations (Tailwind)**
**Height Distribution:**
- **Top Section**: ~35% with `mb-16` separation
- **Bottom Section**: ~65% with larger content area

**Pill Tab Navigation ("Hole" Effect):**
```html
<!-- Active state creates visual "hole" in black navigation -->
<button class="pill-tab data-[active]:bg-[#AE9F8A] data-[active]:text-black">
  Multi-Agent Orchestration
</button>
```

**SVG Quality & Animation:**
```html
<!-- Four unique graphics with identical animation timing -->
<img src="/graphics/[feature]-diagram.svg" 
     alt="[Feature] Diagram" 
     class="w-full h-auto opacity-0 animate-fade-in-delayed"
     style="image-rendering: crisp-edges;" />
```

**Responsive Design:**
```html
<!-- Mobile: Single column with description top, graphics bottom -->
<div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-center">
  <div class="text-content order-1"></div>  <!-- Always top on mobile -->
  <div class="graphic-container order-2"></div>  <!-- Always bottom on mobile -->
</div>

<!-- Pill navigation responsive -->
<div class="flex flex-wrap sm:flex-nowrap gap-1">
  <button class="px-4 sm:px-6 py-3 text-xs sm:text-sm">Tab</button>
</div>
```

### **Functionality & Interactivity**

**Pill Tab Behavior:**
- **Active State**: "Hole" effect showing #AE9F8A background with black text
- **Hover State**: Subtle white/10 background glow for inactive tabs
- **Transition**: `duration-300` for smooth state changes
- **Mobile Adaptation**: Flexible wrapping with smaller text and padding

**Carousel Mechanics:**
- **Slide Transitions**: Identical to Hero section (`duration-500 ease-in-out`)
- **Content Structure**: Consistent two-column grid across all 4 feature tabs
- **Animation Timing**: SVG graphics use same delayed fade-in as Hero section

**Asset Organization:**
- **Icons**: `/icons/` directory (windsurf-icon.svg, cursor-icon.svg, vscode-icon.svg)
- **Screenshots**: `/screenshots/` directory (apm-chat-screenshot.svg)
- **Graphics**: `/graphics/` directory (4 unique SVGs for each feature tab)

### **Component Connections**
- **Header Navigation**: Features button scrolls to full section visibility
- **Scroll Behavior**: Section expands to full viewport height when user scrolls into bottom half
- **Animation Consistency**: All transitions and fade-ins match Hero section timing
- **Responsive Integration**: Mobile layout maintains floating card aesthetic with adapted navigation

---

## Contributors Section Component

### **General Design Description**
**Individual floating glass cards** positioned on pure black void background (no container card). Each contributor gets a **small glassmorphism card** with GitHub profile data arranged in responsive grid matching the width of Hero/Features cards above. Clean, minimal design with **Apple Watch-style bubble hover effects** and direct GitHub profile linking.

### **Components Needed**
- **Section Text**: Start/end text markers on black background
- **Grid Container**: Responsive layout matching card widths above
- **Individual Contributor Cards**: Glass effect with GitHub avatar, username, commit count
- **Interactive Effects**: Scale animation with slow return transition

### **Structure & Layout**
```html
<section class="contributors-section py-16 bg-black">
  <!-- Section Start Text -->
  <div class="max-w-7xl mx-auto w-[calc(100%-30%)] mb-8">
    <h2 class="text-white font-['Inter'] font-bold text-2xl text-center">
      Contributors
    </h2>
    <p class="text-white/70 font-['Inter'] text-center mt-2">
      Meet the team building APM
    </p>
  </div>
  
  <!-- Contributors Grid -->
  <div class="contributors-grid max-w-7xl mx-auto w-[calc(100%-30%)]">
    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-6">
      
      <!-- Individual Contributor Card -->
      <a href="https://github.com/username" target="_blank" class="contributor-card group cursor-pointer">
        <div class="glass-card bg-white/10 backdrop-blur-md border border-white/20 rounded-2xl p-6 transition-all duration-300 ease-out hover:scale-105 hover:bg-white/15">
          
          <!-- GitHub Avatar -->
          <div class="avatar-container mb-4 flex justify-center">
            <img src="https://github.com/username.png" 
                 alt="Username" 
                 class="w-16 h-16 rounded-full border-2 border-white/30 group-hover:border-white/50 transition-colors duration-300" />
          </div>
          
          <!-- Username -->
          <h3 class="text-white font-['Inter'] font-semibold text-lg text-center mb-2">
            username
          </h3>
          
          <!-- Commit Count -->
          <p class="text-white/80 font-['Inter'] text-sm text-center">
            <span class="font-bold">142</span> commits
          </p>
          
        </div>
      </a>
      
      <!-- Additional contributor cards... -->
    </div>
  </div>
  
  <!-- Section End Text -->
  <div class="max-w-7xl mx-auto w-[calc(100%-30%)] mt-8">
    <p class="text-white/50 font-['Inter'] text-sm text-center">
      Join us on GitHub
    </p>
  </div>
</section>
```

### **Color Palette**
- **Background**: `bg-black` (pure void, no container card)
- **Glass Cards**: `bg-white/10` with `backdrop-blur-md` and `border-white/20`
- **Text Colors**: `text-white` (usernames), `text-white/80` (commit counts), `text-white/70` (subtitle), `text-white/50` (end text)
- **Hover States**: `hover:bg-white/15` and `hover:border-white/50`

### **CSS Configurations (Tailwind) - TO BE TESTED**
**Grid Layout:**
```html
<!-- Responsive grid - TO BE TESTED -->
<div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-6">
```

**Glassmorphism Effect - TO BE TESTED:**
```html
<div class="bg-white/10 backdrop-blur-md border border-white/20 rounded-2xl p-6">
```

**Apple Watch Bubble Hover Effect:**
```html
<!-- Scale with slow return transition -->
<div class="transition-all duration-300 ease-out hover:scale-105">
```

**Avatar Styling - TO BE TESTED:**
```html
<img class="w-16 h-16 rounded-full border-2 border-white/30 group-hover:border-white/50" />
```

**Width Matching:**
```html
<!-- Matches Hero/Features card widths exactly -->
<div class="max-w-7xl mx-auto w-[calc(100%-30%)]">
```

### **Functionality & Interactivity**

**Hover Effects (Apple Watch Style):**
- **Scale**: `hover:scale-105` (5% increase)
- **Transition**: `duration-300 ease-out` for smooth scale and slow return
- **Glass Enhancement**: `hover:bg-white/15` for subtle brightness increase
- **Avatar Border**: `hover:border-white/50` for enhanced definition
- **No Shadows**: Removed since background is pitch black
- **No Rotation**: Clean scale-only animation

**Click Behavior:**
- **External Link**: `href="https://github.com/username" target="_blank"`
- **Full Card Clickable**: Entire card area acts as link to GitHub profile

**Data Display (Minimal for API Efficiency):**
- **GitHub Avatar**: Fetched from `https://github.com/username.png`
- **Username**: GitHub username only
- **Commit Count**: Simple numerical count ("142 commits")
- **No Additional Stats**: No role, followers, or other data to reduce GitHub Actions overhead

### **Section Text Styling - TO BE REFINED DURING IMPLEMENTATION**
**Section Markers:**
- **Start**: "Contributors" title with "Meet the team building APM" subtitle
- **End**: "Join us on GitHub" call-to-action
- **Positioning**: Centered alignment with same width as contributor grid
- **Typography**: Inter font family with varying opacity levels for hierarchy

### **Component Connections**
- **Width Alignment**: Matches Hero and Features sections exactly for visual consistency
- **Void Background**: Seamless integration with black background between sections
- **GitHub Integration**: Direct linking to contributor profiles via GitHub Actions data fetching
- **Responsive Design**: Grid adapts from 2 columns (mobile) to 5 columns (desktop) while maintaining floating aesthetic

---

## Asset Requirements

### **Icons & Graphics**
**IDE Platform Icons (`/icons/` directory):**
- `windsurf-icon.svg` - Windsurf AI IDE platform icon
- `cursor-icon.svg` - Cursor AI IDE platform icon  
- `vscode-icon.svg` - Visual Studio Code platform icon
- `github-octocat.svg` - GitHub Octocat icon for navigation header

**Technical Specifications:**
- **Format**: SVG for crisp rendering at all screen densities
- **Size**: Optimized for `w-12 h-12` display (48×48px base)
- **Style**: Clean, minimal icons matching professional aesthetic
- **Rendering**: `image-rendering: crisp-edges` for optimal quality

### **Background Elements**
**Hero Section Network Diagram (`/graphics/` directory):**
- `hero-network-diagram.svg` - Main APM workflow visualization with mesh gradient effects
  - **Features**: 3 core APM concepts (handovers, multi-agent coordination, memory management)
  - **Style**: Professional technical illustration with gradient mesh effects
  - **Animation**: Fade-in with 0.3s delay on page load
  - **Quality**: Vector-based for perfect scaling across all devices

### **Interactive Graphics**
**Feature Showcase Diagrams (`/graphics/` directory):**
- `multi-agent-diagram.svg` - Multi-Agent Orchestration architecture visualization
- `implementation-plan-diagram.svg` - Implementation Plan structure and workflow  
- `dynamic-memory-diagram.svg` - Dynamic Memory Bank system illustration
- `handover-procedure-diagram.svg` - Handover Procedure process flow

**Technical Specifications:**
- **Format**: SVG with complex mesh gradients and technical styling
- **Animation**: Each graphic uses `animate-fade-in-delayed` (0.3s delay) when tab becomes active
- **Quality**: `image-rendering: crisp-edges` for sharp technical details
- **Responsive**: `w-full h-auto` for flexible scaling while maintaining aspect ratios

### **Screenshots & Interface Elements**
**APM Chat Interface (`/screenshots/` directory):**
- `apm-chat-screenshot.svg` - APM chat session interface example
  - **Primary Option**: SVG export from Figma for perfect quality
  - **Fallback Option**: CSS-styled artificial chat interface if SVG quality insufficient
  - **Content**: Example conversation showing Manager Agent initialization
  - **Style**: Dark theme matching professional development environment

**Implementation Approach:**
```html
<!-- Primary: SVG Screenshot -->
<img src="/screenshots/apm-chat-screenshot.svg" 
     alt="APM Chat Interface" 
     class="w-full h-auto rounded-lg"
     style="image-rendering: -webkit-optimize-contrast; image-rendering: crisp-edges;" />

<!-- Fallback: CSS Artificial Screenshot -->
<div class="artificial-screenshot bg-gray-800 rounded-lg p-4 text-green-400 font-mono text-sm">
  <!-- Styled chat interface fallback -->
</div>
```

### **Branding Elements**
**Logo & Text Elements:**
- **APM v0.4 Logo**: Text-based logo using Inter Bold font (no separate graphic file needed)
- **Typography**: Inter and Instrumental Sans fonts (web fonts)

**GitHub Integration Elements:**
- **Contributor Avatars**: Fetched dynamically from `https://github.com/username.png`
- **External Links**: Direct integration with GitHub profiles (no local assets required)

### **Asset Organization Structure**
```
website/public/
├── icons/
│   ├── windsurf-icon.svg
│   ├── cursor-icon.svg
│   ├── vscode-icon.svg
│   └── github-octocat.svg
├── graphics/
│   ├── hero-network-diagram.svg
│   ├── multi-agent-diagram.svg
│   ├── implementation-plan-diagram.svg
│   ├── dynamic-memory-diagram.svg
│   └── handover-procedure-diagram.svg
└── screenshots/
    └── apm-chat-screenshot.svg
```

### **Quality Standards**
**SVG Optimization:**
- **Vector Preservation**: All graphics maintain vector quality for unlimited scaling
- **File Size**: Optimized for web delivery while preserving visual fidelity
- **Compatibility**: Cross-browser SVG support with proper fallbacks
- **Accessibility**: Appropriate alt text and semantic markup for all graphics

**Animation Integration:**
- **Consistent Timing**: All graphics use identical fade-in animation (1.5s duration, 0.3s delay)
- **Performance**: Efficient CSS animations without heavy JavaScript dependencies
- **Quality Preservation**: Animations maintain crisp rendering throughout transitions

---

## Responsive Design Specifications

### **Breakpoint Strategy**
**Tailwind CSS Responsive System:**
- **Mobile**: `default` (< 640px) - Single column layouts, compact spacing
- **Tablet**: `md:` (≥ 768px) - Transitional layouts, moderate spacing  
- **Desktop**: `lg:` (≥ 1024px) - Full two-column layouts, optimal spacing
- **Large Desktop**: `xl:` (≥ 1280px) - Enhanced grid layouts, maximum content width

**Global Card Width System:**
```css
/* Consistent floating card margins across all sections */
.floating-card {
  width: calc(100% - 10%);  /* Mobile: 5% margins each side */
  width: calc(100% - 20%);  /* md: 10% margins each side */
  width: calc(100% - 30%);  /* lg: 15% margins each side */
}
```

### **Mobile-First Considerations**
**Layout Adaptations:**
- **Two-Column to Single-Column**: All Hero and Features section content stacks vertically
- **Content Order**: Description always appears above graphics on mobile (`order-1`, `order-2`)
- **Navigation Adaptations**: Pill tabs wrap with reduced padding (`flex-wrap`, `px-4 py-3`)
- **Typography Scaling**: Responsive text sizes (`text-3xl lg:text-4xl`, `text-base lg:text-lg`)

**Touch Interactions:**
- **Contributors Cards**: Hover effects adapt to touch with appropriate touch targets
- **Navigation**: Touch-friendly button sizes maintained across all interactive elements
- **Carousel Controls**: Adequately sized navigation arrows for mobile interaction

**Performance Considerations:**
- **SVG Optimization**: Vector graphics scale efficiently without quality loss
- **Animation Performance**: CSS transforms and opacity changes for smooth mobile performance
- **Lazy Loading**: Consider lazy loading for graphics below the fold

### **Cross-Browser Compatibility**
**SVG Rendering:**
- **WebKit**: `image-rendering: -webkit-optimize-contrast` for sharp edges
- **Standard**: `image-rendering: crisp-edges` fallback
- **Compatibility**: SVG support with PNG fallbacks where necessary

**CSS Features:**
- **Backdrop Blur**: `backdrop-filter: blur()` with fallbacks for unsupported browsers
- **Custom Properties**: CSS variables with fallback values
- **Grid Layouts**: Flexbox fallbacks for older browser support

### **Animation & Effect Consistency**
**Global Animation Standards:**
- **Duration**: `duration-300` for hover effects, `duration-500` for carousel transitions
- **Easing**: `ease-out` for scale effects, `ease-in-out` for slides
- **SVG Fade-ins**: Consistent `1.5s` duration with `0.3s` delay across all graphics

**Hover Effect Consistency:**
- **Scale Effects**: `hover:scale-105` for interactive cards (Contributors, Hero navigation)
- **Background Glows**: `hover:bg-white/10` for navigation elements
- **Transition Timing**: `transition-all duration-300` for responsive hover feedback
- **Apple Watch Style**: Slow return to original state with `ease-out` timing

**Carousel Mechanics Consistency:**
- **Hero Section**: `transform: translateX()` with `duration-500 ease-in-out`
- **Features Section**: Identical transition timing and mechanics for visual consistency
- **Navigation**: Consistent directional controls with same styling patterns

### **Component-Specific Responsive Behavior**
**Navigation Header:**
- **Fixed Position**: Maintained across all devices with consistent z-index
- **Border Radius**: 20px preserved on all screen sizes for card alignment
- **Interactive Elements**: Touch-friendly sizing with adequate spacing

**Hero Section:**
- **Carousel**: Functional across all devices with adapted navigation controls
- **Grid Layout**: `grid-cols-1 lg:grid-cols-2` with proper content ordering
- **Typography**: Instrumental Sans scales appropriately (`text-4xl lg:text-5xl`)

**Features Section:**
- **Asymmetric Layout**: Height distribution maintained proportionally across devices
- **Pill Navigation**: `flex-wrap sm:flex-nowrap` with responsive text sizing
- **Content Slides**: Two-column desktop to single-column mobile with consistent ordering

**Contributors Section:**
- **Grid Adaptation**: `grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5`
- **Glass Effects**: Backdrop blur maintained across supported devices
- **Card Proportions**: Glassmorphism cards scale proportionally while maintaining readability

### **Accessibility Considerations**
**Visual Accessibility:**
- **Color Contrast**: White text on dark backgrounds meets WCAG guidelines
- **Focus States**: Keyboard navigation support with visible focus indicators
- **Motion Reduction**: Respect `prefers-reduced-motion` for users with motion sensitivities

**Screen Reader Support:**
- **Semantic HTML**: Proper heading hierarchy and landmark elements
- **Alt Text**: Descriptive alt text for all SVG graphics and images
- **ARIA Labels**: Appropriate labels for interactive carousel controls

**Touch Accessibility:**
- **Target Sizes**: Minimum 44px touch targets for mobile interaction
- **Spacing**: Adequate spacing between interactive elements
- **Visual Feedback**: Clear hover and focus states for all interactive elements

---

## Implementation Notes

### **Development Priorities**
**Phase 1: Foundation & Core Structure**
1. **Global CSS Setup**: Implement Tailwind CSS v4 with custom properties and design tokens
2. **Navigation Header**: Fixed positioning with invisible outline mechanics and scroll integration
3. **Hero Section**: Carousel functionality with SVG quality preservation and fade-in animations

**Phase 2: Interactive Components**
4. **Features Section**: Pill tab navigation with slide transitions and responsive layout adaptation
5. **Contributors Section**: GitHub API integration with glassmorphism cards and Apple Watch hover effects
6. **Cross-Component Integration**: Scroll behaviors, navigation linking, and animation consistency

**Phase 3: Polish & Optimization**
7. **Responsive Refinement**: Mobile adaptations and cross-browser compatibility testing
8. **Performance Optimization**: SVG loading, animation performance, and asset optimization
9. **Accessibility Implementation**: ARIA labels, keyboard navigation, and motion preference support

### **Technical Considerations**
**Performance Requirements:**
- **SVG Optimization**: Vector graphics with `image-rendering: crisp-edges` for sharp technical diagrams
- **Animation Efficiency**: CSS-only animations using transforms and opacity for smooth 60fps performance
- **Asset Loading**: Efficient SVG delivery with proper caching headers and compression
- **GitHub API**: Minimal data fetching (avatar, username, commits) to reduce API overhead

**Accessibility Considerations:**
- **WCAG 2.1 AA Compliance**: High contrast ratios with white text on dark backgrounds
- **Keyboard Navigation**: Full carousel and pill tab navigation via keyboard
- **Screen Reader Support**: Semantic HTML structure with proper heading hierarchy
- **Motion Preferences**: Respect `prefers-reduced-motion` for fade-in and scale animations

**SEO Considerations:**
- **Semantic Structure**: Proper HTML5 landmarks and heading hierarchy
- **Meta Optimization**: Open Graph and Twitter Card integration for social sharing
- **Performance Metrics**: Core Web Vitals optimization with efficient loading strategies
- **Progressive Enhancement**: Base functionality without JavaScript dependencies

### **Critical Implementation Details**
**Border Radius Consistency:**
- **20px border radius** must be maintained across ALL cards and header for seamless scroll integration
- Header outline becomes invisible against void background through precise alignment

**Animation Timing Standards:**
- **SVG Fade-ins**: `1.5s duration` with `0.3s delay` across Hero and Features sections
- **Carousel Transitions**: `500ms ease-in-out` for both Hero and Features consistency
- **Hover Effects**: `300ms ease-out` for Apple Watch-style bubble effects
- **Scale Returns**: Slow return timing with `ease-out` for satisfying interaction feedback

**Color Palette Precision:**
- **Exact Color Values**: `#000000` (void), `#181818` (Hero), `#AE9F8A` (Features), `#A6A6A6` (Hero text)
- **Opacity Consistency**: `white/10`, `white/15`, `white/20` for glassmorphism hierarchy
- **Drop Shadow Requirements**: White text on Features section requires `drop-shadow-md` for readability

**Quality Preservation Techniques:**
```css
/* SVG quality preservation across all graphics */
img[src$=".svg"] {
  image-rendering: -webkit-optimize-contrast;
  image-rendering: crisp-edges;
}

/* Glassmorphism consistency */
.glass-card {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(16px);
  border: 1px solid rgba(255, 255, 255, 0.2);
}
```

### **Future Scalability**
**Documentation Integration Preparation:**
- **Modular Component Structure**: Components designed for easy expansion and documentation page integration
- **Consistent Design Patterns**: Floating card system can extend to documentation sections
- **Navigation Extensibility**: Header navigation ready for documentation sub-page routing
- **Asset Organization**: Scalable directory structure (`/icons/`, `/graphics/`, `/screenshots/`)

**Content Management Considerations:**
- **GitHub Actions Integration**: Automated contributor data updates with minimal API calls
- **SVG Asset Pipeline**: Organized asset workflow for future graphic additions
- **Typography Scalability**: Inter and Instrumental Sans font system supports content expansion
- **Component Reusability**: Glass cards and floating elements can be reused for documentation features

**Technical Debt Prevention:**
- **CSS Custom Properties**: Centralized design tokens prevent inconsistencies during expansion
- **Consistent Animation Libraries**: Standardized transition timing enables seamless feature additions
- **Responsive Pattern Consistency**: Established breakpoint system scales to new components
- **Accessibility Foundation**: WCAG compliance foundation supports feature growth without accessibility debt

**Performance Scalability:**
- **Efficient Asset Loading**: SVG-based graphics scale without quality degradation
- **Modular CSS Architecture**: Tailwind utility classes enable efficient style management
- **Animation Performance**: Hardware-accelerated CSS animations maintain performance with feature additions
- **GitHub API Efficiency**: Minimal data fetching pattern established for sustainable contributor display

---

**Note**: Sections marked with placeholders will be populated through collaborative analysis of Figma design screenshots and iterative refinement based on user feedback and requirements.