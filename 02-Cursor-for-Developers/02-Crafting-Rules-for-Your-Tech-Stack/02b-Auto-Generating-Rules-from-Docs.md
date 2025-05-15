Unlock a **new level of AI-assisted development!** Cursor doesn't just *read* documentation with `@Docs`; it can ***forge*** brand new, tailor-made rules directly from it.

Imagine this:
> Instead of manually crafting every rule, you empower Cursor to do the heavy lifting.

And here's the **masterstroke** 🍆  
by guiding this process with your own foundational rule blueprints—like the essential [@00-cursor-rules.mdc](mdc:.cursor/rules/00-cursor-rules.mdc) for universal rule standards and [@01-mdc-guidelines.mdc](mdc:.cursor/rules/01-mdc-guidelines.mdc) for precise MDC file structure—you ensure every AI-generated rule is *born perfectly aligned* with your project's DNA.

This isn't just automation; it's about **instilling your standards into the AI from the get-go**, ensuring consistency and *dramatically* speeding up your workflow.

# Auto-Generating Rules from `@Docs`

Manually writing comprehensive Cursor Rules for every library and framework in your tech stack can be time-consuming. Fortunately, you can leverage Cursor's `@Docs` feature in combination with its rule-generation capabilities to semi-automate this process. By pointing Cursor to official documentation, you can ask it to extract best practices and draft initial rules for you.

## The Synergy: `@Docs` as a Source for Rules

The `@Docs` feature allows you to feed specific documentation directly to the AI. Once the AI has this focused context, you can then instruct it to synthesize that information into a structured Cursor Rule.

**The Workflow:**

1.  **Identify Key Documentation:** Pinpoint the official documentation pages that cover best practices, core APIs, common patterns, or important conventions for the library/framework you want a rule for.
2.  **Add Documentation Sources:** Add the identified documentation to Cursor's settings, giving each source a memorable name and providing its URL or local path.
3.  **Reference Documentation with `@Docs`:** In the chat, use `@Docs [Name]` to select the documentation source(s) you added in settings.
4.  **Prompt for Rule Generation:** Ask Cursor to generate a rule based on the provided documentation.
5.  **Refine and Save:** Review the AI-generated rule, make any necessary adjustments for clarity, completeness, or project-specific nuances, and then save it to your `.cursor/rules/` directory.

## Example: Generating a Rule for FastAPI Best Practices

Let's say you want to create a Cursor Rule that encapsulates some best practices for using FastAPI, a popular Python web framework.

**Step 1: Identify Documentation**

You might find relevant information in sections like:
-   FastAPI's official tutorial on specific features (e.g., dependency injection, error handling).
-   Guides on structuring larger applications.
-   API documentation for key modules.

For this example, let's assume we're interested in rules around path operation functions and Pydantic models.

**Step 2: Add Documentation Sources to Cursor Settings**

Before you can reference documentation in chat, you need to add it to Cursor's settings:
1. Go to Cursor's settings/preferences.
2. Find the "Features" or "Docs" section.
3. Add the FastAPI documentation pages as sources:
    *   Name: "FastAPI Response Model", URL: `https://fastapi.tiangolo.com/tutorial/response-model/`
    *   Name: "FastAPI Body", URL: `https://fastapi.tiangolo.com/tutorial/body/`
    *   Name: "FastAPI Handling Errors", URL: `https://fastapi.tiangolo.com/tutorial/handling-errors/`
(You might also add the main FastAPI documentation as a single, broader source, e.g., named "FastAPI Official".)

**Step 3: Reference Docs in Chat and Prompt for Rule Generation**

```plaintext
@Docs FastAPI Response Model
@Docs FastAPI Body
@Docs FastAPI Handling Errors

Now that you have context from the FastAPI documentation via `@Docs`:

Please draft a new Cursor Rule file named `python-fastapi-best-practices.md`.
This rule should summarize key best practices for writing FastAPI applications, focusing on:
1.  Usage of Pydantic models for request and response data validation.
2.  Properly defining `response_model` in path operation functions.
3.  Best practices for error handling, including using `HTTPException`.
4.  Recommendations for dependency injection usage for cleaner code.

Ensure the rule is formatted clearly with headings and examples where appropriate. It should adhere to the general guidelines in `@.cursor/rules/00-cursor-rules.md`.
```

**Step 4: Refine and Save**

Cursor will generate a draft rule.

You would then review this draft, add more details, clarify points, or include project-specific adaptations before saving it as `.cursor/rules/python-fastapi-best-practices.md`.

## Incorporating Master Rules

When generating new rules, it's crucial to ensure they align with your established standards for rule creation. I use two master rules that define these standards:

*   [@00-cursor-rules.mdc](mdc:.cursor/rules/00-cursor-rules.mdc): General guidelines for all Cursor rules.
*   [@01-mdc-guidelines.mdc](mdc:.cursor/rules/01-mdc-guidelines.mdc): Specific guidelines for the structure and formatting of MDC (Markdown Configuration) files.

By referencing these master rules in your prompt, you instruct the AI to generate new rules that are consistent with your existing framework.

## Tips for Effective Rule Generation from Docs

-   **Be Specific in Your Prompts:** Tell the AI exactly what aspects of the documentation you want it to focus on for the rule.
-   **Iterate:** You might not get the perfect rule on the first try. Generate a draft, then ask for refinements or additions.
-   **One Doc at a Time (Sometimes):** If documentation for a library is vast, you might get better results by adding one specific section with `@Docs`, generating rules for that section, clearing `@Docs`, and then moving to the next section.
-   **Combine with Your Own Knowledge:** The AI provides a great starting point. Augment its output with your own expertise and project-specific requirements.

Using `@Docs` to bootstrap your tech-stack rules can save significant time and ensure your rules are well-grounded in authoritative information, leading to a more effective and knowledgeable AI coding partner. 