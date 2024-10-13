# Git worktree

> Jakub Vokoun
> jakub.vokoun@wftech.cz

---

# Motivace

- pohodlná paralení práce ve více větvích současně
- odpadá opakované použití `git stash`
- efektivnější workflow

---

# Než začneme znovu a lépe...

`git stash` dočasně ukládá necommitované změny, následně se můžeme přepnout do další větve provést potřebné změny a pak se zase přepnout zpět.

---

# Než začneme znovu a lépe...

```sh
cd my-repo
git checkout -b feat/some-tests
vim main_test.go
git status
git add main_test.go
git stash
git checkout main
git checkout -b fix/hotfix
vim main.go
git commit -m "fix: quick hotfix"
git push --set-upstream origin
```

---

# Než začneme znovu a lépe...

```sh
git checkout feat/some-tests
git stash pop
vim main_test.go
```

---

# Začínáme

Začít můžeme hned. Buď s již exiistujícím repozitářem nebo si jej teprve naklonujeme.

## Existující repozitář

```sh
cd my-repo
git worktree add .worktrees/my-new-worktree
```

## Naklonujeme `bare` repozitář

```sh
git clone --bare https://github.com/jakub.vokoun/linux-days-2024
cd linux-days-2024
git worktree add my-new-worktree
```

---

# Cheat sheet

```sh
git worktree add my-new-worktree
```

vytvoří nový worktree s větví `my-new-worktree`

```sh
git worktree add -b foo my-new-worktree`
```

vytvoří nový worktree s větví `foo`

```sh
git worktree list
```

vypíše seznam existujícíh worktrees

```sh
git worktree remove my-new-worktree
````

odstraní worktree `my-new-worktree`

---

# Podpora IDE a editorů

Velká část IDE a editotrů podporuje práci s git worktrees. Buď nativině nebo s pomocí pluginů.

- JetBrains rodina
- VSCode / VSCodium
- Neovim
- Emacs

---

# Reference

- https://plugins.jetbrains.com/plugin/23813-git-worktree
- https://plugins.jetbrains.com/plugin/22555-git-worktree-manage
- https://marketplace.visualstudio.com/items?itemName=PhilStainer.git-worktree
- https://marketplace.visualstudio.com/items?itemName=GitWorktrees.git-worktrees
- https://github.com/ThePrimeagen/git-worktree.nvim
- https://magit.vc/

---

# Demo

- `git`
- PyCharm + plugin
- VSCode + plugin
- Neovim + plugin
- Emacs + Doom Emacs / Magit


