# 🔄 Complete Command Workflow Specifications

## Detailed User Journey Maps & Technical Specifications

---

## COMMAND 1: /learn - Personalized Learning Paths

### User Journey Map

```
START: User types /learn
  ↓
[Step 1] Welcome Screen
├── "Welcome to Ultrathink Learning!"
├── "Let's find your perfect learning path"
└── Options: "Start Fresh" | "Continue" | "Browse First"

  ↓
[Step 2] Learning Style Assessment (Optional)
├── Question: "How do you prefer to learn?"
├── Options:
│   ├── Visual (videos, diagrams)
│   ├── Hands-on (projects, exercises)
│   ├── Reading (documentation, articles)
│   └── Mixed (combination)
└── Question: "How much time can you dedicate?"
    ├── 5 hours/week
    ├── 10 hours/week
    ├── 20 hours/week
    └── 40+ hours/week (full-time)

  ↓
[Step 3] Role/Goal Selection
├── Show 69 roles grouped by category
├── Search functionality
├── "Tell me what interests you" (AI interpretation)
└── User selects 1-3 roles of interest

  ↓
[Step 4] Prerequisite Assessment
├── System checks prerequisites
├── "Do you have these skills?"
│   ├── Programming fundamentals (Y/N)
│   ├── Specific language knowledge (Y/N)
│   ├── Mathematics (Y/N)
│   └── Domain knowledge (Y/N)
└── If gaps: Recommend foundation courses

  ↓
[Step 5] Current Level Assessment (Quick)
├── 5 quick questions per skill area
├── Determine Level 1-5
└── Identify strongest & weakest areas

  ↓
[Step 6] Path Customization
├── Select specialization within role
├── Set specific goals
├── Choose learning pace
│   ├── Slow (6-12 months)
│   ├── Medium (3-6 months)
│   ├── Fast (1-3 months)
│   └── Intensive (Full-time)
└── Define time commitment per week

  ↓
[Step 7] Resource Preferences
├── "Which resources do you prefer?"
│   ├── Video courses
│   ├── Interactive coding
│   ├── Reading & docs
│   ├── Mentorship
│   └── All of the above
└── "Any technologies you want to avoid?"

  ↓
[Step 8] Personalized Path Generation
├── AI generates custom curriculum
├── Breakdown:
│   ├── Phase 1: Foundation (dates & hours)
│   ├── Phase 2: Core Skills (dates & hours)
│   ├── Phase 3: Advanced (dates & hours)
│   ├── Phase 4: Specialization (dates & hours)
│   └── Milestone dates
├── Recommended projects
├── Estimated completion date
└── Time investment summary

  ↓
[Step 9] Path Review & Confirmation
├── Display full path visually
├── "Does this look good?"
├── Adjustment options:
│   ├── "Make it faster"
│   ├── "Make it slower"
│   ├── "Change specialization"
│   └── "Choose different role"
└── Confirm & start

  ↓
[Step 10] First Learning Module
├── Load Agent specialist for this role
├── Show Phase 1, Week 1 content
├── First resource: video/reading/exercise
├── Progress tracking active
└── Bookmark option for resume later

END: Learning path active
```

### Hook Integration Points

| Step | Hook Triggered | Action |
|------|---|---|
| 2 | learning-path-recommender | Analyze learning style |
| 4 | skill-validation | Check prerequisites |
| 5 | assessment-scoring | Calculate level |
| 6 | personalized-content | Generate custom path |
| 8 | progress-tracker | Record path creation |
| 10 | badge-awards | "Started Learning" badge |

### Data Stored

```json
{
  "user_id": "unique_id",
  "learning_path": {
    "role_selected": "backend-developer",
    "specialization": "microservices",
    "level_at_start": 2,
    "time_commitment": "15 hours/week",
    "target_date": "2025-06-18",
    "phases": [...],
    "milestones": [...],
    "learning_style": ["hands-on", "visual"],
    "preferences": {...}
  },
  "progress": {
    "phase_current": 1,
    "week_current": 1,
    "completion_percent": 0,
    "milestones_completed": [],
    "last_accessed": "timestamp"
  }
}
```

---

## COMMAND 2: /browse - Discover & Explore

### User Journey Map

```
START: User types /browse
  ↓
[Step 1] Main Categories View
├── Display 7 categories with icons
├── AI & Data Science (8 roles)
├── Backend Development (11 roles)
├── Frontend & Mobile (13 roles)
├── Programming Languages (11 roles)
├── DevOps & Cloud (12 roles)
├── Architecture & Security (8 roles)
├── Management & Specialized (10 roles)
├── Stats: Total 69 roles, 1000+ hours content
└── Options: Browse | Search | Filter | Random

  ↓
[Step 2] Category Deep Dive
├── User selects category (e.g., "Backend")
├── Shows all 11 roles in category
├── For each role: name, brief description, hours, salary
├── Sorting options:
│   ├── By difficulty
│   ├── By salary
│   ├── By time commitment
│   ├── Alphabetical
│   └── Most popular
└── Filtering: difficulty, salary range, skills

  ↓
[Step 3] Role Detail View
├── User clicks on role (e.g., "Backend Developer")
├── Full role description
├── Key technologies
├── Skills to master (list)
├── Salary progression
│   ├── Entry-level: $80-120K
│   ├── Mid-level: $110-160K
│   ├── Senior: $160-230K
│   └── Staff: $220-320K+
├── Time to competency by level
├── Prerequisites
├── Top projects for this role
├── Job market demand (hot, stable, declining)
├── Related roles (similar skills)
└── Actions: "Start Learning" | "Compare" | "Save"

  ↓
[Step 4] Technology Focused Browse
├── Alternative view: Browse by tech
├── Select technology: React, Python, AWS, etc.
├── Shows all roles using this tech
├── Career path with this tech
├── Learning resources
└── Salary expectations

  ↓
[Step 5] Comparison View
├── Compare up to 3 roles side-by-side
├── Comparison matrix:
│   ├── Skills required
│   ├── Time to competency
│   ├── Salary ranges
│   ├── Job availability
│   ├── Growth trajectory
│   ├── Specializations
│   └── Typical responsibilities
├── Pros/cons of each
└── Salary comparison chart

  ↓
[Step 6] Search Functionality
├── Global search across:
│   ├── Role names
│   ├── Skills
│   ├── Technologies
│   ├── Keywords
│   └── Descriptions
├── Filters: difficulty, salary, time, job market
└── Suggestions as user types

  ↓
[Step 7] Saved & Wishlists
├── Save roles for later comparison
├── Create shortlists: "Interested", "Maybe", "Not for me"
├── Share lists with friends
├── Get recommendations based on saves
└── Timeline: "Plan path for 2025"

  ↓
[Step 8] Career Path Visualization
├── "Show me the path from X to Y"
├── Example: "From Junior Dev to Tech Lead"
├── Visual progression chart
├── Time estimates for each step
├── Skills to learn at each stage
├── Salary progression
└── Decision points (specialist vs management)

END: User exits browse with informed choices
```

### Hook Integration

| Action | Hook | Function |
|--------|------|----------|
| View role | progress-tracker | Track interest |
| Compare roles | personalized-content | Recommend similar |
| Save role | badge-awards | "Explorer" badge |
| View career path | learning-path-recommender | Suggest next role |

---

## COMMAND 3: /assess - Skill Assessments

### Comprehensive Assessment Workflow

```
START: User types /assess
  ↓
[Step 1] Assessment Type Selection
├── "What would you like to assess?"
├── Options:
│   ├── Single skill (React, Python, etc.)
│   ├── Role readiness (ready for X role?)
│   ├── Level check (what's my current level?)
│   ├── Full evaluation (complete profile)
│   ├── Career fit (which roles suit me?)
│   └── Pre-course (evaluate before learning)
└── Time commitment displayed (15 min - 2 hours)

  ↓
[Step 2] Assessment Configuration
├── Difficulty level preference:
│   ├── Beginner (easier, quick)
│   ├── Intermediate (balanced)
│   ├── Advanced (challenging)
│   └── Auto (adaptive)
├── Focus areas (if multi-skill)
├── Format preference:
│   ├── Multiple choice (quick)
│   ├── Short answer (thorough)
│   ├── Practical (coding)
│   └── Mixed (comprehensive)
└── "Start Assessment" | "Get Sample Question"

  ↓
[Step 3] Assessment Execution
├── Questions presented one-at-a-time
├── For each question:
│   ├── Question text
│   ├── Options/answer field
│   ├── Difficulty indicator
│   ├── Hint option (reveals once)
│   └── Explanation shown after answer
├── Timer (if timed)
├── Progress bar
├── Option to skip (comes back later)
└── Save progress (resume later)

  ↓
[Step 4] Question Types

A. Multiple Choice
├── Question
├── 4-5 options
├── Immediate feedback
└── Explanation

B. Short Answer
├── Question
├── Text input
├── AI grading
└── Detailed explanation

C. Practical Coding
├── Problem description
├── Starter code
├── Test cases shown
├── Code editor
├── Auto-grading
└── Solution review

D. True/False
├── 10 statements
├── Identify which are true
└── Explanation for each

  ↓
[Step 5] Adaptive Testing
├── Easy question answered correctly?
│   └── → Show harder question
├── Hard question answered incorrectly?
│   └── → Show easier question
├── Converges on actual level
└── Efficient assessment (20-30 questions)

  ↓
[Step 6] Assessment Complete
├── Show final score
├── Immediate feedback
├── Score breakdown by topic
├── Percentile ranking
└── "Generate Report"

  ↓
[Step 7] Results & Analysis
├── Overall Score: 75/100 (Level 3 - Competent)
├── Breakdown:
│   ├── Fundamentals: 85% (Excellent)
│   ├── Core concepts: 78% (Good)
│   ├── Advanced topics: 65% (Needs work)
│   └── Practical application: 70% (Fair)
├── Comparison:
│   ├── vs. your previous score
│   ├── vs. community average
│   ├── vs. role requirement (if applicable)
│   └── vs. expected by this level
├── Time taken vs. average
└── Confidence scores per topic

  ↓
[Step 8] Insights & Recommendations
├── "Your Strengths"
│   ├── Fundamentals solid
│   ├── Good understanding of patterns
│   └── Practical skills good
├── "Areas for Improvement"
│   ├── Advanced concepts need work
│   ├── Performance optimization weak
│   └── System design needs practice
├── "Recommended Next Steps"
│   ├── Learn X module (Intermediate path)
│   ├── Practice Y skill (5-6 hours)
│   ├── Build Z project (10-15 hours)
│   └── Take X role path (would be ready in 3-4 months)
├── Resources provided
│   ├── Articles to read
│   ├── Videos to watch
│   ├── Exercises to practice
│   └── Projects to build
└── Timeline to next level

  ↓
[Step 9] Learning Plan Generation
├── "Create Personalized Learning Plan?"
├── System generates:
│   ├── Specific topics to learn
│   ├── In recommended order
│   ├── With time estimates
│   ├── With resource links
│   └── With milestone dates
├── "Start Learning" | "Review Plan" | "Save for Later"
└── Send to email if desired

  ↓
[Step 10] Results Portal
├── Access results anytime
├── Download PDF report
├── Track assessment history
├── Compare results over time
├── Share score (anonymously or not)
└── Retake assessment (can track improvement)

END: User has detailed profile & learning plan
```

### Assessment Scoring

```
Score Range: 0-100
Level 1 (Awareness): 0-25
├── Multiple choice only
├── Basic concepts
└── Pass: 60%

Level 2 (Beginner): 26-50
├── Multiple choice + short answer
├── Core concepts
└── Pass: 70%

Level 3 (Competent): 51-75
├── Mixed format
├── Advanced concepts
└── Pass: 80%

Level 4 (Proficient): 76-90
├── Includes practical coding
├── System design
└── Pass: 85%

Level 5 (Expert): 91-100
├── Very difficult questions
├── Novel problems
└── Pass: 90%
```

### Hook Integration Points

| Point | Hook | Function |
|-------|------|----------|
| Start | assessment-scoring | Prepare grading |
| Answer | progress-tracker | Track responses |
| Complete | assessment-scoring | Score & analyze |
| Results | learning-path-recommender | Generate recommendations |
| Create plan | personalized-content | Customize plan |
| Save score | badge-awards | "Assessed" badge |

---

## COMMAND 4: /projects - Project Discovery & Building

### Project Discovery & Execution Workflow

```
START: User types /projects
  ↓
[Step 1] Project Discovery
├── Filter options:
│   ├── By difficulty (Beginner/Intermediate/Advanced)
│   ├── By time (5-20 hrs / 20-60 hrs / 60+ hrs)
│   ├── By technology (React, Python, etc.)
│   ├── By domain (Web, Mobile, Data, etc.)
│   ├── By role (match to learning path)
│   └── By rating (community feedback)
├── Sort by:
│   ├── Popular
│   ├── Newest
│   ├── Most relevant to you
│   ├── Difficulty
│   └── Time commitment
└── Search text (AI-powered)

  ↓
[Step 2] Project Listing
├── Project cards showing:
│   ├── Name & description
│   ├── Difficulty star rating
│   ├── Estimated time (hours)
│   ├── Technologies used
│   ├── Skills taught (3-5)
│   ├── Average rating (⭐⭐⭐⭐)
│   ├── Student count (how many did it)
│   ├── Completion rate
│   └── "Start" | "Details" | "Save"

  ↓
[Step 3] Project Details
├── Full project description
├── Learning objectives (5-8)
├── Prerequisites (what you should know first)
├── Technologies & tools required
├── Time breakdown:
│   ├── Setup: X hours
│   ├── Core learning: Y hours
│   ├── Building: Z hours
│   ├── Testing: A hours
│   └── Polishing: B hours
├── Difficulty breakdown
├── Skills you'll gain
├── Real-world relevance
├── Success criteria
├── Reviews from students
└── "Start Project"

  ↓
[Step 4] Project Start
├── Prerequisites check
├── "Install these tools first" (links provided)
├── Environment setup instructions
├── Clone starter repo (if applicable)
├── First lesson/video
├── Resources page with:
│   ├── All documentation links
│   ├── Code examples
│   ├── Tutorial videos
│   ├── Cheat sheets
│   └── Discussion forums
└── Project workspace activated

  ↓
[Step 5] Project Phases

PHASE 1: Setup & Learn (30% of time)
├── Install tools
├── Watch intro video
├── Read architecture guide
├── Complete code-along tutorial
└── "Setup complete" checkpoint

PHASE 2: Build Core Features (40% of time)
├── Implement feature 1
│   ├── Task description
│   ├── Code hint
│   ├── Test cases
│   ├── Video walkthrough
│   └── Auto-grading (if applicable)
├── Implement feature 2...
├── Implement feature N...
└── Progress bar shows completion

PHASE 3: Advanced Features (20% of time)
├── Optional enhancements
├── Performance optimization
├── UI/UX improvements
├── Additional testing
└── Code review preparation

PHASE 4: Polish & Deploy (10% of time)
├── Fix remaining issues
├── Code cleanup
├── Documentation
├── Deployment (if applicable)
└── Portfolio preparation

  ↓
[Step 6] Guided Learning During Project
├── For each task:
│   ├── Clear instructions
│   ├── Code examples
│   ├── Video (optional)
│   ├── Hint system (3 levels)
│   ├── Test cases to verify
│   └── Discussion forum for questions

├── Help systems:
│   ├── Discord community chat
│   ├── Mentor assistance (if premium)
│   ├── Stack Overflow links
│   ├── Code review requests
│   └── Peer learning groups

└── Progress tracking:
    ├── Phase completion %
    ├── Time spent
    ├── Time vs. estimate
    ├── Checkpoint achievements
    └── Skill progression

  ↓
[Step 7] Code Review & Feedback
├── Submit completed feature
├── Auto checks:
│   ├── Does it compile/run?
│   ├── All tests passing?
│   ├── Code style valid?
│   ├── Security checks
│   └── Performance benchmarks
├── AI feedback on:
│   ├── Code quality
│   ├── Best practices
│   ├── Potential improvements
│   └── Learning suggestions
└── Optional peer review request

  ↓
[Step 8] Project Completion
├── Final checklist:
│   ├── All features working
│   ├── Code reviewed
│   ├── Documentation complete
│   ├── Tested thoroughly
│   └── Ready to deploy/share
├── Completion ceremony:
│   ├── Badge earned
│   ├── Certificate generated
│   ├── Portfolio link created
│   └── Skills verified
└── Feedback survey

  ↓
[Step 9] Portfolio & Sharing
├── Project added to portfolio
├── GitHub repo link
├── Deployed project URL (if applicable)
├── Project description
├── Skills demonstrated
├── Code quality metrics
├── Time investment
└── Sharing options:
    ├── Public/Private
    ├── LinkedIn
    ├── Twitter
    ├── Email to friends
    └── Employer showcase

  ↓
[Step 10] Career & Progression
├── "This project demonstrates:"
│   ├── You're ready for role X
│   ├── You're at level 3/5
│   ├── Next project recommendation
│   └── What to learn next
├── Progress toward goals
├── Suggested next projects
└── "Continue learning" options

END: Project complete, portfolio enhanced, skills verified
```

### Hook Integration

| Event | Hook | Action |
|-------|------|--------|
| Start | progress-tracker | Track project |
| Complete task | project-tracking | Validate completion |
| Finish project | badge-awards | Award badge |
| Complete | project-validation | Check criteria |
| Submit code | performance-metrics | Analyze code quality |
| Share | community-engagement | Encourage sharing |

---

## Cross-Command Flows

### Complete User Journey (3 months)

```
Week 1:
├── /browse → Explore 69 roles
├── Compare 3 interesting roles
└── Shortlist Backend Developer

Week 2:
├── /assess → Quick skill check (30 min)
├── Results show Level 2 in programming
└── Identify gaps: databases, APIs, frameworks

Week 3:
├── /learn → Choose Backend Developer
├── System creates 12-week learning path
├── Phases: Foundation → Core → Advanced → Specialization
└── Start Phase 1

Weeks 3-6:
├── Follow learning path
├── Complete modules daily
├── Practice exercises from commands
└── Progress tracked via hooks

Week 6:
├── /assess → Mid-course check (1 hour)
├── Results show improvement to Level 3
├── Recommends first project
└── Get confidence boost

Weeks 6-8:
├── /projects → Start "E-commerce API" project
├── Build alongside learning
├── Get code reviews
├── Real application of knowledge
└── Earn portfolio project

Week 9:
├── Finish first project
├── Add to portfolio
├── Share on LinkedIn
└── Get recognition

Weeks 9-12:
├── Continue learning path
├── Complete remaining phases
├── Build 2-3 more projects
└── Deepen specialization

Week 12:
├── /assess → Final comprehensive test (2 hours)
├── Results show Level 3-4 (Competent Professional)
├── Certificate earned
├── Portfolio with 3 strong projects
├── Ready for job interviews
└── Recommended next roles: Microservices, Full-Stack

Months 4-6:
├── Continue with advanced projects
├── Specialize in chosen area
├── Target Level 4 (Proficient)
└── Progress to Senior roles
```

---

## Metrics & Analytics

### Per-Command Metrics

**`/learn` Metrics**:
- Paths created
- Paths completed
- Average time to complete
- Paths abandoned
- Most popular roles
- Specialization choices

**`/browse` Metrics**:
- Roles viewed
- Comparisons made
- Career paths explored
- Saves/wishlist additions
- Role transitions tracked

**`/assess` Metrics**:
- Assessments taken
- Average score
- Score distributions
- Time taken
- Retake rates
- Improvement tracking

**`/projects` Metrics**:
- Projects started
- Projects completed
- Average time
- Completion rates
- Code quality scores
- Portfolio additions

---

## Data Models

### Learning Path Data
```json
{
  "path_id": "uuid",
  "user_id": "uuid",
  "role_selected": "backend-developer",
  "created_date": "2025-01-15",
  "target_date": "2025-04-15",
  "phases": [
    {
      "phase_num": 1,
      "name": "Foundations",
      "duration_weeks": 4,
      "hours_total": 80,
      "modules": [...],
      "status": "in_progress",
      "completion_percent": 45
    }
  ],
  "progress": {
    "overall_percent": 15,
    "hours_completed": 12,
    "last_accessed": "2025-01-20"
  }
}
```

---

This comprehensive workflow specification ensures **complete alignment** between commands, agents, skills, and hooks. Every user interaction is tracked, personalized, and optimized for learning success.
