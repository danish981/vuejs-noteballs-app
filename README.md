### Vuejs Notes App

Building vuejs notes taking app with auth and firebase store

### To discard changes

To discard all changes in your project, including deleting any new files you've added that haven't been committed yet,
you can use the following Git commands:

### 1. **Discard all local changes**

This will revert all modified files to their last committed state:

   ```bash
   git reset --hard
   ```

### 2. **Remove untracked files**

To delete files that are not tracked by Git (i.e., new files that haven't been committed), use:

   ```bash
   git clean -fd
   ```

### Explanation:

- `git reset --hard`: This command resets the index and working directory to the state of the last commit, effectively
  undoing all changes to tracked files.
- `git clean -fd`:
    - `-f`: Stands for "force" and is required to remove files.
    - `-d`: Removes untracked directories in addition to untracked files.

### **Warning:**

These commands are **destructive** and **cannot be undone**. Ensure you do not need the changes or new files before
running them.

### Current Video :

04 : Refs, reactive objects and non-reactive objects

- reacive objects

