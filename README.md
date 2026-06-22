# Agent Skills Repository

A curated collection of highly optimized, structured, and specialized skills for AI coding agents. These skills extend agent capabilities with precise workflows, domain expertise, and rigorous protocols.

By injecting these skills into an agent's context, you can elevate its performance from simple "vibe-coding" to disciplined, production-grade software engineering.

---

## 🛠️ Available Skills

### 🛡️ Adversarial Code Review (`code-review-adv`)
* **Description**: Adversarial review of a diff/PR/branch against spec, grounded in tests/lint/SAST, returning `PASS`/`CHANGES`/`BLOCKED` with specific `file:line` findings.
* **Primary Use Cases**: Automated code reviews, PR checks, pre-commit gates, or "break this code" adversarial testing.
* **Core Philosophy**: Evaluates code through the lens of a paranoid, hostile, yet highly calibrated senior reviewer. Focuses on rejecting invalid code, validating spec conformance, and requiring executable proof (tests/lints) over subjective preference.

---

## 🚀 How It Works

Each skill in this repository is packaged with a defined spec, trigger conditions, and a structured workflow that the agent must execute. 

Agents can load these skills dynamically or reference them to handle complex, specialized tasks (such as statistical analysis, A/B testing, refactoring, or rigorous code reviews) that require structured logic and strict guidelines.

### Featured Skill: Adversarial Code Review (`code-review-adv`)

This skill breaks the self-confirmation loop (where developers or agents overlook their own blind spots) by enforcing an asymmetric, adversarial contract.

#### Workflow Summary:
1. **Establish the Contract**: Gather the spec, project standards, and the target diff/branch.
2. **Isolate the Context**: Focus purely on the diff and its conformance.
3. **Run Executable Signal**: Check unit tests, lints, builds, and static analysis.
4. **Critique with Teeth**: Evaluate across spec-conformance, correctness, security, performance, design, and test adequacy.
5. **Calibrate**: Never block on style/preference (NITS); only block on correctness, security, or spec violations.
6. **Convert to Checks**: Propose concrete tests or assertions to capture findings.

#### Output Protocol:
The reviewer emits a structured report culminating in one of three verdicts:
- 🟢 **PASS**: The code successfully meets all criteria without critical flaws.
- 🟡 **CHANGES REQUESTED**: Minor or major issues exist but can be resolved easily.
- 🔴 **BLOCKED**: Critical correctness, security, or spec violations are present.

---

## 🤝 Contributing

Contributions of new, highly specialized agent skills are welcome! When creating a new skill, ensure it follows these principles:
1. **Highly Actionable**: Define clear inputs, structured workflows, and unambiguous outputs.
2. **Asymmetric / Calibrated**: Focus on finding the gap between intent and implementation.
3. **Well-Documented**: Use YAML-style metadata blocks at the top of your skill definition.

To contribute a skill, create a new folder under `skills/` and define its metadata and workflow.
