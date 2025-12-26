# Codebase Search Policy

Proceed with detailed exploration.

---

# Web Search Policy

## Documentation Lookup
1. **Primary**: Use context7 (`resolve-library-id` + `get-library-docs`) for library/framework documentation.
2. **Fallback**: If context7 returns no results or incomplete info, use exa (`web_search_exa` + `get_code_context_exa`).
3. **Last Resort**: If both context7 and exa are unavailable, use built-in web search.

## GitHub Implementation Queries
- For GitHub repository details, code implementations, or open-source project analysis: use exa (`get_code_context_exa`).

## General Web Search
1. **Primary**: Use exa (`web_search_exa`).
2. **Fallback**: If exa fails, use built-in web search.
