# คำสั่งสำหรับ Claude Code

---

## 🔄 AUTO-UPDATE TO GITHUB (สำคัญ!)

**กฎสำคัญ:** เมื่อมีการแก้ไข update ใดๆ ใน CLAUDE.md หรือ skills ให้ **update ไปที่ GitHub อัตโนมัติทันทีทุกครั้ง**

### เมื่อแก้ไข CLAUDE.md หรือ README.md:
```bash
cd /home/u-and-an/projects
git add CLAUDE.md README.md PUSH_TO_GITHUB.md .gitignore .gitmodules
git commit -m "docs: Update global configuration

🤖 Generated with Claude Code
https://claude.com/claude-code"
git push origin main
```

### เมื่อเพิ่ม/แก้ไข Skills:
```bash
# 1. Update skills repo first
cd /home/u-and-an/projects/.claude/skills
git add .
git commit -m "feat: Add/update skill content

🤖 Generated with Claude Code
https://claude.com/claude-code"
git push origin main

# 2. Update config repo to reference new version
cd /home/u-and-an/projects
git add .claude/skills
git commit -m "chore: Update skills submodule to latest

🤖 Generated with Claude Code
https://claude.com/claude-code"
git push origin main
```

### เมื่อทำทั้งสองอย่าง:
```bash
# 1. Skills first
cd /home/u-and-an/projects/.claude/skills
git add .
git commit -m "feat: Add new skill

🤖 Generated with Claude Code
https://claude.com/claude-code"
git push origin main

# 2. Config second
cd /home/u-and-an/projects
git add .
git commit -m "feat: Update CLAUDE.md and skills

🤖 Generated with Claude Code
https://claude.com/claude-code"
git push origin main
```

**หมายเหตุ:**
- ✅ ใช้ commit message ที่ชัดเจน (feat:, docs:, chore:)
- ✅ ระบุว่าแก้อะไร
- ✅ Push ทันทีหลัง commit
- ✅ Update skills ก่อน config เสมอ

---

## 🎯 GLOBAL SKILLS SYSTEM (ใช้ทุกโปรเจค)

> **ความเป็นจริง:** Skills เป็น **Knowledge Base** (SKILL.md files) ที่ Claude โหลดอัตโนมัติ
>
> **วิธีการทำงาน:** Claude ตัดสินใจเองว่าควรใช้ skill ไหน โดยดูจาก:
> 1. User request (คำขอของคุณ)
> 2. Skill description (คำอธิบายใน YAML frontmatter)
>
> **Skills location:** `/home/u-and-an/projects/.claude/skills/` (76 skills พร้อมใช้)
>
> **ไม่มี Skill tool:** ❌ ไม่มี `Skill(command: "name")` - Claude โหลดเอง **อัตโนมัติ**

---

### 🔥 Top 20 Skills (ใช้บ่อยที่สุด)

**เมื่อทำงานใดๆ → ตรวจสอบ keywords ด้านล่าง → ถ้าตรง → เรียก skill ทันที!**

> **💡 สำคัญ:** Keywords รองรับทั้ง **ภาษาอังกฤษ** และ **ภาษาไทย**!

#### 🎬 Content & Video Production

1. **`ai-video-prompting-skill`** ⭐⭐⭐
   - **EN:** `"video prompt", "VEO3", "Sora2", "Runway", "text-to-video", "AI video", "generate video"`
   - **TH:** `"พรอมต์วิดีโอ", "สร้างวิดีโอ", "AI วิดีโอ", "วิดีโอ AI", "เขียนพรอมต์"`

2. **`ffmpeg-video-processing-skill`** ⭐⭐⭐
   - **EN:** `"ffmpeg", "video editing", "concat", "replace audio", "video processing", "merge video"`
   - **TH:** `"ตัดต่อวิดีโอ", "รวมวิดีโอ", "เปลี่ยนเสียง", "แทนเสียง", "ประมวลผลวิดีโอ", "ต่อวิดีโอ"`

3. **`storytelling-mastery-skill`** ⭐⭐⭐
   - **EN:** `"story", "narrative", "screenplay", "character arc", "plot", "script writing"`
   - **TH:** `"เรื่องราว", "เขียนบท", "สคริปต์", "บทวิดีโอ", "โครงเรื่อง", "พล็อต", "ตัวละคร", "เขียนเนื้อเรื่อง"`

4. **`emotional-storytelling-skill`** ⭐⭐⭐
   - **EN:** `"emotional journey", "emotional arc", "feelings", "character emotion", "emotional impact"`
   - **TH:** `"อารมณ์", "ความรู้สึก", "จังหวะอารมณ์", "ดึงอารมณ์", "กินใจ", "สะเทือนใจ", "เรื่องราวสะเทือนใจ"`

---

#### 🧠 Psychology & Persuasion

5. **`consumer-psychology-skill`** ⭐⭐⭐
   - **EN:** `"customer pain", "buying decision", "motivation", "customer behavior", "pain point"`
   - **TH:** `"ปัญหาลูกค้า", "จุดเจ็บ", "ความเจ็บปวด", "พฤติกรรมลูกค้า", "จิตวิทยาลูกค้า", "ทำไมลูกค้าซื้อ", "แรงจูงใจ"`

6. **`emotional-triggers-skill`** ⭐⭐⭐
   - **EN:** `"emotional", "resonance", "connection", "emotional appeal", "touch hearts"`
   - **TH:** `"กระตุ้นอารมณ์", "จุดอ่อน", "สัมผัสใจ", "เข้าถึงอารมณ์", "โดนใจ", "สะเทือนอารมณ์"`

7. **`cognitive-biases-skill`** ⭐⭐
   - **EN:** `"bias", "social proof", "scarcity", "anchoring", "FOMO", "herd mentality"`
   - **TH:** `"อคติ", "หลักฐานทางสังคม", "คนอื่นใช้", "ขาดแคลน", "เหลือน้อย", "กลัวพลาด", "ตามกระแส"`

8. **`influence-weapons-skill`** ⭐⭐
   - **EN:** `"influence", "persuasion", "Cialdini", "reciprocity", "authority", "liking"`
   - **TH:** `"โน้มน้าว", "ชักจูง", "สร้างอิทธิพล", "การตอบแทน", "ผู้เชี่ยวชาญ", "อำนาจ", "ความน่าเชื่อถือ"`

---

#### ✍️ Copywriting & Content

9. **`copywriting-formulas-skill`** ⭐⭐⭐
   - **EN:** `"headline", "CTA", "hook", "AIDA", "PAS", "copywriting", "call to action"`
   - **TH:** `"หัวข้อ", "พาดหัว", "ข้อความโฆษณา", "เขียนขาย", "เขียนโฆษณา", "เขียนคำโฆษณา", "ปุ่มกดซื้อ", "เรียกร้องให้ลงมือ"`

10. **`content-marketing-skill`** ⭐⭐
    - **EN:** `"content strategy", "editorial calendar", "content distribution", "content plan"`
    - **TH:** `"กลยุทธ์เนื้อหา", "แผนเนื้อหา", "ปฏิทินเนื้อหา", "โพสต์อะไร", "วางแผนคอนเทนต์", "กระจายเนื้อหา"`

11. **`invisible-selling-skill`** ⭐⭐
    - **EN:** `"soft sell", "education-based", "value-first", "not salesy", "consultative selling"`
    - **TH:** `"ขายแบบไม่เหมือนขาย", "ให้ความรู้", "ให้คุณค่า", "ไม่ขายดาษๆ", "ขายแบบนุ่มนวล", "ให้ก่อนขาย"`

12. **`sales-copywriting-skill`** ⭐⭐
    - **EN:** `"sales copy", "sales page", "conversion copy", "landing page", "sales letter"`
    - **TH:** `"เขียนขาย", "หน้าขาย", "ปิดการขาย", "เพจขาย", "คอปี้ขาย", "ข้อความขาย", "Landing Page"`

---

#### 🎨 Branding & Design

13. **`brand-voice-skill`** ⭐⭐
    - **EN:** `"brand voice", "tone", "brand consistency", "messaging", "brand personality"`
    - **TH:** `"เสียงแบรนด์", "น้ำเสียง", "บุคลิกแบรนด์", "การสื่อสาร", "ความสอดคล้อง", "ลีลาการพูด"`

14. **`brand-positioning-skill`** ⭐⭐
    - **EN:** `"positioning", "differentiation", "competitive analysis", "unique value"`
    - **TH:** `"ตำแหน่งแบรนด์", "จุดแตกต่าง", "ความแตกต่าง", "วิเคราะห์คู่แข่ง", "จุดขาย", "คุณค่าเฉพาะตัว"`

15. **`design-systems-skill`** ⭐
    - **EN:** `"design system", "component library", "design tokens", "UI components"`
    - **TH:** `"ระบบดีไซน์", "คอมโพเนนต์", "ห้องสมุดดีไซน์", "ส่วนประกอบ UI"`

---

#### 💻 Technical Skills

16. **`debug-methodology-skill`** ⭐⭐⭐
    - **EN:** `"bug", "error", "unexpected behavior", "wrong result", "not working", "broken"`
    - **TH:** `"บั๊ก", "ข้อผิดพลาด", "เออเรอร์", "ไม่ทำงาน", "ทำงานผิด", "มีปัญหา", "พัง", "เพี้ยน", "ผิดปกติ"`

17. **`git-safety-skill`** ⭐⭐
    - **EN:** `"git", "commit", "branch", "backup", "merge", "version control"`
    - **TH:** `"คอมมิท", "แบรนช์", "สำรองข้อมูล", "รวมโค้ด", "ควบคุมเวอร์ชัน", "เซฟโค้ด"`

18. **`automation-workflows-skill`** ⭐⭐
    - **EN:** `"automation", "batch processing", "workflow", "script", "automate"`
    - **TH:** `"ทำให้อัตโนมัติ", "อัตโนมัติ", "ประมวลผลหลายไฟล์", "ลำดับงาน", "สคริปต์", "ทำงานซ้ำ", "ลดขั้นตอน"`

19. **`document-conversion-skill`** ⭐⭐
    - **EN:** `"convert", "PDF", "markdown to PDF", "HTML to PDF", "export", "document"`
    - **TH:** `"แปลง", "แปลงเอกสาร", "ไฟล์ PDF", "ส่งออก", "เปลี่ยนเป็น PDF", "Markdown เป็น PDF"`

20. **`code-quality-standards-skill`** ⭐
    - **EN:** `"code quality", "refactoring", "clean code", "SOLID", "best practices", "code review"`
    - **TH:** `"คุณภาพโค้ด", "ปรับปรุงโค้ด", "โค้ดสะอาด", "เขียนโค้ดให้ดี", "รีแฟคเตอร์"`

---

#### 📊 Marketing & Advertising

21. **`facebook-ads-mastery-skill`** ⭐⭐⭐ (NEW!)
    - **EN:** `"Facebook Ads", "FB Ads", "campaign strategy", "interest targeting", "lookalike audience", "retargeting", "pixel", "ROAS", "CPA", "ad creative", "conversion tracking", "A/B testing", "scaling ads", "Meta Ads"`
    - **TH:** `"โฆษณาเฟซบุ๊ก", "โฆษณาเฟส", "ลงแอด", "ลงโฆษณา FB", "กลุ่มเป้าหมาย", "วิเคราะห์แอด", "ยอดขายจากแอด", "ต้นทุนต่อลูกค้า", "เพิ่มยอดขาย", "สเกลแอด", "ทดสอบโฆษณา", "Pixel", "วัดผลโฆษณา"`

---

#### 🌍 Language & Communication

22. **`professional-translation-skill`** ⭐⭐⭐ (NEW!)
    - **EN:** `"translate", "translation", "Thai to English", "English to Thai", "Chinese to Thai", "Thai to Chinese", "English to Chinese", "Chinese to English", "translate document", "translate book", "translate article", "translate conversation", "translate script", "subtitle translation", "transcription translation"`
    - **TH:** `"แปล", "แปลภาษา", "แปลไทยเป็นอังกฤษ", "แปลอังกฤษเป็นไทย", "แปลจีนเป็นไทย", "แปลไทยเป็นจีน", "แปลอังกฤษเป็นจีน", "แปลจีนเป็นอังกฤษ", "แปลเอกสาร", "แปลหนังสือ", "แปลบทความ", "แปลบทสนทนา", "แปลสคริปต์", "แปลซับไตเติ้ล", "ถอดเสียง", "แปลบทประชุม"`

---

#### 🎨 Web Design & Development

23. **`web-psychology-design-skill`** ⭐⭐⭐ (NEW!)
    - **EN:** `"web design", "website design", "web app", "landing page", "UX psychology", "conversion design", "persuasive design", "high-converting website", "psychology-driven design", "user psychology", "conversion optimization", "CRO", "A/B testing", "visual hierarchy", "color psychology", "typography psychology", "CTA design", "form optimization", "trust signals", "social proof design"`
    - **TH:** `"ออกแบบเว็บ", "ออกแบบเว็บไซต์", "สร้างเว็บ", "สร้างเว็บแอป", "หน้าแลนดิ้งเพจ", "จิตวิทยาการออกแบบเว็บ", "เว็บที่ขายดี", "เว็บแปลงยอดสูง", "ออกแบบให้ปิดการขาย", "เพิ่มยอดขายเว็บ", "ปุ่มกดซื้อ", "ฟอร์มที่ดี", "สีที่ขายดี", "จิตวิทยาสี", "โครงสร้างหน้าเว็บ", "UX ที่ดี", "A/B testing"`

---

#### 🚀 Advanced Marketing & Business Skills (6 NEW!)

24. **`api-wrapper-saas-skill`** ⭐ NEW!
    - **EN:** `"API Gateway", "API Wrapper", "API Proxy", "API Reselling", "SaaS on API", "wrapping APIs", "OpenAI wrapper", "Anthropic wrapper", "API monetization", "usage-based pricing", "API key management", "rate limiting", "multi-provider routing"`
    - **TH:** `"API Gateway", "ห้อ API", "ขาย API", "ทำ SaaS จาก API", "ต่อ API", "เปลี่ยน API", "ขายต่อ API", "จัดการ API key", "กำหนดอัตรา", "หลายผู้ให้บริการ"`
    - **Summary:** Master API Wrapper/Reselling business models - building profitable SaaS on existing APIs (1,245 lines)

25. **`gamification-mastery-skill`** ⭐ NEW!
    - **EN:** `"gamification", "points badges leaderboards", "progression mechanics", "reward schedules", "habit formation", "player types", "Bartle taxonomy", "achievement design", "engagement loops", "retention optimization", "variable rewards", "dopamine engineering"`
    - **TH:** `"เกมมิฟิเคชั่น", "คะแนน ตรา ลีดเดอร์บอร์ด", "ระบบความก้าวหน้า", "ตารางรางวัล", "การสร้างนิสัย", "ประเภทผู้เล่น", "การออกแบบความสำเร็จ", "ลูปการมีส่วนร่วม", "การเก็บรักษา", "รางวัลแปรผัน"`
    - **Summary:** Advanced gamification with Octalysis framework, behavioral psychology (2,195 lines - largest skill!)

26. **`sales-funnel-mastery-skill`** ⭐ NEW!
    - **EN:** `"sales funnel", "Russell Brunson", "Value Ladder", "Perfect Webinar", "DotCom Secrets", "funnel hacking", "tripwire funnel", "webinar funnel", "high-ticket funnel", "funnel economics", "ascension path", "customer journey"`
    - **TH:** `"ช่องทางการขาย", "กระบวนการขาย", "ขั้นบันไดมูลค่า", "เว็บบินาร์สมบูรณ์แบบ", "กระบวนการขายออนไลน์", "ทริปไวร์", "เส้นทางลูกค้า", "ขายของแพง"`
    - **Summary:** Russell Brunson's sales funnel methodologies - Value Ladder, Perfect Webinar (1,497 lines)

27. **`lead-generation-mastery-skill`** ⭐ NEW!
    - **EN:** `"lead generation", "lead magnet", "landing page", "lead scoring", "BANT", "CHAMP", "MEDDIC", "lead nurturing", "email sequences", "conversion optimization", "lead qualification", "marketing automation"`
    - **TH:** `"สร้างลีด", "ดึงดูดลูกค้า", "แม่เหล็กลีด", "หน้าแลนดิ้ง", "คะแนนลีด", "บำรุงลีด", "ลำดับอีเมล", "คุณสมบัติลีด", "อัตโนมัติการตลาด"`
    - **Summary:** Advanced lead generation - 10+ lead magnet types, 30-60% conversion landing pages (1,501 lines)

28. **`product-launch-mastery-skill`** ⭐ NEW!
    - **EN:** `"product launch", "Jeff Walker", "PLF", "Product Launch Formula", "launch neuroscience", "dopamine engineering", "social proof cascade", "scarcity mechanics", "pre-launch buzz", "launch sequence", "sideways sales letter"`
    - **TH:** `"เปิดตัวผลิตภัณฑ์", "สูตรเปิดตัว", "ประสาทวิทยาการเปิดตัว", "โดพามีน", "น้ำตกหลักฐานสังคม", "กลไกความขาดแคลน", "ก่อนเปิดตัว", "ลำดับเปิดตัว"`
    - **Summary:** Jeff Walker's PLF + launch neuroscience, psychology-driven launching (1,418 lines)

29. **`viral-marketing-mastery-skill`** ⭐ NEW!
    - **EN:** `"viral marketing", "Jonah Berger", "STEPPS", "Social Currency", "Triggers", "Emotion", "Public", "Practical Value", "Stories", "word-of-mouth", "viral coefficient", "shareability", "memetic design", "network effects"`
    - **TH:** `"การตลาดไวรัล", "ปากต่อปาก", "แชร์ต่อ", "สกุลเงินทางสังคม", "ตัวกระตุ้น", "อารมณ์", "สาธารณะ", "มูลค่าที่ใช้ได้จริง", "เรื่องราว", "สัมประสิทธิ์ไวรัล", "การแชร์", "ผลกระทบเครือข่าย"`
    - **Summary:** Jonah Berger's STEPPS framework, viral coefficient optimization K > 1.0 (1,929 lines)

**Total:** 9,785 lines of advanced knowledge added!

---

### 🇹🇭 Thai Keywords Mapping (สรุป)

**สำหรับ Skills ที่ใช้บ่อยสุด:**

| English | Thai (คำพูดจริง) |
|---------|------------------|
| **Copywriting** | เขียนข้อความ, เขียนคำโฆษณา, เขียนโฆษณา, เขียนขาย |
| **Screenplay** | เขียนบท, สคริปต์, บทวิดีโอ, เนื้อเรื่อง |
| **Pain point** | ปัญหาลูกค้า, จุดเจ็บ, ความเจ็บปวด, ความทุกข์ |
| **Emotional** | อารมณ์, ความรู้สึก, กินใจ, สะเทือนใจ, โดนใจ |
| **Story** | เรื่องราว, โครงเรื่อง, เนื้อเรื่อง |
| **Video prompt** | พรอมต์วิดีโอ, สร้างวิดีโอ, เขียนพรอมต์ |
| **Bug** | บั๊ก, ข้อผิดพลาด, ไม่ทำงาน, พัง, เพี้ยน |
| **Headline** | หัวข้อ, พาดหัว, ข้อความดึงดูด |
| **Persuasion** | โน้มน้าว, ชักจูง, ทำให้เชื่อ |
| **Convert** | แปลง, แปลงเอกสาร, เปลี่ยนเป็น |

---

### 📋 Full Skills List (76 Skills)

<details>
<summary><b>คลิกเพื่อดูรายชื่อ skills ทั้งหมด (76 skills)</b></summary>

#### 🧠 Psychology & Marketing (26 skills)
- `consumer-psychology-skill`
- `emotional-triggers-skill`
- `behavioral-economics-skill`
- `cognitive-biases-skill`
- `dark-psychology-skill` (defense only)
- `dopamine-engineering-skill`
- `influence-weapons-skill`
- `hypnotic-writing-skill`
- `compliance-techniques-skill`
- `neuromarketing-skill`
- `persuasion-mastery-skill`
- `persuasion-psychology-skill`
- `social-proof-mastery-skill`
- `reciprocity-psychology-skill`
- `authority-positioning-skill`
- `commitment-consistency-skill`
- `liking-similarity-skill`
- `subconscious-triggers-skill`
- `subliminal-persuasion-skill`
- `narrative-psychology-skill`
- `pricing-psychology-skill`
- `scarcity-urgency-skill`
- `objection-crushing-skill`
- `value-stacking-skill`
- `irresistible-offers-skill`
- `tribal-marketing-skill`

#### ✍️ Copywriting & Content (11 skills)
- `copywriting-formulas-skill`
- `sales-copywriting-skill`
- `email-mastery-skill`
- `landing-page-conversion-skill`
- `nlp-copywriting-skill`
- `content-marketing-skill`
- `seo-content-skill`
- `social-media-mastery-skill`
- `viral-content-skill`
- `storytelling-mastery-skill`
- `emotional-storytelling-skill`

#### 🎨 Branding & Strategy (7 skills)
- `brand-voice-skill`
- `brand-positioning-skill`
- `brand-archetypes-skill`
- `brand-strategy-skill`
- `personal-branding-skill`
- `story-branding-skill`
- `story-selling-skill`

#### 🎬 Video & Production (6 skills)
- `ai-video-prompting-skill` ⭐⭐⭐
- `ffmpeg-video-processing-skill` ⭐⭐⭐
- `video-pipeline-skill`
- `whisper-transcription-skill`
- `tts-synthesis-skill`
- `invisible-selling-skill`

#### 💻 Technical & Development (10 skills)
- `debug-methodology-skill` ⭐⭐⭐
- `git-safety-skill` ⭐⭐
- `automation-workflows-skill`
- `document-conversion-skill`
- `code-quality-standards-skill`
- `app-architecture-skill`
- `architecture-patterns-skill`
- `javascript-modern-skill`
- `python-best-practices-skill`
- `security-best-practices-skill`

#### 🎨 Design & UX (4 skills)
- `design-systems-skill`
- `ui-ux-design-skill`
- `animation-microinteractions-skill`
- `modern-frontend-skill`

#### 📊 Marketing & Strategy (10 skills)
- `marketing-strategy-skill`
- `funnel-optimization-skill`
- `paid-ads-skill`
- `facebook-ads-mastery-skill` ⭐ NEW!
- `api-wrapper-saas-skill` ⭐ NEW!
- `gamification-mastery-skill` ⭐ NEW!
- `sales-funnel-mastery-skill` ⭐ NEW!
- `lead-generation-mastery-skill` ⭐ NEW!
- `product-launch-mastery-skill` ⭐ NEW!
- `viral-marketing-mastery-skill` ⭐ NEW!

#### 🌍 Language & Communication (1 skill)
- `professional-translation-skill` ⭐ NEW!

#### 🎨 Web Design & Development (1 skill)
- `web-psychology-design-skill` ⭐ NEW!

</details>

---

### 🚀 How It Works (วิธีการทำงานจริง)

**1. User ถามคำถาม/ให้งาน**
```
User: "สร้าง screenplay สำหรับวิดีโอ pain point"
```

**2. Claude อ่าน skill descriptions**
```
Claude อ่าน YAML frontmatter ของทุก skill:

storytelling-mastery-skill:
  description: "Use for: screenplay, character arc, plot..."

consumer-psychology-skill:
  description: "Use for: pain point, customer behavior..."
```

**3. Claude เลือก skills ที่เหมาะสม**
```
Match found:
- storytelling-mastery-skill (มี "screenplay")
- consumer-psychology-skill (มี "pain point")
```

**4. Claude โหลด SKILL.md อัตโนมัติ**
```
Loading: /home/u-and-an/projects/.claude/skills/storytelling-mastery-skill/SKILL.md
Loading: /home/u-and-an/projects/.claude/skills/consumer-psychology-skill/SKILL.md
```

**5. Claude ใช้ความรู้จาก skills สร้างผลลัพธ์**
```
Output: Screenplay with:
- Three-act structure (จาก storytelling-mastery-skill)
- Authentic pain points (จาก consumer-psychology-skill)
- Emotional arc (จาก emotional-storytelling-skill)
```

---

### ✅ สำหรับผู้ใช้ (User)

**Option 1: ปล่อยให้ Claude ตัดสินใจเอง (แนะนำ)**
```
User: "เขียนบทวิดีโอให้หน่อย"
Claude: [โหลด storytelling-mastery-skill อัตโนมัติ]
        [เขียนบทตาม principles ใน skill]
```

**Option 2: บอก skill ที่ต้องการ (ถ้าต้องการควบคุม)**
```
User: "ใช้ storytelling-mastery-skill เขียนบทให้หน่อย"
Claude: [โหลด skill นั้นมาใช้แน่นอน]
```

**Option 3: ถามว่ามี skills อะไรบ้าง**
```
User: "มี skills อะไรบ้าง?"
Claude: [แสดงรายชื่อ 70 skills พร้อมคำอธิบาย]
```

**ข้อดี:**
- ✅ ไม่ต้องจำว่ามี skill อะไรบ้าง
- ✅ Claude เลือก skills ที่เหมาะสมให้เอง
- ✅ ใช้ความรู้จากหลาย skills พร้อมกัน
- ✅ คุณภาพสูงกว่าตอบแบบปกติ

**ข้อจำกัด:**
- ⚠️ คำอธิบายใน description ต้องชัดเจน
- ⚠️ Claude เลือกตาม keywords → ถ้าคำขอคลุมเครือ อาจเลือก skill ผิด

---

### 📍 Skill Location & Structure

```bash
# Project skills (shared via git):
/home/u-and-an/projects/.claude/skills/

# Personal skills (not shared):
~/.claude/skills/

# List all skills:
ls -1 /home/u-and-an/projects/.claude/skills/

# Total: 76 skills ready to use
```

**โครงสร้างแต่ละ skill:**
```
skill-name/
├── SKILL.md           # ← Main content (required)
│   └── YAML frontmatter:
│       name: skill-name
│       description: "What it does + when to use"
│
└── assets/            # ← Optional support files
    ├── templates/
    ├── examples/
    └── checklists/
```

**ตัวอย่าง YAML frontmatter:**
```yaml
---
name: storytelling-mastery-skill
description: Master narrative craft for marketing and copywriting. Use for: three-act structure, Hero's Journey, character development, conflict creation, emotional arcs, hook-build-payoff, story-based objection handling, and 50+ storytelling techniques.
---
```

**หลักการสำคัญ:**
- 📝 `description` คือกุญแจ → ต้องชัดเจนว่า skill นี้ใช้เมื่อไหร่
- 🎯 ระบุ keywords ที่ trigger skill (เช่น "screenplay", "pain point")
- 📚 Content ใน SKILL.md = ความรู้ที่ Claude จะนำไปใช้

---

### 🔧 Project-Specific Skills

**ถ้าโปรเจคต้องการ skills เฉพาะ:**

```bash
# สร้าง skill ในโปรเจค:
your-project/.claude/skills/custom-skill/SKILL.md

# Claude จะโหลดจาก:
# 1. Project skills: .claude/skills/  (ก่อน)
# 2. Personal skills: ~/.claude/skills/  (ถ้าไม่เจอในโปรเจค)
```

**ตัวอย่าง:** `content-vdo/.claude/skills/` (ถ้ามี skills เฉพาะ video production)

**Override CLAUDE.md rules:**

สร้าง `CLAUDE.md` ในโปรเจคนั้น → เพิ่มกฎเฉพาะ → Claude จะใช้กฎนั้นเพิ่มเติม

**ตัวอย่าง:** `content-vdo/CLAUDE.md` (มีกฎเฉพาะสำหรับ AI video generation)

---

## การแปลงเอกสาร (Markdown → PDF, HTML → PDF)

เมื่อต้องแปลงเอกสาร ให้ใช้ Python พิเศษนี้เสมอ:

```bash
~/projects/.venv-docs/bin/python script.py
```

**ห้าม** ใช้แค่ `python script.py` เพราะจะไม่มี WeasyPrint/Pandoc

## สำหรับเอกสารภาษาไทย - สำคัญ!

เมื่อแปลงเอกสารที่มีภาษาไทย ต้องทำดังนี้:

### 1. ใช้ CSS สำหรับฟอนต์ภาษาไทย
```python
from weasyprint import HTML, CSS

thai_css = CSS(string='''
    @import url('https://fonts.googleapis.com/css2?family=Sarabun:wght@400;700&display=swap');

    body {
        font-family: 'Sarabun', 'Noto Sans Thai', sans-serif !important;
        line-height: 1.8;
        font-size: 14pt;
    }

    h1, h2, h3 {
        font-family: 'Sarabun', 'Noto Sans Thai', sans-serif !important;
    }
''')

HTML('input.md').write_pdf('output.pdf', stylesheets=[thai_css])
```

### 2. ระบุ encoding UTF-8
```python
with open('file.md', 'r', encoding='utf-8') as f:
    content = f.read()
```

---

## 🎯 วิธีแปลง Markdown → PDF ให้ภาษาไทยแสดงผลถูกต้อง (Proven Method)

### ปัญหาที่พบ
- แปลง Markdown → PDF โดยตรง → **ภาษาไทยมองไม่เห็น**
- สาเหตุ: ฟอนต์ไม่ถูกฝังหรือโหลดไม่ทัน

### ✅ วิธีที่ใช้ได้ผล (3 ขั้นตอน)

**ขั้นตอนที่ 1: ตรวจสอบ Encoding**
```bash
python scripts/ensure_utf8_bom.py <file.md>
```

**ขั้นตอนที่ 2: แปลง Markdown → HTML (พร้อมฟอนต์ไทย)**
```python
~/projects/.venv-docs/bin/python -c "
import markdown
from pathlib import Path

# Read markdown
input_path = Path('input.md')
with open(input_path, 'r', encoding='utf-8-sig') as f:
    md_content = f.read()

# Convert to HTML
html_content = markdown.markdown(md_content, extensions=['tables', 'fenced_code'])

# Create full HTML with Thai fonts
full_html = f'''<!DOCTYPE html>
<html lang=\"th\">
<head>
    <meta charset=\"UTF-8\">
    <link href=\"https://fonts.googleapis.com/css2?family=Sarabun:wght@400;700&display=swap\" rel=\"stylesheet\">
    <style>
        @page {{ size: A4; margin: 2cm; }}
        body {{ font-family: 'Sarabun', 'Noto Sans Thai', sans-serif; line-height: 1.8; font-size: 14pt; }}
        h1, h2, h3 {{ font-family: 'Sarabun', sans-serif; font-weight: 700; color: #2c3e50; }}
        h1 {{ font-size: 24pt; }} h2 {{ font-size: 20pt; }} h3 {{ font-size: 16pt; }}
        table {{ border-collapse: collapse; width: 100%; margin: 1em 0; }}
        th, td {{ border: 1px solid #ddd; padding: 8pt; text-align: left; }}
        th {{ background-color: #f2f2f2; font-weight: 700; }}
        blockquote {{ border-left: 4px solid #3498db; margin: 1em 0; padding-left: 1em; font-style: italic; }}
        hr {{ border: none; border-top: 2px solid #eee; margin: 2em 0; }}
    </style>
</head>
<body>
{html_content}
</body>
</html>'''

# Save HTML
html_path = Path('output.html')
with open(html_path, 'w', encoding='utf-8') as f:
    f.write(full_html)
"
```

**ขั้นตอนที่ 3: แปลง HTML → PDF**
```bash
~/projects/.venv-docs/bin/python -m weasyprint input.html output.pdf
```

### 🔑 Key Points
1. **ต้องแปลง MD → HTML ก่อน** (ไม่ใช่ MD → PDF โดยตรง)
2. **ต้องใส่ Google Fonts link** ใน `<head>` ของ HTML
3. **ต้องระบุ font-family** ใน CSS ทุกที่ (body, h1-h6)
4. **ใช้ WeasyPrint CLI** (`-m weasyprint`) ไม่ใช่ Python API

### ตัวอย่างคำสั่งเต็ม (One-liner)
```bash
# 1. Check encoding
python scripts/ensure_utf8_bom.py input.md

# 2. MD → HTML (ใช้สคริปต์ข้างบน)
~/projects/.venv-docs/bin/python convert_md_to_html.py

# 3. HTML → PDF
~/projects/.venv-docs/bin/python -m weasyprint output.html output.pdf
```

### ✅ Verification
```bash
ls -lh output.pdf                    # ควรมีขนาด > 50 KB
file output.pdf                      # ควรเป็น "PDF document, version 1.7"
```

---

## 🔬 การ Debug และแก้ไขปัญหา (Codex Methodology)

**สำคัญ:** เมื่อเจอ bug หรือ unexpected behavior ต้องทำตามขั้นตอนนี้ **ทุกครั้ง**

### 1. **Trace Execution Flow** 🔍

❌ **อย่า assume ว่ารู้ปัญหาทันที!**

✅ **ต้องทำ:**
- ติดตาม code path ทีละขั้นตอน
- ใช้ `sed -n 'line_start,line_end p' file.py` เพื่ออ่าน code sections
- ใช้ `grep -n "function_name" file.py` เพื่อหา call sites
- ใช้ `python -c "import module; print(module.__file__)"` เพื่อยืนยัน import path

**ตัวอย่าง:**
```bash
# หา function ที่เรียกใช้
grep -n "process_chunk" chunk_processor.py

# อ่าน code section
sed -n '200,250p' chunk_processor.py

# ตรวจสอบ import path
python -c "import chunk_processor; print(chunk_processor.__file__)"
```

---

### 2. **Calculate Expected Values** 📐

**ต้องคำนวณ expected output ด้วย math เสมอ!**

```python
# Expected: 1189s (SRT target)
# Actual: 1396s (จาก ffprobe)
# Difference: +207s

# คำถาม: +207s มาจากไหน?
# → Trace backward เพื่อหา source
```

**Checklist:**
- [ ] คำนวณ expected result
- [ ] เปรียบเทียบ actual vs expected
- [ ] ถ้าต่างกัน → backtrack เพื่อหา root cause
- [ ] Validate ทุก intermediate value

---

### 3. **Validate Assumptions** ✓

❌ **อย่า assume code ทำงานถูกต้อง!**

✅ **ต้องทำ:**
- ตรวจสอบ return values
- ตรวจสอบ data flow
- ตรวจสอบ loop iterations
- ยืนยัน variable values

**ตัวอย่าง:**
```bash
# ตรวจสอบว่า loop ทำงานกี่รอบ
sed -n '658,678p' chunk_processor.py

# ตรวจสอบ indentation (spaces vs tabs)
cat -A chunk_processor.py | sed -n '660,665p'

# ตรวจสอบ return type
grep -A 5 "def process_chunk" chunk_processor.py
```

---

### 4. **Systematic Debugging Checklist** 📋

```bash
# ======================================
# Step 1: Understand the Problem
# ======================================
# - Expected result คืออะไร?
# - Actual result คืออะไร?
# - ต่างกันอย่างไร? เท่าไหร่?

# ======================================
# Step 2: Locate Code Path
# ======================================
grep -n "function_name" file.py
sed -n 'start,end p' file.py

# ======================================
# Step 3: Trace Execution
# ======================================
# - อ่าน code line by line
# - Track variable values
# - คำนวณ intermediate results

# ======================================
# Step 4: Identify Root Cause
# ======================================
# - อย่าหยุดที่ surface issues!
# - หา source ของ unexpected values
# - Validate ด้วย math

# ======================================
# Step 5: Verify Fix
# ======================================
# - คำนวณ expected result หลัง fix
# - Test กับ actual data
# - Confirm ว่า drift/values ตรง
```

---

### 5. **Common Pitfalls to Avoid** ⚠️

| ❌ **อย่าทำ** | ✅ **ต้องทำ** |
|---------------|---------------|
| คิดว่ารู้ปัญหาทันที | Trace complete flow |
| แก้ surface symptoms | Calculate expected values |
| Skip math validation | Validate every assumption |
| Assume code ถูกต้อง | Test with real data |
| Pattern matching alone | Deep analysis + math |
| Quick fix without understanding | Root cause analysis |

---

### 6. **Case Study #1: Double TimelineAwareMerger Bug** 📚

#### **ปัญหา:**
- Expected: 1189.9s
- Actual: 1396.6s
- Drift: **+206.7s (+17%)**

#### **❌ Bad Approach (Claude - ฉัน):**
```python
# 1. ดู code → เจอ indentation ที่ดูแปลก
# 2. คิดว่า: "อ้อ! process_chunk() นอก loop!"
# 3. แก้ indentation
# 4. คิดว่าเสร็จแล้ว ❌

# ปัญหา: วินิจฉัยผิด! ไม่ได้เจอ root cause
```

#### **✅ Good Approach (Codex):**
```python
# 1. Math analysis:
#    segments: 1031s
#    final: 1396s
#    silence: 1396 - 1031 = 365s ← มากเกินไป!

# 2. Trace flow:
#    - ChunkProcessor: ใส่ silence ที่ไหน?
#    - MasterProcessor: ใส่ silence ที่ไหน?

# 3. Discover:
#    merger1 = TimelineAwareMerger()  # ใน ChunkProcessor
#    merger1.add_segment() → ใส่ silence
#
#    merger2 = TimelineAwareMerger()  # ใน MasterProcessor
#    merger2.add_segment() → ใส่ silence อีกรอบ!

# 4. Root cause: Double merging!
#    - Chunk level: +182s
#    - Final level: +182s (ซ้ำ!)
#    - Total: ~365s ✓

# 5. Fix: ลบ chunk-level merger
#    → ใช้แค่ final merger ครั้งเดียว
```

#### **ผลลัพธ์:**
- Claude: แก้ indentation (ผิด!) → ยังมี bug
- Codex: แก้ double merger (ถูก!) → drift = 0%

---

### 7. **Case Study #2: Timeline Target Misunderstanding** 🚨

#### **ปัญหา:**
หลังแก้ double merger แล้ว เห็น output:
```
Target (timeline): 1396.6s
Target (segments): 1189.9s
Final drift: +0ms (+0.00%)
```

Claude คิดว่า: "1396.6s ≠ 1189.9s → เป็น bug!"

#### **❌ Bad Approach (Claude - ฉันอีกครั้ง!):**
```python
# 1. เห็นตัวเลขต่างกัน → คิดว่าเป็น bug ทันที
# 2. ไม่ได้ทำความเข้าใจ domain ก่อน
# 3. เกือบแก้ timeline_target_ms ให้ใช้ segment.end_ms
# 4. เกือบ commit fix ที่ผิด! ❌

# ปัญหา:
# - Pattern matching alone (เห็นเลขต่าง → assume bug)
# - ไม่เข้าใจว่า SRT มี timeline span vs segments duration
# - ไม่ได้คำนวณ expected behavior
```

#### **✅ Good Approach (Codex + User):**
```python
# Step 0: Understand the Domain (สำคัญที่สุด!)
# - SRT มี 2 ค่า:
#   1. Segments duration: 1189.9s (เวลาที่มีเสียงพูดจริง)
#   2. Timeline span: 1396.6s (first_start → last_end, รวมช่องว่าง)
#
# - Difference: 1396.6 - 1189.9 = 206.7s
# - นี่คือ gaps ระหว่าง segments ที่ต้องใส่กลับเข้าไปเพื่อซิงค์กับวิดีโอ!

# Step 1: Calculate Expected Behavior
# Synthesized segments: 1031.1s (เสียงจริง)
# Timeline span:         1396.6s (absolute time)
# Expected gaps:         1396.6 - 1031.1 = 365.5s
#
# TimelineAwareMerger ควรจะ:
#   - เอาเสียง 1031.1s
#   - ใส่ gaps 365.5s
#   - ได้ final 1396.6s

# Step 2: Validate with ffprobe
# ffprobe result: 1372.8s
# Actual gaps: 1372.8 - 1031.1 = 341.7s
# Missing: 365.5 - 341.7 = 23.8s ← MP3 encoding overhead (ยอมรับได้!)

# Step 3: Check Final Drift
# Final drift: +0ms (+0.00%) ✅
# Timeline alignment ทำงานสมบูรณ์!

# Step 4: Conclusion
# timeline_target_ms = 1396.6s ← ถูกต้องแล้ว!
# segment_target_ms  = 1189.9s ← ถูกต้องแล้ว!
# ไม่ต้องแก้อะไร! Don't fix what isn't broken!
```

#### **ผลลัพธ์:**
- Claude: เกือบแก้ timeline calculation (ผิด!) → จะทำให้ระบบพัง
- Codex: Validate ว่าถูกต้องแล้ว (ถูก!) → ไม่ต้องแก้!

#### **บทเรียนสำคัญ:**

**กฎใหม่ที่ต้องเพิ่ม:**
```
Step 0: UNDERSTAND THE DOMAIN FIRST! 🎯
======================================
ก่อนสรุปว่าเป็น bug ต้องถามตัวเองก่อน:

1. ค่าเหล่านี้หมายถึงอะไร?
   - Timeline span vs Segments duration แตกต่างกันอย่างไร?
   - มี semantic ที่แตกต่างกันหรือไม่?

2. ความต่างนี้เป็นไปตาม design หรือไม่?
   - ระบบออกแบบมาให้แตกต่างกันหรือเปล่า?
   - มีเหตุผลทางเทคนิคที่ต้องแตกต่างหรือไม่?

3. คำนวณ expected behavior
   - ถ้าระบบทำงานถูกต้อง ควรได้ค่าเท่าไหร่?
   - Math ออกมาตรงกับที่เห็นหรือไม่?

4. Validate against specification
   - Output ตรงกับ spec หรือไม่?
   - Final drift เป็น 0% หรือไม่?

❌ Different values ≠ Bug!
✅ Understand first, calculate second, then decide!
```

**ข้อผิดพลาดที่ต้องหลีกเลี่ยง:**
- ❌ เห็นเลขต่างกัน → สรุปเป็น bug ทันที
- ❌ ไม่เข้าใจ domain semantics
- ❌ ไม่คำนวณ expected behavior ก่อน assume
- ❌ แก้ code ที่ทำงานถูกต้องอยู่แล้ว
- ❌ Pattern matching โดยไม่ deep analysis

**สิ่งที่ต้องทำ:**
- ✅ Understand domain และ data model ก่อนเสมอ
- ✅ คำนวณ expected values ตาม specification
- ✅ Validate ว่า code ทำงานตรงตาม design หรือไม่
- ✅ ถ้าทำงานถูกต้องแล้ว → **Don't fix it!**

---

### 7. **Case Study #3: Codex WAV Pipeline Collaboration** 🤝

#### **สถานการณ์:**
หลังจาก Codex แก้ double merger bug แล้ว Timeline alignment ทำงาน (drift +0ms) แต่ผู้ใช้พบว่าเสียงไม่ตรงกับวิดีโอ:

```
Video duration: 1396.846s
Audio (MP3 mode): 1372.82s
Difference: -24.04s

ปัญหา: วิดีโอมี silent 24s ตอนท้าย
สาเหตุ: MP3 encoding frame rounding overhead
```

#### **Codex เสนอ Solution: WAV Pipeline**
```python
# Idea: แปลงเป็น WAV ก่อน concat → convert MP3 ทีเดียวตอนท้าย

Step 1: Convert all segments/silence to WAV
Step 2: Concat WAV files (no frame overhead)
Step 3: Convert final WAV → MP3 once
Result: Overhead reduced from 24s to ~0.024s (99% improvement!)
```

#### **❌ Bug แรก: Mixed Codec Problem**

Codex implementation แรก (commit f75037e):
```python
# TimelineAwareMerger in WAV mode:
silence_files = [silence_001.wav, silence_002.wav, ...]  # WAV format
segment_files = [seg0001.mp3, seg0002.mp3, ...]         # MP3 format ❌

# ffmpeg concat file:
file 'silence_001.wav'
file 'seg0001.mp3'  # ← Different codec!
file 'silence_002.wav'
file 'seg0002.mp3'  # ← Different codec!

# Result: ffmpeg concat demuxer ไม่สามารถ mix codecs → skip MP3 files
# Output: เฉพาะ silence (no segments!) → Duration 1031s instead of 1396s
```

#### **✅ Codex ซ้อมมือแก้: Segment Conversion**

Codex ทำการวินิจฉัยและแก้ไข (commit b7a722f):
```python
def _ensure_wav_copy(self, source_path: Path) -> Path:
    """
    Convert MP3 segments to WAV for consistent codec during concat.
    """
    if source_path.suffix.lower() == ".wav":
        return source_path  # Already WAV

    # Convert MP3 → WAV
    wav_path = source_path.with_suffix(".wav")
    subprocess.run([
        'ffmpeg', '-i', str(source_path),
        '-ar', '44100',  # 44.1kHz
        '-ac', '2',      # Stereo
        '-c:a', 'pcm_s16le',  # WAV codec
        '-y', str(wav_path)
    ], capture_output=True, check=True)

    return wav_path

def add_segment(self, audio_path, segment, actual_duration_ms):
    if self.output_format == "wav_then_mp3":
        # Convert MP3 segments to WAV BEFORE adding to list
        audio_path = self._ensure_wav_copy(audio_path)

    self.segment_files.append(audio_path)
    ...
```

**ผลลัพธ์:**
```
Test 1: MP3 mode (default)
  Duration: 1372.82s
  Timeline drift: +0ms ✅
  Backwards compatible: YES ✅

Test 2: WAV mode (after fix)
  Duration: 1396.61s
  Timeline drift: +0ms ✅
  Video sync: -0.24s (perfect!) ✅
```

#### **บทเรียนสำคัญ:**

**1. Trust But Verify** 🔍
```python
# Codex implementation ดูดี แต่ต้อง test ก่อนใช้งานจริง

Codex said: "WAV pipeline will work"
Reality: First version had bug (mixed codecs)
Codex response: Diagnosed and fixed quickly (commit b7a722f)

Key: Test thoroughly, even expert implementations!
```

**2. Backwards Compatibility First** 🛡️
```python
# Codex design ที่ดี:
def __init__(self, output_format: str = "mp3"):  # ← Default unchanged
    self.output_format = output_format

if self.output_format == "wav_then_mp3":
    # New feature (opt-in)
    ...
else:
    # Original behavior (default)
    ...

Result:
- Existing code works unchanged ✅
- New feature available if needed ✅
- Easy rollback if issues ✅
```

**3. Git Safety Procedures** 🔐
```bash
# ก่อนให้ Codex แก้ไข:
git checkout -b v11-codex-timeline-fix-backup
git push origin v11-codex-timeline-fix-backup

# ถ้า Codex แก้พัง:
git reset --hard origin/v11-codex-timeline-fix-backup

Result: ไม่กลัว Codex พังโค้ด เพราะมี backup เสมอ!
```

**4. Collaborative Debugging** 🤝
```
Codex Strengths:
✅ Quick implementation
✅ Systematic approach
✅ Self-correcting (found and fixed own bug)
✅ Good architecture (backwards compatible)

Claude Role:
✅ Test implementation
✅ Identify bugs (mixed codec issue)
✅ Provide diagnostic data (ls temp_v11/)
✅ Verify fixes work

Result: Faster than either working alone!
```

**5. Domain-Specific Knowledge Matters** 🎓
```
Why mixed codec failed:
- ffmpeg concat demuxer requires uniform format
- MP3 uses frames, WAV uses raw samples
- Cannot concat different codecs without re-encoding

Codex knew: WAV eliminates overhead
Codex missed: Segments were still MP3 (not converted)
Claude caught: Check temp files → found mixed formats

Lesson: Even experts need domain validation!
```

#### **ผลสรุป:**

**Before Codex collaboration:**
- Timeline alignment broken (double merger)
- Video sync poor (-24s)

**After Codex collaboration:**
- ✅ Timeline alignment perfect (0ms drift)
- ✅ Video sync perfect (-0.24s)
- ✅ Backwards compatible
- ✅ Production ready

**Success factors:**
1. Codex systematic approach
2. Claude thorough testing
3. Git safety procedures
4. Quick iteration (found bug → fixed in 1 commit)
5. Good communication (Claude provided diagnostic data)

**Time saved:**
- Manual debug: ~2-3 hours estimated
- With Codex: ~30 minutes (including bug fix)
- 75% time reduction! 🚀

---

### 7. **Case Study #4: Paperspace Production Success** 🎬

#### **สถานการณ์:**
ทำงานมาหลายวันไม่สำเร็จ วันนี้ใช้ Codex methodology แล้วสำเร็จใน Paperspace

**ปัญหาที่พบ:**
1. `bc: command not found` (Paperspace ไม่มี bc)
2. Path ไม่ตรง (คาดหวัง subfolder แต่จริงๆ อยู่ root)
3. Filename pattern ไม่ match (หา `*_agents.mp3` แต่ได้ `*_v11.mp3`)

#### **❌ Claude's Previous Approach (หลายวัน ไม่สำเร็จ):**
```python
# 1. พบ error → แก้แบบ quick fix
# 2. ไม่ได้ test environment ก่อน
# 3. Assume path structure เหมือน local
# 4. Hardcode filename patterns
# 5. ไม่มี error handling ที่ดี

Result: ใช้ไม่ได้ใน Paperspace ❌
```

#### **✅ Codex Methodology (วันนี้สำเร็จ):**

**Step 1: Understand Environment**
```bash
# ตรวจสอบว่า bc มีไหม
which bc  # ไม่มี!

# เช็ค Python (มีแน่นอน)
which python3  # มี!

Solution: ใช้ Python แทน bc ทุกที่
```

**Step 2: Validate Path Structure**
```bash
# เช็คว่าไฟล์อยู่ที่ไหนจริง
ls -la /notebooks/quantum-sync-v5/

# พบว่า: ไฟล์อยู่ root ไม่ใช่ subfolder!
# Local: /notebooks/quantum-sync-v5/quantum-sync-v11-production/
# Paperspace: /notebooks/quantum-sync-v5/  # ไม่มี subfolder

Solution: แก้ WORK_DIR และ OUTPUT_DIR
```

**Step 3: Debug Filename Pattern**
```bash
# Error: "Audio synthesis failed"
# แต่เห็น output: "✅ SUCCESS! Output saved to: .../Matthew_v11.mp3"

# เช็คจริง
ls output/

# พบ: ep-04-081024_english_Matthew_v11.mp3
# Pattern เดิม: *_${VOICE}_v11_agents.mp3  ❌
# Pattern ใหม่: *_${VOICE}_v11*.mp3  ✅

Solution: ใช้ wildcard ที่ยืดหยุ่นกว่า
```

**Step 4: Systematic Fixes**
```bash
# Fix 1: Replace bc with Python
DURATION_DIFF=$(python3 -c "print($SRT_DURATION - $VIDEO_DURATION)")

# Fix 2: Correct paths
WORK_DIR="${PROJECT_DIR}"  # Not subfolder in Paperspace
OUTPUT_DIR="${PROJECT_DIR}/output"

# Fix 3: Flexible pattern
OUTPUT_AUDIO=$(find output/ -name "*_${VOICE}_v11*.mp3" | head -1)

# Fix 4: Better error handling
if [ -z "$OUTPUT_AUDIO" ]; then
    echo "ERROR: No MP3 file found"
    ls -lh output/  # Show what's actually there
    exit 1
fi
```

**ผลลัพธ์:**
```
BEFORE (หลายวัน):
- bc errors ❌
- Path errors ❌
- File not found ❌
- ไม่รู้ว่าปัญหาอะไร

AFTER (วันนี้ - Codex method):
- ✅ Replace bc → Python
- ✅ Fix paths for Paperspace
- ✅ Flexible filename matching
- ✅ Production success!

Final Video:
- Video: 2567.807s
- Audio: 2567.784s
- Sync: -0.023s (PERFECT!)
- File: 902MB
```

#### **บทเรียนสำคัญ:**

**1. Test Environment First** 🧪
```bash
# ก่อนเขียน script ต้องเช็ค:
which bc          # มีหรือเปล่า?
which python3     # ทางเลือกอื่น?
pwd               # Path structure?
ls -la            # File locations?

Don't assume! Verify everything!
```

**2. Flexible Patterns** 🎯
```bash
# ❌ Rigid pattern
OUTPUT_AUDIO=$(find output/ -name "*_${VOICE}_v11_agents.mp3")

# ✅ Flexible pattern
OUTPUT_AUDIO=$(find output/ -name "*_${VOICE}_v11*.mp3" | head -1)

# ✅ With error handling
if [ -z "$OUTPUT_AUDIO" ]; then
    ls -lh output/  # Show what exists
    exit 1
fi
```

**3. Environment-Specific Code** 🔧
```bash
# Local structure:
WORK_DIR="${PROJECT_DIR}/quantum-sync-v11-production"

# Paperspace structure:
WORK_DIR="${PROJECT_DIR}"  # Files in root

Solution: Detect or document environment differences!
```

**4. Progressive Debugging** 📈
```
Error → Test → Fix → Test → Success

1. bc error → which bc → replace with Python ✅
2. path error → ls -la → fix paths ✅
3. file not found → ls output/ → fix pattern ✅

Systematic approach = Success!
```

#### **Why This Worked:**

**Codex Principles Applied:**
1. ✅ Understand environment (check commands, paths)
2. ✅ Validate assumptions (ls, which, test)
3. ✅ Calculate alternatives (bc → Python)
4. ✅ Flexible solutions (wildcards, error handling)
5. ✅ Test each fix (incremental progress)

**Time Comparison:**
- Manual trial-error: Several days ❌
- Codex methodology: 30 minutes ✅
- **Efficiency: 100x improvement!** 🚀

#### **Lessons for Future:**

**Always:**
- ✅ Check environment before coding
- ✅ Use flexible patterns
- ✅ Add diagnostic output
- ✅ Test incrementally
- ✅ Document environment differences

**Never:**
- ❌ Assume commands exist
- ❌ Hardcode paths
- ❌ Use rigid patterns
- ❌ Skip environment validation
- ❌ Deploy without testing

**Key Takeaway:**
> **"Test environment first, use flexible code, debug systematically"**

---

### 7. **Case Study #5: Modular Training R² Regression (Codex System Thinking)** 🧠

#### **สถานการณ์:**
Paperspace training ให้ R² = 0.36 แทนที่จะเป็น 0.90 (ลดลง 60%!)

**ปัญหา:**
- Expected: XGBoost R² ~0.90, RandomForest R² ~0.85
- Actual: Both R² ~0.36
- Training time: 2-3 hours (ปกติ) แต่ผลแย่มาก

#### **❌ Claude's Approach (Pattern Matching):**
```python
# 1. เห็นปัญหา: Missing market_stats
# 2. คิดทันที: "ต้อง implement market_stats calculation"
# 3. เขียนโค้ดใหม่ 30+ lines per file:

# Step 2A: Create preliminary split
train_indices, test_indices = train_test_split(...)

# Step 2B: Calculate market statistics MANUALLY
from src.data_handler import calculate_market_statistics, calculate_sample_weights
train_df = df_cleaned.iloc[train_indices].copy()
train_df = calculate_sample_weights(train_df, is_train=True)
market_stats = calculate_market_statistics(train_df)
df_cleaned = calculate_sample_weights(df_cleaned, is_train=False)
df_cleaned.iloc[train_indices, ...] = train_df['sample_weight'].values
...

# Result:
# - ✅ Works correctly
# - ❌ 30+ lines per file (×5 files = 150 lines!)
# - ❌ Code duplication (main.py already has this logic!)
# - ❌ Hard to maintain (must sync 6 files)
# - ❌ Violates DRY principle
```

#### **✅ Codex's Approach (System Thinking):**
```python
# Codex thought process:
# 0. "Wait! Does this logic exist somewhere?"
# 1. Scans codebase → Found run_feature_pipeline() in main.py
# 2. Decision: "REUSE IT!"

from training.main import run_feature_pipeline  # ← KEY!

# Simple 15-line solution:
price_bins = pd.qcut(df_cleaned['price'], q=5, labels=False, duplicates='drop')
train_indices, test_indices = train_test_split(
    np.arange(len(df_cleaned)),
    test_size=MODEL_CONFIG.get('test_size', 0.2),
    stratify=price_bins,
    random_state=MODEL_CONFIG.get('random_state', 42)
)

# ✅ Reuse existing pipeline (does everything automatically!)
X, y_log, sample_weights = run_feature_pipeline(
    df_cleaned,
    train_indices=train_indices
)
sample_weights = pd.Series(sample_weights, index=X.index)

# Use pre-calculated indices
X_train = X.iloc[train_indices]
X_test = X.iloc[test_indices]
...

# Result:
# - ✅ Works correctly
# - ✅ 15 lines per file (50% less code!)
# - ✅ No duplication (reuses main.py)
# - ✅ Easy to maintain (single source of truth)
# - ✅ Follows DRY principle
```

#### **ผลลัพธ์:**

**Code Quality:**
- Claude: 150 lines added, high duplication, hard maintenance
- Codex: 75 lines added, no duplication, easy maintenance
- **Codex wins 6-0** on implementation quality! 🏆

**Expected Results (both approaches):**
- XGBoost R²: 0.36 → ~0.90 (+150%)
- RandomForest R²: 0.36 → ~0.85 (+136%)

#### **บทเรียนสำคัญ:**

**New Principle: Step 0 - SCAN EXISTING SOLUTIONS FIRST!** ⭐

```
Step 0: SCAN EXISTING SOLUTIONS FIRST! 🔍
=========================================
Before implementing ANY solution, ask:

1. Does this logic exist elsewhere in codebase?
   → Check main.py, utils, existing functions
   → Use grep/search to find similar patterns

2. Can I reuse an existing function?
   → YES: Call it! (better)
   → NO: Implement new (only if necessary)

3. Would my solution create code duplication?
   → YES: Refactor to reuse existing code
   → NO: Proceed with implementation

❌ DON'T:
- Write new code when existing code solves it
- Duplicate logic across multiple files
- Jump to implementation without scanning

✅ DO:
- Scan codebase first (grep, search, read)
- Reuse existing, well-tested functions
- Follow DRY principle (Don't Repeat Yourself)
- Think about system architecture

"The best code is the code you don't have to write!"
```

**Comparison:**

| Approach | Claude (Pattern Matching) | Codex (System Thinking) |
|----------|---------------------------|-------------------------|
| **Mindset** | "What's missing?" | "What exists?" |
| **First Action** | Implement new code | Scan existing code |
| **Strategy** | Add from scratch | Reuse existing |
| **Code Quality** | ⚠️ Medium | ✅ High |
| **Maintenance** | Hard (6 files) | Easy (1 file) |
| **Lines Added** | ~150 lines | ~75 lines |

**Key Insight:**
> **Pattern Matching → Quick but Duplicative**
>
> **System Thinking → Slower Start but Better Architecture**
>
> **Always scan existing solutions before writing new code!**

**Time Comparison:**
- Manual debug: Would take days to find root cause
- Claude approach: Fix works but creates tech debt
- **Codex approach: Fix works AND improves codebase** 🚀

**Files Fixed:**
- `training/train_terminal.py`
- `training/modular/train_xgboost_only.py`
- `training/modular/train_lightgbm_only.py`
- `training/modular/train_catboost_only.py`
- `training/modular/train_rf_only.py`
- `training/modular/train_ensemble_only.py`

---

### 8. **Debugging Protocol Summary (Updated)** 🎯

**ทุกครั้งที่แก้ bug ต้องทำตามลำดับ:**

**0. ✅ UNDERSTAND THE DOMAIN FIRST!** ⭐ (เพิ่มใหม่!)
   - ค่าต่างๆ หมายถึงอะไร?
   - ความต่างเป็นไปตาม design หรือไม่?
   - คำนวณ expected behavior ตาม spec
   - Different values ≠ Bug!

1. ✅ **Trace execution flow** - ทีละ step, ไม่ข้าม
2. ✅ **Calculate expected values** - ด้วย math
3. ✅ **Compare actual vs expected** - หาความต่าง
4. ✅ **Backtrack to root cause** - ไปให้ถึง source
5. ✅ **Validate fix with test** - ทดสอบจริง

**ห้ามทำ:**
- ❌ Pattern matching alone (หา bug patterns ที่รู้จัก)
- ❌ Quick assumptions (สรุปเร็ว)
- ❌ Surface fixes (แก้อาการ ไม่ใช่สาเหตุ)
- ❌ Skip validation (ไม่ทดสอบ)
- ❌ **Assume different values = bug** (ใหม่!)

**Key Principles:**
> **"เข้าใจ domain ก่อน assume, คำนวณก่อน fix, validate ก่อน commit"**
>
> **"Don't fix what isn't broken!"**

---

### 9. **Quick Reference Commands** 💻

#### **💡 Tips: การแบ่งบรรทัดคำสั่งยาว**

**ถ้าคำสั่งยาว → ใช้ `\` ต่อท้ายบรรทัด:**

```bash
# ✅ ถูกต้อง - ใช้ backslash ต่อบรรทัด
ffprobe -v error \
  -show_entries format=duration \
  -of default=noprint_wrappers=1:nokey=1 \
  input_video.mp4

# ✅ ถูกต้อง - รันในบรรทัดเดียว
ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 input_video.mp4

# ❌ ผิด - กด Enter โดยไม่มี backslash
ffprobe -v error
  -show_entries format=duration
  input_video.mp4
```

**สังเกต:** `\` ต้องอยู่ท้ายบรรทัดทุกบรรทัด (ยกเว้นบรรทัดสุดท้าย)

---

#### **คำสั่งที่ใช้บ่อย:**

```bash
# Trace code flow
grep -rn "function_name" .
sed -n 'start,end p' file.py

# Validate math
python -c "print(1396 - 1031)"  # Calculate difference

# Check imports
python -c "import module; print(module.__file__)"

# Inspect values
cat -A file.py | sed -n 'start,end p'  # Show whitespace

# Clear cache (important!)
find . -name "*.pyc" -delete
find . -type d -name "__pycache__" -exec rm -rf {} +

# Verify result
ffprobe -v error -show_entries format=duration file.mp3

# Download from Google Drive (ใช้บรรทัดเดียว!)
gdown 11iYFzembTYUdZ45BYmDhQBvWe_wv5oY1 -O input_video.mp4
```

---

**สรุป: ทำตาม Codex methodology ทุกครั้ง = แก้ bug ได้ถูกต้องและรวดเร็ว!** 🚀
