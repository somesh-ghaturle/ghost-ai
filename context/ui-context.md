# UI Context

## Theme

The current UI is a dark, minimal landing page. The intent is calm and technical: a centered surface, subtle glow, and a single clear callout rather than a marketing layout.

## Colors

These tokens are defined in [core/static/core/site.css](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/core/static/core/site.css) and should be reused for all future styling.

| Role | CSS Variable | Value |
| --- | --- | --- |
| Page background | `--bg-base` | `#0b1020` |
| Card/surface | `--bg-surface` | `#121a33` |
| Primary text | `--text-primary` | `#f5f7ff` |
| Muted text | `--text-muted` | `#a7b1d6` |
| Accent | `--accent-primary` | `#7c9cff` |
| Border | `--border-default` | `rgba(167, 177, 214, 0.2)` |

## Typography

| Role | Font | Notes |
| --- | --- | --- |
| UI text | Arial / system sans-serif | Used for headings and body copy |
| Mono/code | system monospace | Reserved for future technical output |

## Shape and Spacing

- Card radius: `24px` / `rounded-2xl`
- Larger overlays (future): `rounded-3xl`
- Layout spacing is generous, with a single centered column and wide padding on smaller screens.

## Component Approach

- No component library is installed.
- The page is built with plain Django templates plus one stylesheet.
- Future components should follow the same simple, server-rendered pattern unless the architecture changes.

## Layout Patterns

- Full-viewport center alignment.
- Single hero card with a title, eyebrow label, and description.
- Responsive width capped to a comfortable reading measure.

## Interaction Patterns

- No interactive controls exist yet.
- No icon set is required yet.
- Hover and focus states should remain subtle if new controls are added later.

## Extension Guidance

If another agent adds more pages, keep the same visual language:

- reuse the existing CSS tokens,
- keep the page centered and content-first,
- avoid introducing heavy front-end dependencies without an explicit need.
