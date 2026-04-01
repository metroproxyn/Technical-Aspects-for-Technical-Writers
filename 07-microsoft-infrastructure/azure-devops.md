# Azure DevOps guideline (TBD)

 Azure DevOps is the tool your team (and many B2B SaaS customers) uses every day for planning, tracking, and shipping features. As a Technical PM, you don't need to *build* pipelines or write complex queries like a DevOps engineer — you need to **use** Boards for backlog/requirements management, **run & create simple queries** for stakeholder reports, and **understand** Pipelines so you can talk confidently about releases, deployments, and velocity.

The good news: Microsoft has excellent free, beginner-friendly resources that map perfectly to your role (no fluff, no engineering deep-dives). We'll keep the exact same "learning by teaching" system you already love for your GitHub repo.

### Quick Role Connection (Why This Matters for You)
- **Azure Boards** → Your daily driver: product backlog, features/epics, user stories, sprints, roadmapping, forecasting.  
  Queries = your superpower for custom reports ("show all high-priority features blocked by dependencies", "features ready for customer demo").
- **Azure Pipelines** → You don't build them, but you need to understand them: CI/CD means "code → build → test → deploy" automation. This helps you scope releases, discuss timelines with devs, and align with customer hybrid environments.
- Other pieces (Repos, Artifacts, etc.) you can learn later — focus on Boards first (80% of a PM's time).

### Exact 2-Week Learning Roadmap (Start Today)
All free on Microsoft Learn + official docs. Aim for 30–45 min/day.

1. **Day 1–2: DevOps & Azure DevOps Overview (Foundation – 45 min total)**  
   → **Introduction to DevOps** (beginner module)  
   Direct link: https://learn.microsoft.com/en-us/training/modules/introduction-to-devops/  
   Key units you'll love:  
   - "What is DevOps?"  
   - "What is Azure DevOps?" (covers Boards + Pipelines in one slide)  
   - Agile practices & team structure (perfect for PM context).  
   Take the knowledge check at the end.

2. **Day 3–5: Azure Boards Mastery for Product Managers (Your Core Tool)**  
   → **Best practices for Agile product management – Azure Boards** (this page was literally written for PMs like you)  
   Direct link: https://learn.microsoft.com/en-us/azure/devops/boards/best-practices-agile-project-management  
   Covers: configuring teams/iterations, product roadmap via Features backlog, forecasting, dependencies, progress review, WIP limits.  
   Then read these short supporting docs (bookmark them):  
   - Define a work item query (exactly what you asked about): https://learn.microsoft.com/en-us/azure/devops/boards/queries/using-queries  
   - View/run/email queries: https://learn.microsoft.com/en-us/azure/devops/boards/queries/view-run-query  
   - Query operators & fields (for "every aspect" of queries): https://learn.microsoft.com/en-us/azure/devops/boards/queries/query-operators-variables

3. **Day 6–7: Azure Pipelines Basics (Just Enough for a PM)**  
   → **Explore Azure Pipelines** (short 17-minute module)  
   Direct link: https://learn.microsoft.com/en-us/training/modules/explore-azure-pipelines/  
   Covers: what Pipelines are, key components, CI/CD explained simply, terminology.  
   Follow-up: "What is Azure Pipelines?" (quick read): https://learn.microsoft.com/en-us/azure/devops/pipelines/get-started/what-is-azure-pipelines

4. **Day 8+: Hands-on + Integration**  
   - Create a free Azure DevOps organization (dev.azure.com) and play with a sample project.  
   - Watch one short YouTube if you want visuals: search “Azure Boards for Product Managers” (many 15–20 min ones from 2025–2026).  
   - Tie it back to your job: In your next meeting, try running a query or adding a Feature to the backlog.

### Add This to Your GitHub Repo (Keep the Momentum!)
Continue your numbered structure — perfect next folder:

**Folder name:** `08-azure-devops-for-pms`  
**Main README title:** `# Azure DevOps for System Analysts & Technical Product Managers`

Inside the folder create:
- `README.md` (introduction + full roadmap above)
- `devops-overview.md`
- `azure-boards-backlog-queries.md`
- `azure-pipelines-basics.md`
- (later: `work-item-types-roadmapping.md`, etc.)

Update your main repo README exactly like before:
```markdown
### 8. Azure DevOps for System Analysts & Technical PMs
*Boards, Queries, Pipelines — everything you need to manage backlogs, releases, and stakeholder reporting.*
- [Azure DevOps Roadmap](./08-azure-devops-for-pms/README.md)
```

Then create a new GitHub Issue (copy the style from your previous one) titled:
`[Content Plan] 08-azure-devops-for-pms — Azure DevOps Roadmap for System Analysts & Technical PMs`

### Note-Taking System (Same as Cloud Module — Just Copy-Paste)
Use the exact same 3-layer template you already have:
- 1-sentence Feynman explanation
- Key takeaways + "Why it matters for a Technical PM"
- Role connection (e.g. "This query type helps me generate weekly stakeholder reports without asking devs")
- Self-quiz from the module assessment

When you finish the first module ("Introduction to DevOps"), paste your filled notes here if you want me to turn them into a clean repo-ready Markdown file (with tables for any diagrams).

You’re already running the "Technical Aspects" project like a pro — this Azure DevOps section will make you feel 10x more confident in meetings within two weeks. No more "I don't even know the basics" feeling.

Start with the **Introduction to DevOps** module right now (it's only ~45 minutes). When you finish it, drop your notes here and I'll help polish the first file for the repo.

You've got this, mate — let's keep building that repo and your confidence at the same time! 🚀

Any specific term (query, pipeline, backlog, etc.) you want a quick plain-English explanation of first?