# chat-handoff

A Claude Skill that turns any conversation into a concise recap and a
copy-pasteable continuation prompt, making it easy to resume in a new
chat, hand off to someone else, or archive before the conversation
becomes too long.

## What it does

When triggered, chat-handoff:

-   Reviews the current conversation, including its goal, key decisions,
    constraints, preferences, completed work, and any remaining tasks.
-   Produces a concise, plain-language summary of the conversation.
-   Generates a copy-pasteable continuation prompt that captures all the
    essential context, allowing a new Claude chat to continue seamlessly
    without access to the original conversation.

## Why

Long conversations eventually become difficult to navigate, approach
context limits, or simply benefit from a fresh start. chat-handoff
condenses everything important into a portable summary, so you can
continue your work without losing context.

## Use cases

-   Continue a long conversation in a fresh chat.
-   Hand a project off to a colleague, teammate, or friend.
-   Archive a conversation before closing it.
-   Split a broad discussion into a focused new thread.
-   Preserve context before switching devices or applications.

## Usage

Simply ask in plain language, for example:

-   "Summarize this chat."
-   "Give me a prompt to continue this conversation."
-   "Recap this thread so I can start fresh."
-   "Wrap this up before I lose context."

The skill automatically activates when it recognises requests like
these---no special syntax required.

## Output

The skill returns:

1.  A concise summary of the conversation.
2.  A copy-pasteable continuation prompt in its own fenced code block.

``` text
I'm continuing an earlier conversation. Here's the context:

**What this is about:** ...
**Key context:** ...
**What's been done:** ...
**Current state:** ...
**Next step:** ...
```

Keeping the continuation prompt in a separate code block makes it easy
to copy directly into a new conversation.

## Installation

Download `chat-handoff.skill`, open it in Claude, and select **Save
skill** to install it.

## Structure

``` text
chat-handoff/
└── SKILL.md
```

`SKILL.md` contains the skill's name, trigger description, and
behaviour.

## Notes

-   Uploaded files and generated artefacts are not automatically
    available in a new conversation. The skill lists them so you know
    what needs to be reattached.
-   If multiple unrelated topics are being discussed, the skill asks
    which thread should be included instead of making assumptions.
-   Review the generated continuation prompt before sharing it, as it
    may contain information from the conversation that you don't intend
    to share.
