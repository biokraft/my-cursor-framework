# Auto-Generating Rules from `@Docs`

Manually writing comprehensive Cursor Rules for every library and framework in your tech stack can be time-consuming. Fortunately, you can leverage Cursor's `@Docs` feature in combination with its rule-generation capabilities to semi-automate this process. By pointing Cursor to official documentation, you can ask it to extract best practices and draft initial rules for you.

## The Synergy: `@Docs` as a Source for Rules

The `@Docs` feature allows you to feed specific documentation directly to the AI. Once the AI has this focused context, you can then instruct it to synthesize that information into a structured Cursor Rule.

**The Workflow:**

1.  **Identify Key Documentation:** Pinpoint the official documentation pages that cover best practices, core APIs, common patterns, or important conventions for the library/framework you want a rule for.
2.  **Load Documentation with `@Docs`:** Use the `@Docs add [URL or path]` command to load this documentation into Cursor's context.
3.  **Prompt for Rule Generation:** Ask Cursor to generate a rule based on the provided documentation.
4.  **Refine and Save:** Review the AI-generated rule, make any necessary adjustments for clarity, completeness, or project-specific nuances, and then save it to your `.cursor/rules/` directory.

## Example: Generating a Rule for FastAPI Best Practices

Let's say you want to create a Cursor Rule that encapsulates some best practices for using FastAPI, a popular Python web framework.

**Step 1: Identify Documentation**

You might find relevant information in sections like:
-   FastAPI's official tutorial on specific features (e.g., dependency injection, error handling).
-   Guides on structuring larger applications.
-   API documentation for key modules.

For this example, let's assume we're interested in rules around path operation functions and Pydantic models.

**Step 2: Load with `@Docs`**

```plaintext
@Docs add https://fastapi.tiangolo.com/tutorial/response-model/
@Docs add https://fastapi.tiangolo.com/tutorial/body/
@Docs add https://fastapi.tiangolo.com/tutorial/handling-errors/
```

(You might add more specific pages or the main documentation URL.)

**Step 3: Prompt for Rule Generation**

```plaintext
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

Cursor will generate a draft rule. It might look something like this (abbreviated):

```markdown
# FastAPI Best Practices for Python Projects

This rule outlines best practices when developing applications with FastAPI, based on official documentation.

## 1. Pydantic for Data Validation
- Always use Pydantic models to define the structure and validation for request bodies and response data.
- Example:
  ```python
  from fastapi import FastAPI
  from pydantic import BaseModel

  class Item(BaseModel):
      name: str
      price: float
  # ...
  ```

## 2. Explicit `response_model`
- Clearly define the `response_model` in your path operation functions to ensure consistent and validated responses. This also aids OpenAPI schema generation.
- Example:
  ```python
  @app.post("/items/", response_model=Item)
  async def create_item(item: Item):
      return item
  ```

## 3. Robust Error Handling
- Use `fastapi.HTTPException` for standard HTTP errors.
- ...

## 4. Dependency Injection
- Leverage FastAPI's dependency injection system for managing dependencies like database connections or authentication logic.
- ...
```

You would then review this draft, add more details, clarify points, or include project-specific adaptations before saving it as `.cursor/rules/python-fastapi-best-practices.md`.

## Tips for Effective Rule Generation from Docs

-   **Be Specific in Your Prompts:** Tell the AI exactly what aspects of the documentation you want it to focus on for the rule.
-   **Iterate:** You might not get the perfect rule on the first try. Generate a draft, then ask for refinements or additions.
-   **One Doc at a Time (Sometimes):** If documentation for a library is vast, you might get better results by adding one specific section with `@Docs`, generating rules for that section, clearing `@Docs`, and then moving to the next section.
-   **Combine with Your Own Knowledge:** The AI provides a great starting point. Augment its output with your own expertise and project-specific requirements.

Using `@Docs` to bootstrap your tech-stack rules can save significant time and ensure your rules are well-grounded in authoritative information, leading to a more effective and knowledgeable AI coding partner. 