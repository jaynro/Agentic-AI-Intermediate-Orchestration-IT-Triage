# Project 3 – The Self-Healing Engineer (Autonomous DevOps AI)

## README

### Overview

The Self-Healing Engineer is an AI agent designed to autonomously diagnose and fix software issues, embodying the role of a DevOps/SRE or bug-fixing developer. This project demonstrates an advanced application of agentic AI: the agent uses a looping strategy to iteratively attempt solutions until the problem is resolved or a limit is reached. It integrates with a development environment – reading error logs and test results, editing code or configurations, running tests/commands – much like a human engineer working in an IDE.

> ⚠️ **Note**: This is an example capstone project. We encourage students to propose their own agent-based projects based on personal interest, experience, or industry relevance.

### Project Objectives

* **Automated Bug Fixing (Code Self-Healing)**: Identify code bugs based on failing tests, generate patches, and re-test in a loop until successful.
* **Automated Config/Environment Remediation**: Detect and resolve system misconfigurations or errors (e.g. restart services, edit settings).
* **Looping Behavior**: Use an ADK-style LoopAgent approach to iterate on fixes, learning from each failure until success or maximum retries.

### Features

* Test execution and failure detection
* Error analysis with LLM
* Code patch generation and application
* Verification of fixes via test reruns
* Iterative retry logic
* Safe escalation and rollback
* Logging and version control (per-attempt diffs and summaries)

### Usage

1. Clone this repo.
2. Navigate to the `buggy_project/` directory.
3. Run the demo:

   ```bash
   python run_self_healing.py
   ```
4. Observe:

   * Test output
   * Fix attempts with LLM-generated patches
   * Logs and diffs saved to file

### System Requirements

* Python 3.8+
* `pytest`
* OpenAI API (or a local LLM wrapper)

### Example

```
[Attempt 1] Test failure summary: AssertionError: divide(5,0) did not raise ZeroDivisionError
Proposed fix: Add check for divisor == 0 and raise ZeroDivisionError
Applying fix...
Re-running tests...
Success: All tests passed after 1 attempt 🎉
```

### Directory Structure

```
/
├── buggy_project/
│   ├── calculator.py            # Demo app with bug
│   ├── test_calculator.py      # Pytest test suite
│   ├── service.conf            # Config file for system error demo
│   ├── memory_service.py       # Dummy service with simulated log output
├── self_healing_agent.py       # Main agent implementation
├── run_self_healing.py         # Driver script for code/system fix loop
├── agent_fixes.log             # Log of attempted fixes
├── patch_attempt_*.diff        # Diffs per iteration
```

### Capstone Deliverables

* Self-Healing Agent codebase
* Log files and change history
* System and test configuration
* Presentation/demo walkthrough

### Capstone Presentation Guidance

Prepare a live demo showing:

* A failing test and agent’s fix loop
* A config issue resolved by the agent
* Logs of each iteration
* Final test pass

Include reflections on challenges, iterations, and lessons learned. This capstone demonstrates how autonomous agents can meaningfully contribute to software reliability.
