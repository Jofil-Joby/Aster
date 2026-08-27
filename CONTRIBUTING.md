# Contributing to Aster

Thanks for taking an interest in Aster.

Aster is intentionally lightweight, so contributions should preserve its core idea: useful functionality without unnecessary complexity.

## Development

1. Fork the repository.
2. Clone your fork.
3. Make your changes inside `aster/`.
4. Load the `aster` directory as an unpacked extension in Chrome.
5. Test the change from a fresh new tab.
6. Check both **Midnight** and **Light** themes for UI changes.

## Before opening a pull request

- Make sure the extension still loads without errors.
- Test the changed feature in Chrome.
- Check desktop and narrow/mobile layouts when relevant.
- Check keyboard interaction for new controls.
- Avoid introducing dependencies unless they provide a clear benefit.
- Keep the existing visual language consistent.

## Commit messages

Prefer short, descriptive commit messages such as:

```text
fix: correct light theme clock color
feat: add shortcut drag ordering
docs: improve installation instructions
style: refine focus timer spacing
```

## Pull requests

Include:

- What changed
- Why it changed
- How it was tested
- Screenshots for meaningful UI changes

Keep pull requests focused. A bug fix, three unrelated redesigns, and a new authentication system do not need to become one heroic commit.

## UI contributions

Aster uses a restrained interface with compact controls, subtle borders, large time typography, and a warm accent. New UI should feel like part of the existing product rather than a separate application wearing an Aster name tag.
