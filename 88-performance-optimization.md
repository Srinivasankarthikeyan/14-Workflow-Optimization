# 88. Workflow Performance Optimization

Optimizing GitHub Actions workflows helps reduce execution time and cost.

## Best Practices

### 1. Use Specific Action Versions
Use full SHAs for security and stability, but pinned major versions (e.g., `@v4`) are common for balance.

### 2. Caching Dependencies
Use `actions/cache` or built-in caching in `setup-*` actions to avoid re-downloading dependencies.

### 3. Use Faster Runners
GitHub-hosted runners are convenient, but self-hosted or "larger" runners can be faster for heavy workloads.

### 4. Optimize Docker
- Use small base images (e.g., Alpine).
- Leverage Docker layer caching.
- Use `docker/build-push-action` with `type=gha` cache.

### 5. Conditional Execution
Use `on.push.paths` or `on.pull_request.paths` to trigger workflows only when relevant files change.

### 6. Parallelism
Use the `strategy.matrix` to run jobs in parallel.

### 7. Fail Fast
Set `strategy.fail-fast: true` to stop all matrix jobs if one fails.
