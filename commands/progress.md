# /progress

Track your learning progress, achievements, and advancement through your chosen career path.

## Usage

```
/progress [role] [--detailed] [--export] [--compare]
```

## Examples

### View your overall progress
```
/progress
```

### Check progress in a specific role
```
/progress react-developer
/progress backend-python
```

### Get detailed breakdown
```
/progress react-developer --detailed
```

### Export progress report
```
/progress react-developer --export pdf
/progress react-developer --export csv
```

### Compare with recommended pace
```
/progress react-developer --compare
```

## Progress Metrics

### Completion Metrics
- **Overall Progress** - Percentage of topics completed
- **Stage Progress** - Achievement within current stage
- **Topics Completed** - Number of completed learning modules
- **Skills Mastered** - Confirmed skills with assessments
- **Projects Completed** - Hands-on projects finished

### Time Metrics
- **Time Invested** - Total hours spent learning
- **Time per Topic** - Average hours per module
- **Recommended vs Actual** - Comparison to expected pace
- **Learning Velocity** - Speed of topic completion

### Quality Metrics
- **Assessment Scores** - Quiz and exam performance
- **Project Quality** - Grading of completed projects
- **Code Review Feedback** - Quality assessments
- **Skill Confidence** - Self-reported confidence levels

## Progress Dashboard

### Current Stage
Shows which of the 4 learning stages you're in:
1. 🟢 **Foundations** - Core concepts
2. 🟡 **Intermediate** - Advanced patterns
3. 🟠 **Advanced** - Complex systems
4. 🔴 **Professional** - Mastery level

### Streak & Consistency
- **Learning Streak** - Consecutive days of learning
- **Longest Streak** - Best consistency achieved
- **Frequency** - Learning sessions per week
- **Consistency Score** - Overall dedication metric

### Achievements & Badges

Unlock badges by reaching milestones:
- 🎖️ **First Topic** - Complete your first learning topic
- 📚 **Knowledge Base** - Complete 10 topics
- 🏆 **Stage Master** - Complete a full learning stage
- 🚀 **Fast Learner** - Complete 50% ahead of schedule
- 🎯 **Focused** - 30-day learning streak
- 💎 **Excellence** - Score 90%+ on assessments
- 🌟 **Role Expert** - Complete entire role path
- 👥 **Mentor** - Help 5 other learners

### Recommended Next Steps
- **Next Topic** - Suggested topic to study
- **Prerequisites** - Skills to review
- **Stretch Goal** - Challenge topic
- **Review Items** - Concepts to reinforce

## Detailed Breakdown

View detailed progress by component:

### By Stage
```
Stage 1: Foundations        ████████░░ 80% (32/40 hours)
Stage 2: Intermediate       ██████░░░░ 60% (36/60 hours)
Stage 3: Advanced           ░░░░░░░░░░ 0%  (0/80 hours)
Stage 4: Professional       ░░░░░░░░░░ 0%  (0/60 hours)
```

### By Category
```
Fundamentals        ██████████ 100% ✅
Advanced Patterns   ████████░░ 80%  📚
Performance         ██████░░░░ 60%  📚
Testing             ████░░░░░░ 40%  🚀
Deployment          ░░░░░░░░░░ 0%   ⏳
```

### By Topic
- ✅ Completed
- 🔄 In Progress
- ⏳ Upcoming
- 🔁 Review Needed
- 🚀 Mastered

## Comparison & Benchmarking

Compare your progress:
- **vs Recommended Pace** - Are you ahead or behind?
- **vs Peer Average** - How do you compare to others?
- **vs Estimated Completion** - When will you finish?
- **vs Similar Roles** - Progress in related paths

## Export Options

### PDF Report
- Professional formatting
- Printable layout
- Certificates and badges
- Complete progress history

### CSV Data
- All metrics in spreadsheet format
- Historical data export
- Easy data analysis
- Integration with tools

### JSON Export
- Complete learning history
- All raw metrics
- Timestamps and data
- Program-readable format

## Milestones

Track major achievements:
- ✅ Stage 1 Complete
- ✅ First Project Finished
- ✅ Halfway to Goal
- ✅ Mastery Assessment Passed
- ✅ Career Path Complete

## Learning Insights

AI-powered insights based on your progress:
- 📈 **Trending Up** - You're accelerating in this topic
- 📉 **Slow Down** - You might need more time here
- 🔥 **On Fire** - Great momentum, keep it up!
- ⚠️ **Stuck?** - Struggling with this concept? Get help
- 🎯 **Perfect Pace** - You're on track perfectly

## Tips for Continued Progress

1. **Daily Learning** - Consistent 1-2 hours beats weekend cramming
2. **Build Projects** - Apply knowledge to real problems
3. **Review Regularly** - Reinforce learning with spaced repetition
4. **Seek Help** - Use agents when stuck
5. **Celebrate Wins** - Acknowledge your progress
6. **Adjust Pace** - Speed up or slow down as needed

## Share Your Progress

- 📤 Share achievements on social media
- 📧 Email progress report to mentor
- 💾 Save progress for portfolio
- 🔗 Get shareable progress link

## Reset or Change Path

- Switch to different role with `/learn new-role`
- Reset progress with `/learn role --restart`
- Archive past learning with `/progress --archive`
