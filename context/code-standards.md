# Code Standards

## General

- Keep changes small and focused on one Django boundary at a time.
- Prefer root-cause fixes over workaround layers.
- Do not mix routing, styling, and data logic in the same change unless the task explicitly requires it.

## Python / Django

- Follow Django's standard project layout.
- Keep views thin: render templates, prepare context, and delegate everything else.
- Put configuration in [ghost_ai/settings.py](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/ghost_ai/settings.py).
- Put routes in [ghost_ai/urls.py](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/ghost_ai/urls.py) and app URLs in [core/urls.py](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/core/urls.py).
- Create app-specific code under [core/](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/core) rather than expanding the project package with feature logic.

## Templates

- Use [templates/base.html](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/templates/base.html) for shared shell markup.
- Keep page-specific markup inside the app template directory.
- Prefer semantic HTML and keep blocks simple and explicit.

## Styling

- Use CSS custom properties for shared theme values.
- Keep presentational rules in [core/static/core/site.css](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/core/static/core/site.css).
- Avoid inline styles unless there is no better option.

## Verification

- Run `python manage.py check` after structural or routing changes.
- Run `python manage.py runserver` and verify the actual page when UI or template work changes.
- If models are added later, add migrations and validate them before handoff.

## File Organization

- `ghost_ai/` — settings, ASGI, WSGI, root URL config.
- `core/` — view logic, app routing, templates, static files.
- `templates/` — shared shell templates.
- `requirements.txt` — Python dependencies.
- `README.md` — local setup and run instructions.
