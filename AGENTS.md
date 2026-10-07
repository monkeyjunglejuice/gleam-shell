# Repository Guidelines

## Project Structure & Module Organization

This repository is the Emacs package gleam-shell, a Comint-based Emacs wrapper/frontend for gsh https://github.com/v4rm4n/gsh
Related Emacs packages are:
- https://github.com/gleam-lang/gleam-mode (this package is allowed as a dependency, if code from this package can be re-used)
- https://github.com/takeokunn/ob-gleam

## Features and Functionality
Completion candidates may be provided by:
- gsh directly
- Eglot when in a Gleam project
Completion backend selection must be a customization option: e.g. only gsh, only Eglot, or both gsh + Eglot.
Completion backends must be cleanly separated.

## Coding Style & Naming Conventions

- Use Emacs Lisp with lexical binding preserved in the file header.
- Prefix project symbols with `gsh-` for functions, variables, commands, faces, and customization options.
- Keep code dependency-free except for libraries bundled with GNU Emacs (https://github.com/gleam-lang/gleam-mode is allowed as a dependency).
- Use Emacs standard APIs for completion (e.g. completion-in-region)
- Docstrings for functions and variables (1 space after full stop instead of 2 spaces).
- Keep the  maximum line length at 80 characters, but you can deviate from the 80 characters limit for URLs.
- Prefer a functional and declarative programming style wherever possible; e.g. use recursion instead of loops when it's safe; pure functions insteat of mutation; and use pattern-matching when available.
- Code must be correct, performant, general and terse. Strive for elegant simplicity.
- Don't write overly defensive code.
- Minimum required GNU Emacs version is Emacs 31.1

## Testing Guidelines

No formal test suite is initially present. For code changes, at minimum load the affected file in batch mode and byte-compile it. For interactive behavior, test in a clean Emacs session.

## Commit & Pull Request Guidelines

Keep commit subjects concise and present tense. The commit subject must state why the change has been made, rather than what has been changed.

Pull requests should include:

- A brief description of the user-facing change.
- Validation commands run, including any warnings left unresolved.
- Screenshots or short notes for visible UI/theme changes.
- Linked issues when fixing reported bugs.

## Agent-Specific Instructions

- Keep changes minimal and focused.
- Do not reformat unrelated files unless the task explicitly asks for it.
- Never make assumptions about the program logic from function names, variable names or comments/docstrings. Always analyze and follow the actual program logic.
- Don't fix bugs by adding more code on top. Review the architecture and logic to get a grasp of the intention and the bigger picture, backtrack and then work out a fix. It's fine if this leads to architectural changes, API changes or more extensive refactors when it makes the implementation more general, robust, clearer, simpler and better maintainable.
