# Disclude

Scan source code for signs of hidden intent and obfuscation, including Unicode attacks, encoded payloads, dynamic execution patterns, and supply-chain escape hatches. This is not a general purpose vulnerability scanner: `disclude` is a static analysis tool specialized in finding hidden malicious code in C, Rust, Python, TypeScript, and Bash.

## GitHub Action YAML configuration:

```
  jobs:
    disclude:
      uses: disclude-io/.github/.github/workflows/disclude-scan.yml@main
      permissions:
        actions: read
        contents: read
        security-events: write
```

## GitHub Action YAML configuration With LLM review:

```
  jobs:
    disclude:
      uses: disclude-io/.github/.github/workflows/disclude-scan.yml@main
      secrets: inherit      # passes ANTHROPIC_API_KEY (or OPENAI_API_KEY / OLLAMA_API_KEY)
      with:
        llm: true
      permissions:
        actions: read
        contents: read
        security-events: write
```