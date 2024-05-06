---

layout: col-sidebar
title: OWASP DeepSecrets
tags: OWASP Secrets Secret Scanning Scanner Detection Detector Tool Code Analysis Analyzer Vulnerability Credential SAST Static Scanner Token Password Secret
level: 3.5
type: tool
pitch: Secrets scanner that understands code

---

# Introduction
## OWASP DeepSecrets - a better tool for secret scanning
Yet another tool - why?

Existing tools don't really "understand" code. Instead, they mostly parse texts.

DeepSecrets expands classic regex-search approaches with semantic analysis, dangerous variable detection, and more efficient usage of entropy analysis. Code understanding supports 500+ languages and formats and is achieved by lexing and parsing - techniques commonly used in SAST tools.

DeepSecrets also introduces a new way to find secrets: just use hashed values of your known secrets and get them found plain in your code.

# How it Works

Under the hood story is in articles here: [https://hackernoon.com/modernizing-secrets-scanning-part-1-the-problem](https://hackernoon.com/modernizing-secrets-scanning-part-1-the-problem)

# FAQ

## Mini-FAQ
> Pff, is it still regex-based?

Yes and no. Of course, it uses regexes and finds typed secrets like any other tool. But language understanding (the lexing stage) and variable detection also use regexes under the hood. So regexes is an instrument, not a problem.

> Why don't you build true abstract syntax trees? It's academically more correct!

DeepSecrets tries to keep a balance between complexity and effectiveness. Building a true AST is a pretty complex thing and simply an overkill for our specific task. So the tool still follows the generic SAST-way of code analysis but optimizes the AST part using a different approach.

> I'd like to build my own semantic rules. How do I do that?

Only through the code by the moment. Formalizing the rules and moving them into a flexible and user-controlled ruleset is in the plans.

> But what about Semgrep Secrets? Looks like you're cloning their thing.

DeepSecrets was released in April 2023 — half a year before the Semgrep Secrets release and I'm very glad to be followed. We share the same ideas and principles under the hood but:
- DeepSecrets is free, Semgrep is a commercial product
- Code analysis in DeepSecrets is wider and not limited to a specific set of languages like in Semgrep


> I still have a question

Feel free to communicate with the [maintainer](https://github.com/ntoskernel/deepsecrets/blob/main/pyproject.toml#L6-L8)
