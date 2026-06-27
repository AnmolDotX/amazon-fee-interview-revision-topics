This is your definitive, master preparation curriculum for the Amazon Front End Engineer (FEE) interview loop. It is structured explicitly around the latest standards, focusing on high-frequency topics, exact sub-concepts, and representative sample questions you must master.

---

## Round 1: Problem Solving & Data Structures (DSA)

Amazon expects an FEE to have a strong handle on data manipulation, space/time complexity, and memory utilization. The focus is heavily weighted toward structures that resemble or manipulate hierarchical UI data.

### Key Topics to Cover

* **Trees & Hierarchies (High Frequency):** DOM trees are naturally hierarchical. You must master Depth-First Search (DFS) and Breadth-First Search (BFS), finding lowest common ancestors, and tree serialization/deserialization.
* **The String & Array Blueprint:** Two-pointer techniques, sliding windows for contiguous tracking, and custom manipulation without built-in library methods.
* **Hash Maps & Sets:** Constant-time $\mathcal{O}(1)$ lookups, frequency maps, caching strategies (memoization), and duplicate detection.
* **Stacks & Queues:** Evaluating nested structures (like HTML tags or brackets), managing state history (undo/redo), and processing asynchronous microtask/macrotask event queues.

### Sample Questions & Patterns

* **Pattern 1: DOM/Tree Traversal**
* *Question:* Given two identical DOM trees $A$ and $B$, and a specific node $N$ in tree $A$, find the corresponding node in tree $B$.
* *Question:* Implement a function `flattenTree(root)` that takes a nested object structure (representing a folder directory or UI layout) and flattens it into a single-level array of items.


* **Pattern 2: Sliding Window / String Processing**
* *Question:* Find the longest substring without repeating characters ([LeetCode 3](https://leetcode.com/problems/longest-substring-without-repeating-characters/)).
* *Question:* Implement an algorithm to find the minimum window substring that contains all characters of another string ([LeetCode 76](https://leetcode.com/problems/minimum-window-substring/)).


* **Pattern 3: Stack Processing**
* *Question:* Validate if a string containing HTML tags or various brackets (`(`, `{`, `[`) is properly balanced and closed in the correct order.



---

## Round 2: Front-End Machine Coding & Web UI Build

This round tests your capability to write production-grade, maintainable code within 45 to 60 minutes. You must show mastery over vanilla web APIs, framework paradigms, state flow, and web accessibility.

### Key Topics to Cover

* **Vanilla JavaScript Fundamentals:** Core browser event loops, event delegation/bubbling, closures, prototypes, custom Promise implementations, throttling, and debouncing.
* **UI Components from Scratch:** State synchronization, performant DOM updates, asset optimization, and state transitions.
* **Accessibility (a11y) & Semantic HTML:** Proper usage of ARIA roles (`aria-live`, `aria-expanded`, `role="combobox"`), keyboard navigation focus traps, and screen-reader friendliness.
* **CSS Layout Architectures:** Advanced Flexbox and Grid layouts, responsive breakpoints without layout shift (CLS minimization), and robust style isolation.

### Sample Questions & Custom Implementations

* **Pattern 1: Custom Utilities & Polyfills**
* *Question:* Implement a custom `Promise.all()` polyfill that handles an array of promises, resolving only when all resolve, or rejecting immediately on the first failure.
* *Question:* Write a robust `debounce` and `throttle` function that handles trailing/leading executions and preserves the correct execution context (`this`).


* **Pattern 2: Machine Coding Widgets**
* *Question:* Build an **Autocomplete / Typeahead Search Bar** from scratch. Requirements: Fetch data from a mock API, debounce network calls, support keyboard arrow keys to navigate suggestions, highlight the matching text segment, and ensure accessibility standards.
* *Question:* Build a **Virtual Scroll / Infinite Scroll List View**. Requirements: Handle 50,000 items gracefully without dropping frames, recycle DOM nodes to prevent memory bloat, and track scroll thresholds using `IntersectionObserver`.
* *Question:* Build a highly accessible **Star Rating Widget** or **Dynamic Nested Accordion** component using clean state passing.



---

## Round 3: Front-End System Design & Architecture

For mid-to-senior levels, you must design complex client-side applications. The evaluation moves away from database clustering and focuses entirely on the flow of data across the client layer.

```
+-------------------------------------------------------------+
|                      CLIENT CONTAINER                       |
|                                                             |
|  +--------------------+             +--------------------+  |
|  |     VIEW LAYER     | <---------> |    STATE ENGINE    |  |
|  | (React / Component) |  Updates    | (Normalized Cache) |  |
|  +--------------------+             +--------------------+  |
|            ^                                  ^             |
|            | User Interaction                 | Synced      |
|            v                                  v             |
|  +-------------------------------------------------------+  |
|  |                   NETWORKING LAYER                    |  |
|  |     (REST / WebSockets, Retry Logic, Abort Signals)    |  |
|  +-------------------------------------------------------+  |
+-------------------------------------------------------------+
                             |
                             | Network Request
                             v
               +---------------------------+
               |    EDGE / BACKEND APIS    |
               +---------------------------+

```

### Key Topics to Cover

* **Application Lifecycle & Architecture:** Single Page Applications (SPA) vs. Server-Side Rendering (SSR) vs. Static Site Generation (SSG). Client-side routing models and bundle splitting/lazy loading modules.
* **State Management & Normalization:** Global vs. local state architecture, structuring data stores to avoid complex deep nesting, and minimizing unnecessary re-renders.
* **Client-Server Data Delivery:** REST APIs vs. GraphQL vs. WebSockets/SSE. Designing robust network handling with error boundary fallbacks, retry logic with exponential backoff, and pagination patterns (Cursor vs. Offset).
* **Performance Optimization & Analytics:** Core Web Vitals profiling (LCP, FID/INP, CLS). Asset pipeline optimizations (critical CSS path, image compression formats like WebP, font preloading), and setting up real-user monitoring (RUM) tracking beacons safely.
* **Security Profiles:** Mitigating Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), maintaining secure Content Security Policies (CSP), and handling token storages safely (`HttpOnly` cookies vs. LocalStorage).

### Sample Architecture Prompts

* *Prompt:* **Design an Infinite Scroll News Feed App (like Amazon's home product feed).**
* *Focus Areas:* Discuss data schema normalization, API pagination options, performance optimization of the view pipeline to avoid DOM memory leakage, image lazy-loading, and local caching strategies for offline accessibility.


* *Prompt:* **Design a Real-Time Collaborative Document Workspace (or Live Notification System).**
* *Focus Areas:* Choosing between long polling, WebSockets, or Server-Sent Events (SSE). Discussing state conflict resolution mechanisms on the client side, and gracefully degradation architectures when internet access is dropped.


* *Prompt:* **Design a Global Component Design System.**
* *Focus Areas:* Distribution pipelines, component versioning strategies, managing theme configurations (CSS variables vs CSS-in-JS), accessibility compliance architectures, and testing methodologies.



---

## Round 4: Amazon Leadership Principles & Behavioral

Amazon's hiring engine uses their official Leadership Principles (LPs) to determine if a candidate fits the company's culture. You must prepare multiple distinct professional stories formatted strictly in the **STAR method** (Situation, Task, Action, Result).

### Core Principles Evaluated for FEEs

* **Customer Obsession:** Prioritizing user experience over technical convenience.
* **Ownership:** Moving past the boundaries of your immediate team to fix a problem, write missing documentation, or address systemic tech debt.
* **Deliver Results:** Finding ways to ship impactful work despite tight deadlines, changing product definitions, or missing requirements.
* **Have Backbone; Disagree and Commit:** Backing up your arguments with engineering data while maintaining a healthy collaborative environment.

### Target Behavioral Scenarios

* *Question:* "Tell me about a time when you noticed a critical performance bottleneck or security vulnerability on the frontend that wasn't directly assigned to you. What actions did you take to correct it?"
* *Question:* "Describe a situation where you had a major technical disagreement with a backend engineer or product manager regarding how an API contract should be structured. How did you resolve the deadlock?"
* *Question:* "Give me an example of a time when you had to balance shipping a critical frontend feature quickly versus implementing perfect code quality. What trade-offs did you make, and how did you track the follow-up debt?"

### High-Impact Preparation Drill

To guarantee you hit the exact bar expected across all rounds, use this final breakdown matrix during your daily study tracking:

| Round Type | Daily Focus Topic | Practice Target |
| --- | --- | --- |
| **DSA** | Tree/DOM Iterations & Queue processing | Implement DFS/BFS without frameworks or helpers. |
| **Machine Coding** | Component building & Accessibility | Build widgets inside a plain text editor with strict keyboard navigation loops. |
| **System Design** | Client architecture & Performance profiling | Map data layers, caching lifetimes, and API endpoints out loud. |
| **Behavioral** | Leadership Stories | Draft 6 distinct STAR narratives emphasizing engineering ownership and impact. |
