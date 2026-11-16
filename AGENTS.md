# Engineering Standards & Agent Guidelines

**Project:** GitHub Builder Card
**Engineering Challenge:** Hackyard Winter 2026 Engineering Challenge
**Applicability:** All autonomous and semi-autonomous coding agents operating in this workspace.

---

## 1. Architecture & Dependency Philosophy

* **Minimal & Maintainable:** Keep the application minimal, focused, and understandable. This is a single-page frontend application designed to run entirely in the browser.
* **No Unnecessary Dependencies:** Do not introduce external state management (Redux, Zustand), backend servers, databases, or redundant styling libraries.
* **Official Documentation First:** Rely on official, current documentation (GitHub REST API, Vite, React, Tailwind CSS v4, shadcn/ui) as the primary source of truth. Never invent undocumented endpoints or payload properties.

---

## 2. Code Quality & TypeScript Standards

* **Strict TypeScript:** Enforce strict type safety with `strict: true`. Avoid `any`, `unknown` without narrowing, and untyped objects.
* **Compile-Time vs. Runtime:** Acknowledge that TypeScript provides compile-time verification, not runtime validation. Handle external API payloads defensively.
* **No Dead or Fabricated Code:** Do not write unused functions, artificial sample data, or simulated statistics.
* **Concise Code:** Avoid noisy, redundant code comments that merely restate what the code clearly does. Document only non-obvious technical rationales.

---

## 3. GitHub API Data Integrity & Defensive Handling

* **Truthful Data Presentation:**
  * Disclose repository ranking sampling boundaries (up to 100 recently active public repositories sorted client-side by stars).
  * Distinguish primary repository language distribution from byte-level codebase volume.
  * Format activity events strictly using fields documented in the Events API payload (`PushEvent`, `PullRequestEvent`, `IssuesEvent`, `CreateEvent`, `WatchEvent`, `ForkEvent`, `ReleaseEvent`).
  * Never invent commit counts or claim metrics without an actual supporting data source.
* **Sequential Request Pipeline:** Execute API requests sequentially per GitHub best practices to avoid triggering secondary rate limits. Stop immediately if the profile lookup returns 404 or a fatal rate limit.
* **Rate-Limit Classification:** Check `x-ratelimit-remaining === "0"` first to identify primary rate limits. Strictly validate `x-ratelimit-reset` as a positive safe integer. Inspect response messages for secondary rate-limit indicators. Never retry continuously in a loop.
* **Browser CORS Safety:** Send standard `Accept: application/vnd.github+json` headers only. Do not send `X-GitHub-Api-Version` in browser fetch requests as it is omitted from GitHub's CORS preflight allowlist.

---

## 4. Operational & Git Discipline

* **Approval-Gated Actions:**
  * Never execute destructive commands without user approval.
  * Never create Git commits, push to remotes, or perform branch merges without explicit user approval.
* **Professional Git Workflow:**
  * `main` is the stable, deployable default branch.
  * Use task-specific feature branches (`feat/`, `fix/`, `chore/`, `docs/`, `test/`).
  * Commit small, logically grouped units using Conventional Commits.
  * Review diffs (`git diff`, `git status`) before staging and committing.
  * Prefer Squash and merge for short-lived feature branches to preserve a clean, linear history.
* **Investigation Before Action:**
  * Read actual source files and execution logs before attempting to diagnose or fix errors.
  * Never guess or claim an untested configuration has been verified. Report actual command outputs, exit codes, warnings, and errors honestly.

---

## 5. Hackyard AI-Use Policy Compliance

* **Author Transparency:** The developer must personally author, understand, and be capable of explaining all core logic and architectural decisions in this repository.
* **No Misrepresentation:** Agents must never attempt to conceal AI collaboration, misrepresent code authorship, or bypass the challenge's published integrity guidelines.
