# Call-agent authoring skills

This repository holds skills in the Agent Skills format: one folder for each skill under `skills/`, each with a `SKILL.md` that starts with YAML frontmatter (`name`, `description`).

## Who uses these skills

- Resia Butler, in `resia-gateway`, when it writes a Call Agent's instructions.
- The Vocaleo prompt writer, in `vocaleo-gateway`, when it writes the system prompt for one call.

Each consumer has a `call-agent-authoring-skills.lock` file with one commit SHA of this repository and a script that copies that commit into its own skills folder. The copy is committed in the consumer together with the lock file. A change here reaches a consumer only when its lock file moves to a new commit.

The repository is public. The Resia gateway also serves these skills on public pages (ENG-4129).

## Rules for every skill

1. **Strategy only.** Describe what the agent does, in plain words: "press the key for the pharmacy", "stay silent and listen". Never write control syntax such as `[[DTMF:1]]`, and never name an executor tool. Each product adds its own controls.
2. **General technique only.** Never write a key press, a menu path, or a menu fact for one business or chain. Menus change, and a stale path is worse than none. Facts for one destination belong to a future Destination knowledge feature.
3. **No customer content.** No customer or organization names, no phone numbers, no person's details, and no text copied from a customer's prompt.
4. **Product-neutral.** Write for "the agent" on "the call". Do not name an internal product or executor.
5. **Plain language.** Use ASD-STE100 Simplified Technical English: short sentences, active voice, simple tenses, one term for one concept.
6. **Small.** Keep each `SKILL.md` near 120 lines or less.

## Change a skill

Open a pull request to `main`. A human reviews every content change before a consumer moves its lock file.
