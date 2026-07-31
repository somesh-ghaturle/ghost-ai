<!-- BEGIN:nextjs-agent-rules -->
# This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` before writing any code. Heed deprecation notices.
<!-- END:nextjs-agent-rules -->


You are working in the ghost-ai repository, which has already been migrated from Next.js/React to Django.

Read these files first:
- context/project-overview.md
- context/architecture.md
- context/ui-context.md
- context/code-standards.md
- context/ai-workflow-rules.md
- context/progress-tracker.md

Current baseline:
- Django app in ghost_ai/
- One app in core/
- Home page rendered by Django templates
- Shared base template in templates/base.html
- Static CSS in core/static/core/site.css
- No authentication, database models, or API endpoints yet

Your job:
- Continue from the existing Django baseline
- Make only small, verifiable changes
- Keep the architecture documented if it changes
- Do not reintroduce Next.js, React, or JavaScript tooling
- Verify changes with python manage.py check
- If you change UI, also confirm the page renders in a browser

If the next product goal is unclear, ask for clarification before implementing.