# Portfolio Content Updates

## Data Source

All portfolio content extracted from **resume.pdf** by Gowtham Bhaskar Teki

### Updated Sections

#### 1. HeroSection.tsx
- **Tagline**: "GenAI PM crafting intelligent products that heal, teach, and empower."
- **Tags**: GenAI, Product Manager, LLM Engineering
- **Profile Image**: `f526295bdde79bfd018746c5da9d08c05fa3c1c9.png`

#### 2. AboutSection.tsx
- **Bio**: "I design and lead the development of AI-driven products that solve complex real-world problems. With expertise in LLM engineering, RAG systems, and product strategy, I've shaped products in healthcare, education, and fintech domains."
- **Education**: B.Tech Electronics and Communication Engineering, Lovely Professional University (2023–2027)
- **Email**: tekigowtham04@gmail.com

#### 3. ProjectsSection.tsx
Three featured projects in reverse chronological order:

1. **CareNote AI** (Jan–Apr 2025)
   - Domain: Healthcare/MedTech
   - Tagline: Clinical Documentation Copilot
   - Impact: "Reduced clinical documentation time by 60%, enabled physicians to focus on patient care"
   - GitHub: https://github.com/tekigowtham2204/CareNote-AI

2. **LearnPath AI** (Aug–Dec 2024)
   - Domain: EdTech/Learning
   - Tagline: Adaptive Skill-Gap Engine
   - Impact: "Increased learner engagement by 45%, improved completion rates from 32% to 78% across 500+ learners"
   - GitHub: https://github.com/tekigowtham2204/LearnPath-AI

3. **FinSense AI** (May–Aug 2024)
   - Domain: FinTech
   - Tagline: Conversational Financial Clarity Engine
   - Impact: "Resolved 92% of user queries accurately, reduced support tickets by 850/month"
   - GitHub: https://github.com/tekigowtham2204/FinSense-AI

#### 4. SkillsSection.tsx
Four skill categories:

1. **AI / LLM Engineering**
   - LLM Fine-tuning, RAG, Prompt Engineering, Semantic Search, Vector Databases (Pinecone, Milvus, ChromaDB)
   - LangChain, LlamaIndex, OpenAI API, Anthropic Claude

2. **Backend & AI Infrastructure**
   - Python (FastAPI, Flask), Microservices, System Design
   - Database Design (PostgreSQL, MongoDB), Async Processing, Caching

3. **AI Product Strategy**
   - Market Analysis, User Research, Product Roadmapping
   - A/B Testing, Metrics & KPIs, Stakeholder Management

4. **DevOps & Deployment**
   - Docker, Kubernetes, CI/CD (GitHub Actions)
   - AWS (EC2, Lambda, RDS), Monitoring & Logging

#### 5. ContactSection.tsx
- **Email**: tekigowtham04@gmail.com
- **Phone**: +91–9080329453
- **LinkedIn**: linkedin.com/in/gowthambhaskar
- **GitHub**: github.com/tekigowtham2204

## Component Implementation Notes

### Responsive Design
All sections use Tailwind CSS breakpoints:
- `md:` for tablets (768px+)
- `lg:` for desktops (1024px+)

### Animations
Framer Motion (`motion/react` v12.23.24) powers:
- Fade-in on scroll
- Staggered item animations
- Hover effects on interactive elements

### Accessibility
Radix UI components ensure:
- Keyboard navigation
- ARIA labels
- Focus management

### Performance
Vite build optimizes:
- Code splitting
- Lazy loading of images
- Tree shaking unused CSS

## Testing Checklist

- [ ] Dev server starts without errors: `npm run dev`
- [ ] Production build succeeds: `npm run build`
- [ ] All sections render correctly on mobile, tablet, desktop
- [ ] Links to GitHub projects are active
- [ ] Smooth scroll animation works across browsers
- [ ] Contact links open correctly (email, phone, socials)
- [ ] GitHub Pages deployment displays correctly at base path `/Gowtham-Portfolio/`
