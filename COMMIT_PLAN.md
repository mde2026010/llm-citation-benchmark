# Suggested Git Commit Plan

The assignment requires at least five meaningful commits. Do not use generic messages such as `update1`, `done`, or `final`.

Use a sequence like:

```bash
git add README.md paper/
git commit -m "Initial repository structure and project overview"

git add references/ data/
git commit -m "Add verified scholarly literature collection"

git add datasets/ tools/
git commit -m "Add research datasets and verification tools"

git add implementations/ tutorials/
git commit -m "Add implementations and learning resources"

git add citation-audit/
git commit -m "Document citation integrity audit methodology"
```

If you have an actual audit spreadsheet or paper PDF, add those in a separate commit after reviewing them.
