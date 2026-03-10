# test-binder

Course notebooks prepared for launch on MyBinder.

## Project layout

- `requirements.txt`: Python dependencies shared by local setup and Binder.
- `binder/requirements.txt`: Binder entrypoint that reuses the root `requirements.txt`.
- `binder/runtime.txt`: Python version pin used by Binder builds.
- `binder/postBuild`: post-build hook (kernel registration).
- `lesson_2_1/notebooks/`: assignment notebooks.

## Why dependencies were missing on Binder

When a `binder/` folder is present, Binder prioritizes config files from `binder/`.
Without `binder/requirements.txt`, the root `requirements.txt` may be ignored.

This repository now includes `binder/requirements.txt` with:

```txt
-r ../requirements.txt
```

so the same dependency list is used by Binder.

## Launch example

```text
https://mybinder.org/v2/gh/malmilo6/test-binder/main?filepath=lesson_2_1/notebooks/notebook_1/L2_1_N1_Assignment_EN.ipynb
```

After the environment starts, use the kernel named `Python (binder-env)`.

