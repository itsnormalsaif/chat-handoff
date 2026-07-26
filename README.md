# chat-handoff

A Claude Skill that summarizes a conversation into a short recap and a copy-pasteable "continuation prompt," so you can resume the same context in a new chat, hand it off to someone else, or archive it before it gets too long.

## What it does

When triggered, the skill:

1. Reviews the current conversation (goal, key decisions, constraints/preferences, what's been produced, what's still open)
2. Writes a short, plain-language **summary** for you to read
3. Drafts a **continuation prompt** — written in your voice, ready to paste as the first message of a new chat — that gives a fresh Claude enough context to keep going without having seen the original thread

## Why

Long conversations get unwieldy: context limits, slow scrolling, or you just want a clean slate without losing the thread. `chat-handoff` compresses everything that matters into something portable.

**Use cases**
- Starting a fresh chat once one gets long or close to a length limit
- Handing a task off to a coworker or friend to continue in their own chat
- Archiving a conversation's state before closing it, in case you resume later
- Splitting a meandering conversation into a focused new one on just the current thread
- Saving context before switching devices or apps

## Usage

Just ask, in plain language, e.g.:

- "Summarize this chat"
- "Give me a prompt to continue this conversation"
- "Recap this thread so I can start fresh"
- "Wrap this up before I lose context"

The skill triggers automatically on requests like these — no special syntax needed.

## Output format

```
[Short summary in plain text]

**Continuation prompt:**
​```
I'm continuing an earlier conversation. Here's the context:

**What this is about:** ...
**Key context:** ...
**What's been done:** ...
**Current state:** ...
**Next step:** ...
​```
```

The continuation prompt is kept in its own fenced code block so it's a single tap-and-hold or click away from being copied.

## Installation

Download `chat-handoff.skill` and open it in Claude — click **Save skill** to install it to your account.

## Structure

```
chat-handoff/
└── SKILL.md   — skill instructions (name, trigger description, and step-by-step behavior)
```

## Notes

- Uploaded and generated files don't automatically carry over into a new conversation — the skill flags any files/artifacts by name so you know to re-attach them if needed.
- If a conversation covers multiple unrelated topics, the skill will ask which thread you want included rather than guessing.
- Worth a quick glance at the generated prompt before sharing it with someone else, since it will contain whatever was discussed.
