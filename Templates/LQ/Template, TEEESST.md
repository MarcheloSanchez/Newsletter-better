<%*
/*
  Basic Activity Log Template
  This template prompts for details and calculates the base XP.
*/

// Prompt for activity details:
const activity = await tp.system.prompt("Enter the activity name:");
const category = await tp.system.prompt("Enter the category (e.g., Physical, Mental, etc.):");
const rawAttributes = await tp.system.prompt("Enter comma-separated attributes (e.g., Health, Endurance):");
const attributes = rawAttributes.split(",").map(attr => attr.trim());
const effort = parseFloat(await tp.system.prompt("Enter effort (1-3):"));
const impact = parseFloat(await tp.system.prompt("Enter impact (1-3):"));
const duration = parseFloat(await tp.system.prompt("Enter duration factor (e.g., 1 for daily, 7 for weekly):"));

// Calculate XP:
const xp = effort * impact * duration;

// Get current date:
const date = tp.date.now("YYYY-MM-DD");

// Build YAML frontmatter:
let yaml = `---
activity: "${activity}"
category: "${category}"
attributes: [${attributes.map(a => `"${a}"`).join(", ")}]
effort: ${effort}
impact: ${impact}
duration: ${duration}
xp: ${xp}
date: "${date}"
completed: false
---
`;

tR += yaml;
%>
