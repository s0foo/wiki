
** MELPA
*** Add MELPA to Emacs
In init.el:
(require 'package)
(add-to-list 'package-archives '("melpa" . "https://melpa.org/packages/") t)
(package-initialize)
*** My packages list
- elfeed
- evil
- magit
*** Update MELPA packages
1. M-x package-list-packages
2. U
3. x
4. y

** Org-mode
- Refile entries: C-c C-w
- New entry (TODO, Note, Journal): C-c c

** Manual
- Access: C-h i
- For a specific function: C-h f <name of the function>
** Notes
*** Workflow
- https://unmonoqueteclea.github.io/2025-02-28-introducing-jira.el:-emacs-integration-for-jira.html
*** Shortcuts
**** General
- Save: C-x C-s
- Quit: C-x C-c
- Open file: C-x C-f
**** Links
- Open a link: C-c C-o
- Edit a link: C-c C-l
**** T
- TODO and DONE: C-c C-t
**** Editing
- Remove all newlines of a region:
  - Select the region
  - M-x replace-string
  - C-q C-j
  - RET RET
