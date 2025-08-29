# Usage

/prp:execute {prp_path}

Where prp_path is typically at {project_root}/planning/PRP.md, so we can infer the {project_root} from the location.

# Overview

PRP stands for Product Requirements Prompt, and it contains my initial ideas for a product.

This "PRP Execution Workflow" is a multi-step process for kicking off the design and early planning phases of the project.

# Step 1: Determine Intent and Target Audience

## Inputs

- {project_root}/project.hjson
- /planning/PRP.md

## Outputs

- /planning/10-PRP/intent.md
- /planning/10-PRP/target-audiences.md
- /planning/clarifying-questions.md
- Ask me to confirm target audience

## Workflow

- If {project_root}/project.hjson does not exist, create it using /src/axi/process/projects/project.example.hjson and ask me to confirm the settings are ok before proceeding.
  - Remember and refer to {project_root}/project.hjson in the future when planning phases and epics and brainstorming features.

- Analyze the features mentioned in the PRP and try to figure out my intent, and think hard about what I seem to be wanting.  Save this to a file at a new subdirectory: 10-PRP/intent.md
  - If anything could benefit from clarification from me, write those questions to /planning/clarifying-questions.md, and propose answers (and proposed alternate answers) in line with the questions.
- Also analyze who my target audience(s) seems to be, and save this to 10-PRP/target-audiences.md
- Ask me to confirm the target audience, and ask me if we should also plan for a more widespread audience (such as the general public).

# Step 2: Analysis per target audience

## Outputs

- /planning/10-PRP/inferred-features.md
- /planning/10-PRP/target-audiences-assessment.md

## Workflow

- Based on my response from step 1, modify "10-PRP/target-audiences.md" 
- For each intended target audience, give an assessment (as a percentage) of the following:
  - how feature-complete the PRP seems to be
  - infer what features could be added to make the project more feature complete, and save this 10-PRP/inferred-features.md, and give a percentage of feature-completeness after including these inferred features

- For each target audience, identify the challenges and any significant effort required in making the product production-ready.  If there will be major challenges, we should identify them as early as possible in the project lifecycle.
- Write the detailed assessment to 10-PRP/target-audiences-assessment.md, and respond to me with a summary.
- Ask me if I would like to proceed with brainstorming more features.  If yes, proceed to Step 3 - Brainstorming, otherwise skip to Step 4 - Planning.

# Step 3: Brainstorming

## Outputs

- /planning/10-PRP/brainstorming.md

## Workflow

- On your own, think up all sorts of additional features that we could add to make the product more:
  - feature-rich
  - visionary
  - productive
  - useful
  - fun
  - altruistic
- Save all these ideas to 10-PRP/brainstorming.md.
  - Sort ideas into sections of descending probability of being useful.  Example layout of sections:
  ```
# Very Likely Useful Ideas

...

# Moderately Likely Useful Ideas

...

# Possibly Useful Ideas

...

# Wild Ideas for Future Directions

- If there are a ton of features, we could split the ideas into folders:
  - /planning/10-PRP/brainstorming/9-very-interesting/*.md
  - /planning/10-PRP/brainstorming/5-moderately-interesting/*.md
  - /planning/10-PRP/brainstorming/2-possibly-interesting/*.md
  - /planning/10-PRP/brainstorming/1-wild-ideas/*.md

- Respond to me with a summary of ideas, and mention this file to me so I can have a look.  Ask me if I'd like you to brainstorm any more about any particular directions, or if I am ready to proceed with the next step (planning)

# Step 4: Planning the Phases of the Project

## Outputs

- /planning/20-phases/phases.md

## Workflow

- Based on everything so far, generate a phased plan for implementing all of the features in a logical order.
  - Assume work may occur on different feature areas in parallel.
- Write this plan to 10-PRP/phases.md
- Respond to me with a summary of phases, and ask me if I would like to make changes, or proceed to the next step.

# Step 5: Planning Epics For Each Phase

Epics are what we call the highest level tasks for a phase.

## Outputs

- /planning/20-phases/phase-{phase-id}/phase-{phase-id}-{phase-name}.md
- /planning/20-phases/phase-{phase-id}/epic-{phase-id}-{epic-id}-{epic-name}.md

Example:
- /planning/20-phases/phase-01/phase-01-MVP.md
- /planning/20-phases/phase-01/epic-01-001-Core-Functionality.md
- /planning/20-phases/phase-01/epic-01-002-User-Feedback-System.md
- /planning/20-phases/phase-02/phase-02-Public-Beta.md
- /planning/20-phases/phase-02/epic-02-001-Payment-Integration.md
- /planning/20-phases/phase-02/epic-02-002-Custom-Themes.md

## Workflow

- For each phase, write a phase overview document that tells a story with motivation for the phase, and the goals, and the rationale for inclusion of various epics.  Save this file to 20-phases/phase-{phase-id}/phase-{phase-id}-{phase-name}.md, where {phase-id} is a zero-padded number with two digits.
- For each phase, break the phase down into epics.  Epics will later be broken down into tasks.  For each epic, create an epic definition file in 20-phases/phase-{phase-id}/epic-{phase-id}-{epic-id}-{epic-name}.md where epic-id is a zero-padded number of 3 digits.
- Ask me if I'd like you to do one of the following:
  - 1. refine the phases 
  - 2. refine the epics
  - 3. refine the phases and epics
  - 4. continue with the next step

If I choose to refine, please examine the selected aspects and look for ways to make them flow in a way that will maximize project success:
- ease of implementation (assume most developoment will be carried out by agents)
- getting the most important features ready as early as possible
- proving the usefulness of the application as early as possible (evaluation by users)
- and any other factors for success you can think of.

# Step 6: Next Steps

Suggest to the user to continue with the /orch:plan command.


