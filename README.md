# obsidian-ai-fitness-coach

This repo creates workflows and memory management systems for a LLM to serve as a fitness coach with daily check-ins. The coach will write daily workout plans with clear instructions, helpful tips, and places to log what you did and any feedback to the coach. It does not provide coaching knowledge to the LLM, the quality of coaching depends heavily on the model itself and how you work with it.

## Requirements

### Obsidian Sync

The AI coach creates a workout plan and log file in markdown, it is intended to be followed on your phone in the Obsidian app. This also requires a syncing solution between your desktop and phone. This project has been tested with native Obsidian Sync, Claude, and OpenCode.

### LLM Model

You can use any, but Claude Sonnet is recommended. ChatGPT works as well.

### Agent Orchestration

You can open Claude Code, Codex, or OpenCode in the root of this folder. The agent will read its instructions on startup. In theory you can also integrate it into other platforms such as OpenClaw, but that has not been tested.

## Quick Start

1. Copy this folder into your Obsidian Vault.
1. Open Claude/Codex/OpenCode in that directory.
1. Work with the agent to develop a profile of you and your goals, a workout program, and your first workout.
   * Note: there is not a new user onboarding skill yet, so you may need to partially direct this and help the agent along.
1. Make sure Obsidian is running on your PC/mac so that the workout file syncs to your phone's Obsidian app.
1. Go workout and follow the instructions on your phone in the `sessions/pending/` folder, fill in the feedback fields as you go.
1. Open Claude/Codex/OpenCode again — the agent detects the completed session automatically (provided you filled in the feedback fields) and initiates the debrief.
1. Plan your next workout with the coach.

## Integration Options

This repo can be in `your_obsidian_workout_folder/.claude/` and Claude should automatically detect it. You can also copy or symlink these files into the configuration directory of your agent platform per its instructions on which files go where.
