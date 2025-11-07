# Prime

This repository contains Swagger (OpenAPI 2.0) specifications for building Microsoft Power Automate custom connectors against the TeamDynamix Web API.

## Available connectors

| Connector | Description | File |
| --- | --- | --- |
| Core administration & directory | Authentication plus directory metadata (accounts, applications, groups, industries, integrations, locations, people, type categories, and days off). | `connectors/core/TeamDynamix-Core-Administration-Directory.swagger.json` |

## Downloading a connector file

1. Navigate to the file path above in the GitHub UI.
2. Click **Raw** to open the JSON.
3. Save the page with your browser (Ctrl/Cmd+S) and ensure it retains the `.swagger.json` extension.

Alternatively, you can download a file directly with `curl`:

```bash
curl -L -o TeamDynamix-Core-Administration-Directory.swagger.json \
  https://raw.githubusercontent.com/DJR7777/prime/main/connectors/core/TeamDynamix-Core-Administration-Directory.swagger.json
```

If you need a different revision, replace `main` in the URL with the desired branch name or commit hash.

## Getting the files from this workspace into your GitHub repository

This environment cannot push directly to your GitHub repository because it has
no network credentials or remote configured. That means I can stage files and
generate commits inside this workspace, but you (or another developer) need to
pull the resulting patch into your own clone and push it to GitHub. To bring
the changes into your repo:

1. Copy the patch snippet I provide at the end of each run (it starts with
   `diff --git` and ends with `--` lines) into a local file, for example
   `ai-update.patch`.
2. From the root of your cloned repository, apply the patch:

   ```bash
   git apply ai-update.patch
   ```

3. Review the files that were added or updated. You can now commit and push
   them to GitHub as usual. For example, assuming your origin remote points to
   `https://github.com/DJR7777/prime.git`:

   ```bash
   git add connectors/core/TeamDynamix-Core-Administration-Directory.swagger.json README.md
   git commit -m "Add TeamDynamix core directory connector"
   git push origin main
   ```

If you only need a single file (for example the core directory connector
specification), copy the file contents from the diff or the final message and
save them manually. The files in this workspace live under
`connectors/<area>/`.
