<p align="center">
  <img src="./logo.png" alt="i-have-adhd" width="140" />
</p>
<p align="center">
  <strong align="center">ADHD-friendly outputs. No ADHD diagnosis needed!</strong>
</p>
<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/github/license/ayghri/i-have-adhd?style=flat" alt="License"></a>
</p>

<p align="center">
  <strong>English</strong> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <a href="README.ja.md">日本語</a> ·
  <a href="README.ko.md">한국어</a>
</p>


## Install

<details>
<summary><strong>Claude Code</strong></summary>

```bash
claude plugin marketplace add anshu957/i-have-adhd-science
claude plugin install i-have-adhd-science@i-have-adhd-science
```

Then type `/i-have-adhd-science`. No local clone needed: Claude Code fetches the repo and keeps it updated.

Want it on every session? `touch ~/.claude/.i-have-adhd-science-always` (see [INSTALL.md](./INSTALL.md)).

</details>

<details>
<summary><strong>Codex</strong></summary>

```bash
codex plugin marketplace add ayghri/i-have-adhd --ref main
codex plugin add i-have-adhd@i-have-adhd
```

Then type `$i-have-adhd` to apply the output style explicitly. The skill can also be invoked implicitly when Codex sees a task that benefits from it.

</details>

Install instructions for other coding agents live in [INSTALL.md](./INSTALL.md).

## What it does

A skill for your coding assistant that stops it from burying the answer. Action first. Steps numbered. No "Hope this helps!"


## What changes


<table>
<tr>
<td width="50%">

## Before

> Great question! Let me think about this. Your auth flow has a few moving pieces: the middleware, the token verification, and the cookie handling. Looking at `src/auth.ts`, the `verifyToken` function (around lines 42-58) seems to be using an older `jsonwebtoken` API. One approach would be to update the package and rewrite that function. After making the change, you'd want to run the auth tests to confirm nothing breaks. By the way, you might also want to look at your dependency versions overall. Hope this helps! Let me know if you want to dig deeper.

</td>

<td width="50%">

## After

> Run `npm install jsonwebtoken@latest`, then edit `src/auth.ts:42`.
>
> 1. Open `src/auth.ts`
> 2. Replace `verifyToken` (lines 42–58) with the snippet below
> 3. Run `npm test -- auth.spec.ts`
>
> Next: paste the first failing line if any test fails.

</td>
</tr>
</table>


## The rules

Seven, plus one that governs them. Full text in [SKILL.md](./skills/i-have-adhd-science/SKILL.md).

**0. Shape never overrides substance.** Brevity compresses words, not science.

*Delivery*
1. Front-load what can be acted on.
2. Cut what is not load-bearing.
3. Be concrete.

*Thinking*
4. Hold your position on evidence, not on pressure.
5. Show what backs every claim.
6. Distrust the result before you report it.

*Language*
7. A word earns its place by adding precision.

Everything under a rule is an example of it, not another rule. This fork trades the upstream's 10 formatting rules for 7 that also cover how the work is judged — the failure mode in research is not a slow start, it is a fast wrong answer nobody argued with.

## Tune it

Edit `skills/i-have-adhd-science/SKILL.md`. If installed from a local clone, edits are live at the next session — no reinstall. If installed from GitHub:

```bash
claude plugin uninstall i-have-adhd-science
claude plugin marketplace remove i-have-adhd-science
claude plugin marketplace add <your-username>/i-have-adhd-science
claude plugin install i-have-adhd-science@i-have-adhd-science
```

Restart Claude Code, then re-invoke `/i-have-adhd-science`.

## Credits

Loosely based on *The Adult ADHD Tool Kit* by J. Russell Ramsay and Anthony L. Rostain. Adapted for how an LLM should respond, not how a human should organize their day.

## License

MIT.

Star ⭐ if it saved you one scroll past one "Great question!"
