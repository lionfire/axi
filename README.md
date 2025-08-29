# Axi

This is my personal AI coding agent framework, currently designed for Claude Code.
(The axi name may change.)

## Status: Ready Now

- **PRP Execution:** take your PRP (product requirements prompt) which can be a simple sentence, and turn it into a complete project plan that is ready to build.

## Status: Coming soon, perhaps

- VS Code devcontainer setup
  - this will allow you to run Claude Code in dangerously skip permissions mode but retain a measure of safety
- TMUX Orchestration
  - for now, check out https://github.com/Jedward23/Tmux-Orchestrator.  I am working on integrating orchestration with automatic task dispatching.

# Documentation

## PRP

Command: /prp:execute

Read [.claude/commands/prp/execute](prp/execute.md) to see how it works.

Highlights:
- inferred features
- target audience
- clarifying questions
  - with suggested answers
- Planning: phases > epics > tasks
  - emphasis on parallel execution

Tip:
- After it's done, just say "do it" to see if Claude Code can actually build it.
  - (I am experimenting with more sophisticated orchestration.)
