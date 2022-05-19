# Multiroot Workspace Pytest Coverage Debugging Issue
Not being able to use breakpoints when coverage is running is a known issue.
It is possible to disable coverage during test debugging in VS Code
by specifying a customized launch configuration that sets `PYTEST_ADDOPTS`
to `--no-cov`. However, this customized configuration only reads `launch.json`.
This repository demonstrates this "bug", which is actually documented
in the VS Code [docs](https://code.visualstudio.com/docs/python/testing#_debug-tests).

Project A demonstrates that pytest configured with the `--no-cov` option in
`pyproject.toml` can stop at breakpoints as expected. However, even though the
correct configuration settings are set in `workspace.code-workspace` Project B
shows that the same breakpoint that works in Project A does not stop
execution during test debugging. This indicates that indeed VS Code Python
only examines the `launch.json` file for a customized test debug launch
configuration. 
