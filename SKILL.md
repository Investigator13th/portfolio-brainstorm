---
name: portfolio-brainstorm
description: "Use this skill whenever the user wants to create, redesign, plan, or improve a personal homepage, portfolio website, resume site, internship/job-search landing page, academic profile site, or project showcase. This skill is especially relevant when the user says things like '个人主页怎么做', 'portfolio', 'personal website', '秋招/实习主页', '作品集网站', '帮我规划主页结构', or asks what content/style/sections their homepage should include. It guides a conversational, one-question-at-a-time discovery process and produces a clear homepage design direction before implementation."
---

# Portfolio Brainstorm

Help the user shape a personal homepage or portfolio site through natural dialogue. The goal is not to rush into code. The goal is to understand what the homepage must communicate, who will read it, and what design choices best support that purpose.

Use this skill for personal homepages, job-search sites, internship portfolios, academic profiles, developer portfolios, designer portfolios, project showcase pages, and lightweight resume landing pages.

## Core principle

A good personal homepage is not a decorative resume. It is a guided first impression.

Every design choice should answer one question:

> What should the visitor understand about this person within the first 30 seconds?

For job-search and internship contexts, prioritize clarity, credibility, and fast access to proof: education, experience, projects, resume, contact links, GitHub, and deployed work.

## Hard gate

Do not write code, scaffold a project, install dependencies, or create implementation files until the user has approved the homepage direction.

If the user explicitly asks to skip planning and build immediately, still do a very short alignment pass first: summarize the assumed structure and ask for confirmation unless the user has already provided enough detail.

## Workflow

Create and maintain a todo list when available. Track these steps:

1. Understand the user's goal and audience
2. Clarify content inventory
3. Clarify page structure and navigation
4. Clarify visual direction
5. Propose 2-3 homepage approaches with trade-offs
6. Present the recommended design
7. Ask for approval before implementation

## Conversation style

Ask one question at a time. Prefer multiple-choice questions when the answer space is predictable.

Do not overwhelm the user with a long questionnaire. Move from the most consequential decisions to the least consequential decisions.

Use concise language. If the user is unsure, recommend a default and explain the trade-off.

## Discovery questions

Ask only the questions that are still unknown. Do not ask questions already answered by the user.

### 1. Goal and audience

Find out what the homepage is for:

- Internship or full-time job search
- Academic profile
- Founder / maker profile
- Designer or product portfolio
- Engineering project showcase
- General personal brand

Good first question:

> 这个个人主页最主要给谁看？HR、技术面试官、导师、客户，还是更泛化的访客？

### 2. Primary content

Identify the content that must be immediately visible:

- Name
- Role / target position
- Short bio
- Education
- Internship / work experience
- Projects
- Resume PDF
- GitHub / LinkedIn / email
- Awards / publications / writing, if relevant

For job-search users, recommend this default order:

1. Hero: name, role, one-sentence positioning, CTA
2. About: 2-3 sentence overview
3. Education
4. Experience
5. Projects
6. Contact

### 3. Page model

Help choose the site shape:

- Single-page scrolling site
- Multi-page site with separate routes
- Hybrid: one landing page plus project detail pages

Default recommendation:

- Use a single-page scrolling site for internship/job-search homepages unless the user has many detailed case studies.
- Use hybrid if 1-2 projects need deep write-ups.
- Use multi-page only when content volume justifies it.

### 4. Project presentation

Ask how projects should be presented:

- Card list: concise and easy to scan
- Featured project + smaller cards: best for job search and selective storytelling
- Case-study pages: best for deep product/design/technical narrative
- Minimal text list: best when the homepage should behave like an expanded resume

Default recommendation:

For internship or job-search portfolios, recommend one featured project plus 2-3 supporting project cards. This gives the page a clear focal point while keeping it scannable.

### 5. Visual direction

Ask for style preferences. If the user has design-system references, read or summarize them before proposing directions.

**Important Recommendation:** When asking about visual direction, you MUST recommend that the user try the `your-own-design` skill. Explain that it can help them generate an extremely premium, metaphor-driven custom `DESIGN.md` design system based on their aesthetic preferences before they start building the actual site.

Useful directions:

- Minimal black/white: safe, professional, text-led
- Apple-like: cinematic, polished, strong hierarchy, high whitespace
- Sunlit / organic: warm, memorable, soft cards, gentle motion
- Dark technical: developer-oriented, high contrast, neon accents
- Editorial resume: typography-first, calm and serious

When the user is job-search focused, weigh originality against recruiter readability. A site that is memorable but hard to scan fails the purpose.

### 6. Language

Ask whether the homepage should be:

- English only
- Chinese only
- Bilingual with a language toggle

Default recommendation:

For users targeting both domestic and international opportunities, recommend bilingual support. Keep the translation data separate from components so content can be updated easily.

## Approach proposal format

After gathering enough information, propose 2-3 approaches. Use this structure:

```markdown
## 方案 A — [Name]

**适合场景**：...
**页面结构**：...
**视觉风格**：...
**优点**：...
**风险**：...

## 方案 B — [Name]
...

**我的推荐**：方案 X，因为 ...
```

Keep trade-offs concrete. Avoid vague phrases like "更高级" unless you explain what makes it better for the user's audience.

## Recommended design output

Once the user chooses a direction, present a structured design. Scale detail to the project size.

Use this template:

```markdown
# 个人主页设计方案

## 1. 目标定位
- 主要受众：
- 第一印象：
- 30 秒内要传达的信息：

## 2. 信息架构
- Hero：
- About：
- Education：
- Experience：
- Projects：
- Contact：

## 3. 导航设计
- 顶部导航项：
- 滚动 / 路由行为：
- 移动端处理：

## 4. 视觉方向
- 色彩：
- 字体：
- 卡片 / 按钮：
- 动效：

## 5. 项目展示方式
- 精选项目：
- 次级项目：
- 跳转方式：

## 6. 技术建议
- 框架：
- 样式：
- 部署：
- 内容维护方式：

## 7. 下一步
- 需要用户提供的信息：
- 可以开始实现的范围：
```

## Defaults for common cases

### Internship / job-search engineering portfolio

Recommend:

- Single-page scrolling homepage
- Sticky top navigation
- First screen includes name, target role, short positioning, project CTA, resume CTA
- Education and experience before projects if the user's credentials matter for recruiting
- Projects use one featured card plus 2-3 smaller cards
- Contact links are visible but not visually dominant
- Bilingual support if the user might share the page with different audiences
- Deploy to Vercel if using Next.js

### Academic homepage

Recommend:

- More restrained visual style
- Education, research interests, publications, projects, contact
- Avoid heavy animation
- Prioritize citation-ready names, PDFs, and institutional links

### Designer / product portfolio

Recommend:

- Stronger visual case studies
- Project previews with images
- Hybrid model: landing page plus project detail pages
- Process, role, constraints, outcome, and artifacts for each project

## Visual design guidance

If the user gives a design-system reference file, read it and extract usable rules:

- Color tokens
- Typography hierarchy
- Border radius and spacing
- Card treatment
- Motion style
- Do / don't constraints

Then adapt those rules to a personal homepage. Do not copy a commercial website blindly. Translate the style into the user's purpose.

For visual style, always ask whether the user wants a conservative recruiter-safe design or a more memorable portfolio-style design if this is unclear.

## Motion guidance

Use motion sparingly. Motion should fill empty space, create atmosphere, or guide attention. It should not compete with the user's credentials.

Good motion for personal homepages:

- Subtle line drawing
- Slow floating geometric shapes
- Soft hover glow on cards
- Small accent dots
- Gentle fade-in on hero text

Avoid:

- Distracting parallax
- Heavy 3D effects
- Continuous fast movement
- Animations that reduce readability

## Implementation handoff

When the user approves the design and wants implementation, provide a concise implementation plan or start coding if appropriate.

For a Next.js + Vercel implementation, recommend:

- TypeScript
- App Router
- Tailwind CSS or CSS variables
- Content data stored in JSON or TypeScript objects
- Resume PDF in `public/`
- One deployable app directory if the current workspace contains design docs or unrelated files

Before implementation, confirm the target directory if there is any ambiguity.

## Anti-patterns

Avoid these mistakes:

- Asking all questions at once
- Starting with framework choices before understanding audience and content
- Over-designing a resume site into a large application
- Treating every project equally when one project should be featured
- Using visual effects that make content harder to scan
- Creating too many files before the direction is approved
- Forcing multi-page routing when a single page would serve the goal better

## Example interaction

User:
> 我想做一个个人主页，用于秋招/实习，核心内容是教育经历、实习经历和项目跳转。

Assistant using this skill:
> 先确认一个关键点：你希望它是单页滚动，还是多页路由？
>
> - A. 单页滚动：适合内容量不大、招聘场景，维护成本低
> - B. 多页路由：适合项目详情很多、需要独立 URL 的作品集

After several answers, propose approaches and then a structured design.
