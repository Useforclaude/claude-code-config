# Claude Code Skills & Global Configuration

This repository contains **68 professional Claude Code skills** and global configuration for enhanced AI-assisted development.

## 🎯 What's Included

### 📚 68 Expert Skills
- **Psychology & Marketing** (26 skills): Consumer psychology, emotional triggers, cognitive biases, influence tactics
- **Copywriting & Content** (11 skills): Storytelling, sales copy, email mastery, SEO content
- **Branding & Strategy** (7 skills): Brand voice, positioning, archetypes
- **Video & Production** (6 skills): AI video prompting, FFmpeg workflows, TTS synthesis
- **Technical & Development** (10 skills): Debug methodology, git safety, automation
- **Design & UX** (4 skills): Design systems, UI/UX, animations
- **Marketing & Strategy** (4 skills): Marketing strategy, funnel optimization, Facebook Ads

### 🌐 Global CLAUDE.md
- Skills auto-loading system (Thai + English keywords)
- Codex debugging methodology
- Document conversion workflows (Thai font support)
- Video production best practices
- Git safety procedures

---

## 🚀 Quick Start

### Option 1: Clone to Your Projects Directory

```bash
# Clone this repo
git clone <your-repo-url> ~/my-projects

# Or if you already have a projects folder:
cd ~/my-projects
git clone <your-repo-url> .claude
mv .claude/CLAUDE.md .
```

### Option 2: Use as Submodule (Recommended)

```bash
# In your project directory:
git submodule add <your-repo-url> .claude-skills

# Link the skills
ln -s .claude-skills/.claude .claude
ln -s .claude-skills/CLAUDE.md CLAUDE.md
```

### Option 3: Direct Copy

```bash
# Download and extract
curl -L <your-repo-url>/archive/main.zip -o skills.zip
unzip skills.zip
cp -r skills-main/.claude ~/my-projects/
cp skills-main/CLAUDE.md ~/my-projects/
```

---

## 📖 How Skills Work

Skills are **model-invoked** (automatic) - Claude loads them based on:
1. Your request keywords
2. Skill descriptions

**Example:**
```
You: "เขียนบทวิดีโอเรื่องปัญหา ERP ให้หน่อย"

Claude:
[Scans: "บทวิดีโอ" (screenplay) + "ปัญหา" (pain point)]
[Loads: storytelling-mastery-skill + consumer-psychology-skill]
[Generates: Professional screenplay with authentic pain points]
```

### ✅ You Don't Need To:
- ❌ Remember skill names
- ❌ Manually invoke skills
- ❌ Know what skills exist

### ✅ Claude Will:
- ✅ Auto-detect relevant skills
- ✅ Load appropriate knowledge
- ✅ Apply expert frameworks
- ✅ Deliver higher quality results

---

## 🇹🇭 Thai Language Support

All skills support **Thai keywords**:

| English | Thai |
|---------|------|
| Copywriting | เขียนข้อความ, เขียนโฆษณา, เขียนขาย |
| Screenplay | เขียนบท, สคริปต์, บทวิดีโอ |
| Pain point | ปัญหาลูกค้า, จุดเจ็บ, ความเจ็บปวด |
| Emotional | อารมณ์, ความรู้สึก, กินใจ, สะเทือนใจ |
| Video editing | ตัดต่อวิดีโอ, รวมวิดีโอ, ประมวลผลวิดีโอ |
| Bug | บั๊ก, ไม่ทำงาน, พัง, เพี้ยน |
| Convert | แปลง, แปลงเอกสาร, เปลี่ยนเป็น |

---

## 📂 Structure

```
.
├── CLAUDE.md                    # Global configuration & rules
├── .claude/
│   └── skills/                  # 68 professional skills
│       ├── storytelling-mastery-skill/
│       │   └── SKILL.md         # Skill content + YAML metadata
│       ├── consumer-psychology-skill/
│       ├── copywriting-formulas-skill/
│       ├── ai-video-prompting-skill/
│       ├── debug-methodology-skill/
│       └── ... (62 more)
└── README.md                    # This file
```

---

## 🔗 Understanding the Two Repositories

This project uses **two separate GitHub repositories** that work together:

### 📦 Repository 1: `skills-claude` (Knowledge Base)
**URL:** https://github.com/Useforclaude/skills-claude.git

**What it contains:**
- 67 SKILL.md files (actual knowledge base content)
- Each skill is a standalone markdown file with YAML frontmatter
- Pure content - no configuration

**Structure:**
```
skills-claude/
├── storytelling-mastery-skill/
│   └── SKILL.md
├── consumer-psychology-skill/
│   └── SKILL.md
├── copywriting-formulas-skill/
│   └── SKILL.md
└── ... (64 more skills)
```

**Purpose:**
- ✅ Shareable knowledge base
- ✅ Can be used in multiple projects
- ✅ Community-maintained (others can contribute skills)
- ✅ Version-controlled independently

**When to update:**
- Adding new skills
- Improving existing skill content
- Fixing errors in skill knowledge

---

### ⚙️ Repository 2: `claude-code-config` (Configuration)
**URL:** https://github.com/Useforclaude/claude-code-config.git

**What it contains:**
- `CLAUDE.md` - Global configuration & rules
- `README.md` - Documentation (this file)
- `.gitignore` - Project exclusions
- `.gitmodules` - Submodule reference to skills-claude
- `.claude/skills/` - Submodule pointing to skills-claude repo

**Structure:**
```
claude-code-config/
├── CLAUDE.md              # Global config (52KB)
├── README.md              # Documentation (11KB)
├── .gitignore
├── .gitmodules
└── .claude/
    └── skills/            # ← Submodule → skills-claude repo
```

**Purpose:**
- ✅ Global Claude Code configuration
- ✅ References skills via git submodule
- ✅ Personal/team-specific settings
- ✅ Can be cloned to set up new machines

**When to update:**
- Changing CLAUDE.md rules
- Updating documentation
- Modifying configuration

---

### 🤔 Why Two Repositories?

**1. Separation of Concerns**
- **Content** (skills) vs **Configuration** (CLAUDE.md)
- Skills can be shared across teams
- Configuration can be customized per person/team

**2. Independent Updates**
- Update skills without touching config
- Update config without touching skills
- Different teams can maintain each

**3. Reusability**
- Use the same skills repo in multiple config setups
- Share skills with community
- Fork and customize separately

**4. Clean Version Control**
- Skills have their own commit history
- Config has its own commit history
- No conflicts between content and settings

---

### 📥 How They Work Together

**When you clone:**
```bash
git clone --recurse-submodules https://github.com/Useforclaude/claude-code-config.git ~/my-projects
```

**You get:**
1. `claude-code-config` repo → Main configuration
2. `.claude/skills/` → Automatically populated from `skills-claude` repo (submodule)

**Result:** Complete setup with both config and skills!

---

### 🔄 Updating Each Repository

**Update Skills Only:**
```bash
cd ~/my-projects/.claude/skills
git pull origin main
git add .
git commit -m "docs: Update skills content"
git push
```

**Update Config Only:**
```bash
cd ~/my-projects
# Edit CLAUDE.md or README.md
git add CLAUDE.md README.md
git commit -m "docs: Update global configuration"
git push
```

**Update Both:**
```bash
# 1. Update skills first
cd ~/my-projects/.claude/skills
git add .
git commit -m "feat: Add new skill"
git push

# 2. Update config to reference new skills version
cd ~/my-projects
git add .claude/skills  # Update submodule reference
git commit -m "chore: Update skills submodule"
git push
```

---

### 🎯 Which Repo Should I Use?

| Task | Repository |
|------|------------|
| Add new skill | `skills-claude` |
| Edit skill content | `skills-claude` |
| Change CLAUDE.md rules | `claude-code-config` |
| Update documentation | `claude-code-config` |
| Share skills with others | `skills-claude` |
| Share your config | `claude-code-config` |
| Clone for new machine | `claude-code-config` (with `--recurse-submodules`) |

---

## 🎓 Top 10 Most Used Skills

1. **ai-video-prompting-skill** ⭐⭐⭐ - VEO3/Sora2 prompts
2. **storytelling-mastery-skill** ⭐⭐⭐ - Screenplay/narrative
3. **emotional-storytelling-skill** ⭐⭐⭐ - Emotional arcs
4. **consumer-psychology-skill** ⭐⭐⭐ - Customer behavior
5. **emotional-triggers-skill** ⭐⭐⭐ - Emotional content
6. **content-marketing-skill** ⭐⭐ - Content strategy
7. **ffmpeg-video-processing-skill** ⭐⭐⭐ - Video workflows
8. **copywriting-formulas-skill** ⭐⭐ - Headlines/CTAs
9. **debug-methodology-skill** ⭐⭐⭐ - Systematic debugging
10. **git-safety-skill** ⭐⭐ - Safe git workflows

---

## 🛠️ Usage Examples

### Example 1: Content Creation
```
You: "เขียนข้อความโฆษณา ERP ให้ดึงดูดใจ"

Claude loads:
- copywriting-formulas-skill (AIDA, PAS, FAB)
- emotional-triggers-skill (กระตุ้นอารมณ์)
- invisible-selling-skill (ขายแบบไม่เหมือนขาย)

Output: High-converting copy with proven formulas
```

### Example 2: Video Production
```
You: "สร้าง screenplay เรื่องปัญหา SME"

Claude loads:
- storytelling-mastery-skill (three-act structure)
- consumer-psychology-skill (pain points)
- emotional-storytelling-skill (emotional arcs)

Output: Professional screenplay with authentic scenarios
```

### Example 3: Debugging
```
You: "โค้ดมันพัง ทำงานไม่ถูก"

Claude loads:
- debug-methodology-skill (Codex methodology)

Output: Systematic root cause analysis
```

---

## 🔧 Customization

### Add Your Own Skills

```bash
# Create new skill
mkdir -p .claude/skills/my-custom-skill
```

Create `SKILL.md` with YAML frontmatter:
```yaml
---
name: my-custom-skill
description: What it does. Use for: keyword1, keyword2, keyword3.
---

# Skill Content

Your frameworks, techniques, and knowledge here...
```

### Project-Specific Skills

```bash
# In your project:
mkdir -p .claude/skills/project-specific-skill
# Create SKILL.md...
```

Claude will load from:
1. Project skills: `.claude/skills/` (first)
2. Global skills: `~/projects/.claude/skills/` (fallback)

---

## 📊 Skill Categories

<details>
<summary><b>🧠 Psychology & Marketing (26 skills)</b></summary>

- consumer-psychology-skill
- emotional-triggers-skill
- behavioral-economics-skill
- cognitive-biases-skill
- dopamine-engineering-skill
- influence-weapons-skill (Cialdini)
- hypnotic-writing-skill (Milton Erickson)
- compliance-techniques-skill
- neuromarketing-skill
- persuasion-mastery-skill
- social-proof-mastery-skill
- reciprocity-psychology-skill
- authority-positioning-skill
- commitment-consistency-skill
- liking-similarity-skill
- subconscious-triggers-skill
- narrative-psychology-skill
- pricing-psychology-skill
- scarcity-urgency-skill
- objection-crushing-skill
- value-stacking-skill
- irresistible-offers-skill (Alex Hormozi)
- tribal-marketing-skill
- dark-psychology-skill (defense only)
- persuasion-psychology-skill
- subliminal-persuasion-skill

</details>

<details>
<summary><b>✍️ Copywriting & Content (11 skills)</b></summary>

- copywriting-formulas-skill (50+ formulas)
- sales-copywriting-skill
- email-mastery-skill
- landing-page-conversion-skill
- nlp-copywriting-skill
- content-marketing-skill
- seo-content-skill
- social-media-mastery-skill
- viral-content-skill
- storytelling-mastery-skill
- emotional-storytelling-skill

</details>

<details>
<summary><b>🎨 Branding & Strategy (7 skills)</b></summary>

- brand-voice-skill
- brand-positioning-skill
- brand-archetypes-skill (Jungian)
- brand-strategy-skill
- personal-branding-skill
- story-branding-skill (StoryBrand)
- story-selling-skill

</details>

<details>
<summary><b>🎬 Video & Production (6 skills)</b></summary>

- ai-video-prompting-skill (VEO3/Sora2/Runway)
- ffmpeg-video-processing-skill
- video-pipeline-skill
- whisper-transcription-skill
- tts-synthesis-skill
- invisible-selling-skill

</details>

<details>
<summary><b>💻 Technical & Development (10 skills)</b></summary>

- debug-methodology-skill (Codex)
- git-safety-skill
- automation-workflows-skill
- document-conversion-skill
- code-quality-standards-skill
- app-architecture-skill
- architecture-patterns-skill
- javascript-modern-skill (ES6+)
- python-best-practices-skill
- security-best-practices-skill

</details>

<details>
<summary><b>🎨 Design & UX (4 skills)</b></summary>

- design-systems-skill
- ui-ux-design-skill
- animation-microinteractions-skill
- modern-frontend-skill

</details>

<details>
<summary><b>📊 Marketing & Strategy (4 skills)</b></summary>

- marketing-strategy-skill
- funnel-optimization-skill
- paid-ads-skill
- facebook-ads-mastery-skill ⭐ NEW!

</details>

---

## 🌟 Key Features

### 1. **Automatic Loading**
No manual invocation needed - Claude detects and loads skills automatically.

### 2. **Multilingual Keywords**
Thai and English keywords supported for all major skills.

### 3. **Production-Ready**
All skills contain proven frameworks, real-world examples, and best practices.

### 4. **Expert Knowledge**
Based on established methodologies:
- Cialdini's Influence Principles
- Milton Erickson's Hypnotic Patterns
- Alex Hormozi's Offer Framework
- StoryBrand 7-Part Framework
- Codex Debugging Methodology

### 5. **Well-Documented**
Each skill includes:
- Clear descriptions
- Usage examples
- Integration guidelines
- Best practices
- Common pitfalls

---

## 📚 Documentation

- **CLAUDE.md**: Complete setup guide and usage rules
- **Skill SKILL.md files**: Individual skill documentation
- **This README**: Quick start and overview

---

## 🤝 Contributing

Want to add skills or improve existing ones?

1. Fork this repo
2. Create your skill in `.claude/skills/your-skill-name/`
3. Add YAML frontmatter with clear description
4. Include examples and frameworks
5. Submit a PR

---

## 📄 License

MIT License - Free to use, modify, and distribute.

---

## 💡 Tips

### Maximize Skill Effectiveness

1. **Use descriptive keywords** - "เขียนบทวิดีโอที่กินใจ" > "เขียนบท"
2. **Combine skills** - Claude can load multiple skills simultaneously
3. **Be specific** - "Fix bug in authentication" > "Fix bug"
4. **Ask for skill recommendations** - "What skills can help with X?"

### Discover Available Skills

```
You: "What skills are available?"
Claude: [Lists all 67 skills with descriptions]

You: "Show me skills about video"
Claude: [Lists video-related skills]

You: "Use storytelling-mastery-skill to write X"
Claude: [Loads that specific skill]
```

---

## 🎯 Use Cases

- **Content Creation**: Blogs, social media, email campaigns
- **Video Production**: Screenplays, AI prompts, editing workflows
- **Marketing**: Strategies, campaigns, conversion optimization
- **Copywriting**: Sales pages, landing pages, ads
- **Development**: Debugging, architecture, code quality
- **Branding**: Voice, positioning, storytelling

---

## ⚡ Performance

Skills are loaded on-demand:
- Fast: Only loads relevant skills
- Efficient: No overhead when not needed
- Smart: Context-aware selection

---

## 🔗 Links

- [Claude Code Documentation](https://docs.claude.com/en/docs/claude-code)
- [Skills Guide](https://docs.claude.com/en/docs/claude-code/skills)
- [CLAUDE.md Best Practices](https://docs.claude.com/en/docs/claude-code/claude-md)

---

## ✅ Status

- **Skills**: 68/68 complete ✅
- **Thai Keywords**: Top 20 skills ✅
- **Documentation**: Complete ✅
- **Testing**: Production-ready ✅

---

**Created with Claude Code** 🤖

https://claude.com/claude-code
