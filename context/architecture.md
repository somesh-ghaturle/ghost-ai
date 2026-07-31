# Architecture Context

## Stack

| Layer | Technology | Role |
| --- | --- | --- |
| Framework | Django | Web application framework |
| Language | Python | Application logic and server execution |
| Rendering | Django templates | Server-rendered HTML pages |
| Styling | CSS | App shell and landing-page presentation |
| Database | SQLite (default) | Local development storage |

## System Boundaries

- [ghost_ai/](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/ghost_ai) — Django project configuration, URL routing, and ASGI/WSGI entry points.
- [core/](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/core) — The app that owns the current landing page, its template, and its static assets.
- [templates/](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/templates) — Shared base template(s) used across pages.
- [requirements.txt](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/requirements.txt) — Python dependency list for the project.

## Storage Model

- **SQLite database**: Default Django development database. No application tables are currently defined.
- **Static files**: CSS lives in [core/static/core/site.css](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/core/static/core/site.css). Additional front-end assets should stay under the app's static tree.
- **Templates**: Shared shell markup lives in [templates/base.html](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/templates/base.html); page-specific markup lives in app templates.

## Auth and Access Model

- There is no authentication flow yet.
- The landing page is public and open to everyone.
- Django admin is enabled in settings for future use, but no custom admin work has been done.
- There are no permissions, roles, or ownership rules yet.

## Runtime Commands

- `python manage.py check` — structural validation of the Django project.
- `python manage.py runserver` — local development server.
- `python manage.py migrate` — only needed once models are added.

## Invariants

1. The home route must remain available at `/`.
2. The project must remain runnable with standard Django commands.
3. Framework settings stay in [ghost_ai/settings.py](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/ghost_ai/settings.py), not spread across ad hoc files.
4. Presentation concerns stay in templates/CSS, not embedded in views.
5. Future product work should not reintroduce Next.js or React.
