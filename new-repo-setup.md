*Source of inspiration:* 

[From Design doc to code: the Groundhog AI coding assistant (and new Cursor vibecoding meta)](https://ghuntley.com/specs/)

---

# How to start a new project

When starting a new project it’s recommend to use two main components when using Cursor IDE:

1. **/specs** - to store the specification of your project requirements
2. **stdlib** - for defining agent behaviour in specific cases

**/specs** ➕ **/stdlib** ➕ **loopback** = good vibes 

</aside>

## Initial Cursor rules (stdlib)

### Location & Format Guidelines for Rules

`.cursor/rules/00-mdc-guidelines.md` is the main rule file that contains the guidelines for all other rules. Always start with this file.



### Language specific rules

I will update this repo with language specific rules as I go. But if you need something specific, you can use the power of Cursor to define these rules interactively. Start of with the following prompt:

```
Create a new Cursor MDC rule for all *.py files (in all subdirectories)

You are a expert expert software engineer who knows python. Infact you are the software engineer who created python. Your task is to come up with technical recommendations in these rules which document best practices when authoring python.

Split each concern about python into seperate MDC rules.

Prefix each rule with the filename of "python-$rulename.mdc"

Write these rulse to disk
```

After it created these initial rules, feel free to adjust them to your liking or interactively define additional ones, in case your supposedly smart agent left something out.

## Coming up with the specifications

Start with a lengthy conversation with your favorite LLM about product requirements aka. specs. E.g.:

```
We are going to create an AI coding assistant command line application in rust

The AI coding assistant is called "groundhog".

It uses the "tracing" crate for logging, metrics and telemetry.
All operations have appropriate tracing on them that can be used to troubleshoot the application.

Use the clap cargo create for command line parsing.

The first operation is

"$ groundhogexplain"

When groundhog explain is invoked it prints hello world.

IMPORTANT: Write up the specifications into the "specs/" folder with each domain topic (including technical topic) as a seperate markdown file. Create a "SPECS.md" in the root of the directory which is an overview document that contains a table that links to all the specs.
```

## keep going until implemented
The next secret is really just continually issuing the same prompt

```
Study @SPECS.md for functional specifications.
Study @.cursor for technical requirements
Implement what is not implemented
Create tests
Run "cargo build" and verify the application works
Run "cargo clippy" and resolve linting errors
```
Did the LLM go on a bad path? Restart a new chat session to clear the LLM context window and use the above prompt. Keep doing it until everything is implemented.