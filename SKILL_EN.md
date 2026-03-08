🦞 Lobster Memory Butler v1.2 (English Version)
Eliminate API crashes. Give your OpenClaw a "sense of pain" and "self-healing" capabilities.

🌟 Why do you need it?
Many users encounter sudden freezes or system errors during long conversations.

The Truth Behind the Crash:

Framework Misleading: Many frameworks default to a 200,000 token limit, which far exceeds the actual physical limit of the model API.

Physical Ceiling: Taking DeepSeek-V3.2 as an example, its physical limit is strictly 128,000 tokens.

Logic Conflict: When the conversation penetrates the 128k ceiling, the API errors out immediately. Meanwhile, the framework (expecting a 140k trigger for 70%) fails to respond in time, causing a total system crash.

Lobster Memory Butler is the "survival kit" designed to fix this specific pain point.

✨ Core Features
Auto-Calibration: Built-in physical capacity database for mainstream models. It automatically corrects "fake parameters" to match the real API physical redline.

Smart Dual-Mode Feedback:

Comprehensive Mode: Displays a detailed memory report, risk levels, and operational suggestions to help you understand the brain state.

Routine Mode: Outputs a single-line status for daily use to maximize token savings.

Persona-Adaptive Warnings: When usage reaches 60% or 85%, the assistant will warn you naturally based on your defined persona (Analyst, Programmer, etc.).

User-Friendly Commands: Supports simple commands like "Slim down memory", "Reset brain", or "Check status".

🛠️ Installation Guide
1. Skill Definition (JSON)
Add the following definition in your OpenClaw Skill management backend:

JSON
{
  "name": "lobster_memory_management",
  "description": "Lobster Memory Butler. Supports compact, reset, status, and full_status.",
  "parameters": {
    "type": "object",
    "properties": {
      "action": { "type": "string", "enum": ["compact", "reset", "status", "full_status"] }
    },
    "required": ["action"]
  }
}
2. Inject the Logic (System Prompt)
Append the following logic to the bottom of your Assistant's System Prompt:

Calibration: Force 128,000 (for DeepSeek) with a 90% safety redline.

Interaction: Default to Routine Mode for daily tasks; switch to Comprehensive Mode upon request.

📖 User Manual
To slim down: Simply say "Slim down memory" or "Compact".

To start over: Say "Reset brain", "New topic", or send the 🧹 emoji.

To view details: Say "Full status" or "Show details" to see the complete memory health report.
