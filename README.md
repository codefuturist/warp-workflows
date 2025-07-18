# Warp Terminal Workflows

This repository contains custom workflows for the [Warp terminal](https://www.warp.dev/).

## Installation

To use these workflows:

1. Clone this repository:
   ```
   git clone https://github.com/codefuturist/warp-workflows.git
   ```

2. Create a symbolic link to make the workflows available to Warp:
   ```
   ln -sf /path/to/warp-workflows/.warp/workflows ~/.warp/project_workflows
   ```

3. Restart Warp to see the workflows

## Available Workflows

- **Git Status Summary**: Show a simplified git status output
- **System Information**: Display detailed system hardware and software information
- **Find Large Files**: Find and list the largest files in a directory

## Adding New Workflows

1. Create a new YAML file in the `.warp/workflows` directory
2. Follow the [Warp workflow format](https://docs.warp.dev/features/entry/yaml-workflows)
3. Commit and push your changes
4. The workflows will be available to anyone who has linked the repository

## License

MIT

## Alternative Installation

Instead of linking the entire directory, you can create symbolic links for individual workflow files:

```bash
# For each workflow file
ln -sf /path/to/warp-workflows/.warp/workflows/workflow_name.yaml ~/.warp/workflows/
```

This allows you to mix these workflows with your existing personal workflows.

## Maintenance

When you add, update, or remove workflow files in the repository, you'll need to update the symbolic links:

```bash
# After updating the repository
git pull

# Recreate the symbolic links
ln -sf /path/to/warp-workflows/.warp/workflows/*.yaml ~/.warp/workflows/
```

Alternatively, you can use this script to update all links:

```bash
#!/bin/bash
repo_path="/path/to/warp-workflows/.warp/workflows"
for file in "$repo_path"/*.yaml; do
  filename=$(basename "$file")
  ln -sf "$file" ~/.warp/workflows/
done
```

