# ghost-ai Project Overview

## Overview

ghost-ai is now a minimal Django application. The repository was migrated away from the prior Next.js/React scaffold and currently serves a single public landing page rendered by Django templates.

The app is intentionally small: it exists as a clean Python starting point that another agent can extend without having to reverse-engineer framework history or unfinished product scope.

## Current State

- Framework: Django
- Language: Python
- UI: Server-rendered HTML with a shared base template
- Styling: App-scoped static CSS in [core/static/core/site.css](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/core/static/core/site.css)
- Entry points: [manage.py](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/manage.py), [ghost_ai/settings.py](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/ghost_ai/settings.py), [ghost_ai/urls.py](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/ghost_ai/urls.py)

## Goals

1. Keep the repo on a clean Django baseline.
2. Preserve the current landing-page experience.
3. Make it easy for another agent to add the next feature without redoing setup.

## Core User Flow

1. A developer installs dependencies from [requirements.txt](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/requirements.txt).
2. They run `python manage.py check` or `python manage.py runserver`.
3. They open `/` and see the ghost AI landing page.

## Features

### Landing Page

- Centered hero card.
- Project title and short description.
- Dark, minimal visual style.

### Django Project Structure

- Standard Django project package in [ghost_ai/](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/ghost_ai).
- One app, [core/](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/core), owning the home page.
- Shared template shell in [templates/base.html](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/templates/base.html).

## Scope

### In Scope

- Public home page.
- Django settings, routing, and server entry points.
- Static CSS and templates.
- Documentation that explains the Django baseline.

### Out of Scope

- Authentication.
- Database models or business workflows.
- API endpoints.
- Admin customization beyond Django defaults.

## Success Criteria

1. `python manage.py check` passes.
2. `python manage.py runserver` serves `/` with a 200 response.
3. The repository contains no Next.js/React runtime dependencies.
4. Another agent can continue from this folder without guessing the architecture.
