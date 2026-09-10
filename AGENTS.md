# AGENTS.md — Project Rules

## 1. Purpose

This project is a new website or landing page created from an existing, ready-to-use donor project.

The donor project is the technical, structural and visual foundation for the new project.

The donor is assumed to be already implemented and functional.

The goal is to reuse the donor's working architecture and functionality while adapting the project to a new business, brand, content, visual identity and requirements.

The project must evolve incrementally.

Do not rebuild the donor project from scratch.

Do not introduce a new architecture unless explicitly requested.

Do not perform broad refactors unless required for the requested task.

The new project must remain an independent project with its own Git repository, Git history, remote repository and deployment configuration.

---

## 2. Donor Project and New Project

There are two separate entities:

### Donor Project

The donor is an existing, completed and functional website.

It may contain:

- HTML
- CSS
- JavaScript
- assets
- images
- SVG files
- fonts
- JSON data
- translations
- animations
- responsive behavior
- reusable components
- configuration
- SEO implementation
- documentation
- deployment-related files

The donor's existing implementation should be reused whenever possible.

Do not unnecessarily modify the donor project itself.

### New Project

The new project is created from the donor's source files but must become an independent project.

The new project must have:

- its own project directory
- its own Git repository
- its own Git history
- its own GitHub repository
- its own remote origin
- its own deployment configuration
- its own deployment credentials or keys where applicable

The new project is not a Git fork unless explicitly requested.

The new project is not a continuation of the donor's Git history.

---

## 3. Creating a New Project from a Donor

When starting a new project from a ready donor:

1. Identify the donor project.
2. Verify that the donor source is the intended version.
3. Copy the donor's project files into the new project directory.
4. Do not copy the donor's `.git` directory.
5. Do not copy the donor's Git history.
6. Do not copy the donor's Git remote configuration.
7. Do not copy donor-specific deployment credentials or SSH keys.
8. Preserve the donor's working source architecture.
9. Restore or create project-specific `AGENTS.md` and `README.md`.
10. Initialize a new Git repository.
11. Create or connect the new GitHub repository.
12. Configure the new project's deployment independently.
13. Make the initial commit.
14. Push the new project to its own remote repository.

### Critical rule

The donor's `.git` directory must NEVER be copied into the new project.

Never use a recursive copy operation that unintentionally copies:

```text
.git/