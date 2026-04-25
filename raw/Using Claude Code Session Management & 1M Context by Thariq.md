---
title: "Using Claude Code: Session Management & 1M Context"
source: "https://x.com/trq212/status/2044548257058328723"
author:
  - "[@trq212]"
published: 2026-04-16
created: 2026-04-19
description: "In my recent calls with Claude Code users, one theme keeps coming up: the 1M token context window is a double-edged sword. Session management matters more than ever and there seem to be a lot of questions about it."
tags:
  - "clippings"
  - "claude-code"
  - "context-management"
---

![Image](../assets/2026-04-19-claude-code-session-management/img-1.jpg)

In my recent calls with Claude Code users, one theme keeps coming up: the 1M token context window is a double-edged sword. It lets Claude Code operate autonomously for longer and handle tasks more reliably, but it also opens the door to context pollution if you're not deliberate about managing your sessions. Session management matters more than ever and there seem to be a lot of questions about it. Do you keep one session open in a terminal, or two? Start fresh with every prompt? When should you use compact, rewind, or subagents? What causes a bad compact? There's a surprising amount of detail here that can really shape your experience with Claude Code and almost all of it comes from managing your context window.

---

## A Quick Primer on Context, Compaction & Context Rot

![Image](../assets/2026-04-19-claude-code-session-management/img-2.jpg)

The context window is everything the model can "see" at once when generating its next response. It includes your system prompt, the conversation so far, every tool call and its output, and every file that's been read. Claude Code has a context window of one million tokens. Unfortunately using context has a slight cost, which is often called **context rot**. Context rot is the observation that model performance degrades as context grows because attention gets spread across more tokens, and older, irrelevant content starts to distract from the current task. For our 1MM context model, we see some level of context rot happen around ~300-400k tokens, but it is highly dependent on the task- not a fast rule. Context windows are a hard cutoff, so when you're nearing the end of the context window, you will need to summarize the task you've been working on into a smaller description and continue the work in a new context window, we call this **compaction**. You can also trigger compaction yourself.

---

## Every Turn Is a Branching Point

![Image](../assets/2026-04-19-claude-code-session-management/img-3.jpg)

Say you've just asked Claude to do something and it's finished, you've now got some information in your context (tool calls, tool outputs, your instructions) and you have a surprising number of options for what to do next:

- **Continue** — send another message in the same session
- **/rewind (esc esc)** — jump back to a previous message and try again from there
- **/clear** — start a new session, usually with a brief you've distilled from what you just learned
- **Compact** — summarize the session so far and keep going on top of the summary
- **Subagents** — delegate the next chunk of work to an agent with its own clean context, and only pull its result back in

While the most natural is just to continue, the other four options exist to help manage your context.

---

## When to Start a New Session

![Image](../assets/2026-04-19-claude-code-session-management/img-4.jpg)

The new 1M context windows means that you can now do longer tasks more reliably, for example to have it build a full-stack app from scratch. But just because your model hasn't run out of context, it doesn't mean you shouldn't start a new session. Our general rule of thumb is **when you start a new task, you should also start a new session**. A grey area is when you may want to do related tasks where some of the context is still necessary, but not all. For example, writing the documentation for a feature you just implemented. While you could start a new session, Claude would have to reread the files that you just implemented, which would be slower and more expensive. Since documentation may not be a highly intelligence sensitive task, the extra context is probably worth the efficiency gain of not having to re-read the relevant files again.

---

## Rewinding Instead of Correcting

![Image](../assets/2026-04-19-claude-code-session-management/img-5.jpg)

If I had to pick one habit that signals good context management, it's **rewind**. In Claude Code, double-tapping Esc (or running /rewind) lets you jump back to any previous message and re-prompt from there. The messages after that point are dropped from the context. Rewind is often the better approach to correction. For example, Claude reads five files, tries an approach, and it doesn't work. Your instinct may be to type "that didn't work, try X instead." but the better move is to rewind to just after the file reads, and re-prompt with what you learned. "Don't use approach A, the foo module doesn't expose that — go straight to B." You can also use "summarize from here" to have Claude summarize its learnings and create a handoff message, kind of like a message to the previous iteration of Claude from its future self that tried something and it didn't work.

---

## Compacting vs. Fresh Sessions

![Image](../assets/2026-04-19-claude-code-session-management/img-6.jpg)

Once a session gets long, you have two ways to shed weight: **/compact** or **/clear** (and start fresh). They feel similar but behave very differently. Compact asks the model to summarize the conversation so far, then replaces the history with that summary. It's lossy, you're trusting Claude to decide what mattered, but you didn't have to write anything yourself and Claude might be more thorough in including important learnings or files. You can also steer it by passing instructions (`/compact focus on the auth refactor, drop the test debugging`).

---

## What Causes a Bad Compact?

*(Section content based on image)*

Good compactions require Claude to think carefully about what to preserve from the session. Bad compactions happen when:
- The task was too complex for a single session
- Claude tried to preserve too much irrelevant context
- The summary loses critical information about the task goal

---

## Subagents: Context Isolation for Parallel Work

*(Section content based on image)*

Subagents let you delegate work to a clean context window:
- Each subagent gets its own fresh context
- Results are pulled back into the main session
- Useful for parallel tasks that don't need shared context

---

## Key Takeaways

1. **Context is finite but large** — 1M tokens, but context rot starts around 300-400k
2. **New task = new session** — Don't hesitate to start fresh when the task changes
3. **Rewind over correction** — Jump back rather than building on mistakes
4. **Compact intentionally** — Guide compaction with focus instructions
5. **Subagents for isolation** — Use when you need clean context for parallel work

---

**Stats:** 2.2M views · 8.3K likes · 15.7K bookmarks · 1.3K reposts · 286 replies
