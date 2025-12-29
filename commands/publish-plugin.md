---
name: publish-plugin
description: plugin
allowed-tools: Read
---

# /publish-plugin

Publish and distribute your plugin to the Claude Code marketplace with expert guidance from the Community Manager and Growth Strategist.

## Usage

```
/publish-plugin [plugin-name] [--validate] [--prepare] [--submit] [--distribute]
```

## Examples

### Start publishing process
```
/publish-plugin my-plugin
```

### Validate plugin
```
/publish-plugin my-plugin --validate
```

### Prepare for submission
```
/publish-plugin my-plugin --prepare
```

### Submit to marketplace
```
/publish-plugin my-plugin --submit
```

### Distribute through channels
```
/publish-plugin my-plugin --distribute
```

## Publishing Process

### Phase 1: Validation (--validate)

Ensure plugin is ready:
- Structure validation
- Manifest validation
- Code quality check
- Documentation check
- Accessibility check
- Security scan

Output:
- Validation report
- Issues list
- Recommendations
- Quality score

### Phase 2: Preparation (--prepare)

Prepare for marketplace:
- Polish documentation
- Create marketing assets
- Write descriptions
- Create screenshots
- Record demo video
- Prepare FAQs

Output:
- Marketing assets
- Marketplace listing
- Screenshots
- Demo video
- Support documentation

### Phase 3: Submission (--submit)

Submit to marketplaces:
- Claude Code marketplace
- Alternative marketplaces
- Directory listings
- Plugin registries
- Community platforms

Output:
- Submission confirmations
- Listing URLs
- Support resources
- Tracking information

### Phase 4: Distribution (--distribute)

Promote your plugin:
- Launch announcement
- Social media campaign
- Email campaign
- Community engagement
- Partnership activation
- PR outreach

Output:
- Distribution plan
- Marketing calendar
- Campaign results
- User feedback

## Full Publishing Workflow

```
/publish-plugin my-plugin --validate --prepare --submit --distribute
```

Combines all phases for complete publishing process.

## Validation Checklist

### Structure Validation
- [ ] `.claude-plugin/plugin.json` exists
- [ ] Manifest is valid JSON
- [ ] All required fields present
- [ ] File paths are correct
- [ ] No circular dependencies
- [ ] File permissions correct

### Content Validation
- [ ] README is complete
- [ ] LICENSE file present
- [ ] CHANGELOG exists
- [ ] Documentation is accurate
- [ ] Code examples work
- [ ] Links are valid

### Code Quality
- [ ] No syntax errors
- [ ] Proper formatting
- [ ] Comments where needed
- [ ] No hardcoded secrets
- [ ] Error handling implemented
- [ ] Performance optimized

### Security Scan
- [ ] No known vulnerabilities
- [ ] Dependencies updated
- [ ] Secure coding practices
- [ ] No sensitive data exposed
- [ ] Authentication secure
- [ ] HTTPS for external APIs

### Accessibility Check
- [ ] WCAG compliance
- [ ] Color contrast
- [ ] Keyboard navigation
- [ ] Screen reader support
- [ ] Alternative text
- [ ] Clear error messages

## Marketplace Preparation

### Listing Information
```json
{
  "name": "My Plugin",
  "displayName": "My Awesome Plugin",
  "description": "Short description of what it does",
  "longDescription": "Detailed description",
  "author": "Your Name",
  "tags": ["useful", "plugins"],
  "icon": "emoji or URL",
  "repository": "GitHub URL",
  "documentation": "Docs URL"
}
```

### Marketing Assets
- **Icon/Logo** - 512x512 PNG
- **Screenshots** - 1-5 screenshots
- **Cover Image** - 1200x600 banner
- **Demo Video** - 30-60 second MP4
- **Description** - 50-500 characters
- **Category** - Main category
- **Tags** - 3-5 tags

### Documentation
- **Getting Started** - 5 minute guide
- **Features Overview** - Feature list
- **Installation** - Step-by-step
- **Configuration** - Setup guide
- **Examples** - Code examples
- **Troubleshooting** - Common issues
- **FAQ** - Frequently asked questions

### Support Information
- **Contact** - Email or support page
- **Issue Tracking** - GitHub issues
- **Community** - Discord/forum
- **Documentation** - Link to docs
- **Changelog** - Version history
- **Roadmap** - Future plans

## Marketplace Submission

### Claude Code Marketplace

1. **Register Account**
   - Create account if needed
   - Verify email
   - Complete profile

2. **Prepare Listing**
   - Fill in all fields
   - Upload assets
   - Write description
   - Add tags and category

3. **Submit Plugin**
   - Review submission
   - Agree to terms
   - Submit for review

4. **Await Approval**
   - Review period: 2-7 days
   - May request changes
   - Get approval notification

### Alternative Marketplaces

- Plugin directories
- GitHub marketplace
- npm registry
- Package managers
- Community sites

## Publishing Timeline

### Week 1: Validation & Preparation
- Day 1-2: Validate plugin
- Day 2-3: Prepare assets
- Day 3-4: Create documentation
- Day 4-5: Prepare marketing
- Day 5-7: Final review

### Week 2: Submission & Launch
- Day 1-2: Submit to marketplace
- Day 3-4: Prepare announcements
- Day 5: Launch day
- Day 6-7: Monitor and support

### Week 3+: Distribution & Growth
- Week 3: Full distribution
- Week 4: Gather feedback
- Week 5+: Optimize and iterate

## Distribution Channels

### Direct Channels
- Official marketplace
- Plugin registry
- Community directories
- Plugin search engines
- Technology news sites

### Owned Channels
- Website
- Blog
- Email list
- Social media
- Community forums

### Partnership Channels
- Influencer partnerships
- Integration partnerships
- Marketplace partnerships
- Channel partnerships
- Integration directories

## Launch Announcement

### Content to Create
- Blog post announcing launch
- Social media posts (multiple)
- Email to subscribers
- Press release
- Community post
- Video announcement

### Channels to Use
- Twitter/X
- LinkedIn
- Product Hunt
- Hacker News
- Community forums
- Email newsletters

### Timing
- Announce pre-launch teasers
- Launch day announcement
- Follow-up posts
- Weekly highlights
- Feature spotlights
- User stories

## Post-Launch Support

### First Week
- [ ] Monitor support channels
- [ ] Respond to feedback
- [ ] Fix critical issues
- [ ] Update documentation
- [ ] Gather user data
- [ ] Share early wins

### First Month
- [ ] Release updates
- [ ] Implement user requests
- [ ] Optimize based on data
- [ ] Build community
- [ ] Create user guides
- [ ] Launch referral program

### Ongoing
- [ ] Regular updates
- [ ] Community engagement
- [ ] User support
- [ ] Feature development
- [ ] Marketing campaigns
- [ ] Analytics monitoring

## Success Metrics

### Marketplace Metrics
- Downloads/installs
- Rating/reviews
- Trending position
- Search visibility
- Marketplace ranking

### Usage Metrics
- Daily active users
- Monthly active users
- Feature usage
- Session duration
- Retention rate

### Business Metrics
- Revenue (if applicable)
- Customer acquisition cost
- Customer lifetime value
- Churn rate
- Conversion rate

### Community Metrics
- Forum posts
- GitHub stars
- Social followers
- Community size
- Engagement rate

## Quality Standards

### Rating Standards
- 4.5+ stars: Excellent
- 4.0-4.5 stars: Very good
- 3.5-4.0 stars: Good
- 3.0-3.5 stars: Acceptable
- <3.0 stars: Needs improvement

### Review Response
- Respond to all reviews
- Thank positive reviewers
- Address concerns
- Offer to help with issues
- Keep tone professional

## Maintenance Checklist

- [ ] Keep dependencies updated
- [ ] Fix security issues
- [ ] Release regular updates
- [ ] Monitor user feedback
- [ ] Update documentation
- [ ] Maintain marketplace listing
- [ ] Engage with community
- [ ] Track analytics

## Publisher Guidelines

**Quality Standards**
- Clean, professional presentation
- Clear documentation
- Active maintenance
- Responsive support
- Regular updates
- User-focused design

**Ethical Standards**
- Honest descriptions
- No misleading claims
- Privacy respected
- Data handled securely
- Transparent pricing
- User trust earned

**Community Standards**
- Positive engagement
- Helpful responses
- Fair pricing
- Respect for users
- Openness to feedback
- Community contribution

## Tips for Success

1. **Polish first** - Ensure plugin is production-ready
2. **Clear description** - Help users understand value
3. **Great documentation** - Make it easy to use
4. **Responsive support** - Help users succeed
5. **Regular updates** - Show active maintenance
6. **Engage community** - Build relationships
7. **Gather feedback** - Listen to users
8. **Iterate** - Continuously improve

## Launch Checklist

- [ ] Validation complete
- [ ] All assets ready
- [ ] Documentation final
- [ ] Support system ready
- [ ] Marketplace listing prepared
- [ ] Announcements scheduled
- [ ] Marketing calendar ready
- [ ] Team ready for launch
- [ ] Analytics configured
- [ ] Feedback mechanisms ready
