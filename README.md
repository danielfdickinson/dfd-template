# DFD template

Daniel's main template with pre-commit hooks from <https://pre-commit.com>.

## Status

[![pre-commit.ci
status](https://results.pre-commit.ci/badge/github/danielfdickinson/dfd-template/main.svg)](https://results.pre-commit.ci/latest/github/danielfdickinson/dfd-template/main)

## Repository URL

<https://github.com/danielfdickinson/dfd-template>

## Features and default configuration

**Note**: The default is fairly opinionated (it _is_ primarily for DFD, after
all), but can be overridden.

* Uses EditorConfig for an editor neutral default styling
	* Defaults to [using tabs where possible for accessibility
	reasons][tabaccess]
	* `root = false` so that the user can set their preferred (or required for
	accessibility reasons) rendering of the tabs via a `.editorconfig` file in
	a higher level directory, or their home directory. Not doing this defeats
	the purpose of using tabs vs. spaces.
	* `tab_width` is **not** set in this repository so that the user's config
	will be used. (See above).
* Uses pre-commit to do (among other things) linting and spell checking prior
to a commit succeeding.
* For this repository we also apply the pre-commit as part of the CI pipeline
to ensure users have actually used pre-commit locally.
* Hooks we use (by purpose, not name; for the name refer to
[the pre-commit config](.pre-commit-config.yaml) in this repo). This are
configured (at the least) to be skipped for certain files or regular
expressions (python3 regex).
	* Prevent large files from being committed
	* Prevent case-only differences in filenames
	* Prevent having a 'docstring' after code
	* Require that non-binary executables have a `shebang`
	* Require JSON files load without error (in Python)
	* Require that files with a `shebang` are executable
	* Prevent committing files with git merge conflict 'leftovers' (e.g. missed
	markers)
	* Ensure there are no dangling symlinks
	* Ensure TOML files load without error (in Python)
	* Ensure references to files in remote repositories are permalinks (e.g.
	references to a file in a repo on GitHub).
	* Ensure XML files load with error (in Python)
	* Prevent commit with symlinks changed to files with the content to which it
	was pointing
	* Detects committing many types of private keys
	* Sort specified files alphabetically if they are not already such (will fail
	the commit if a change is made).
	* Remove a UTF-8 byte order marker
	* Prevent addition of new git submodules
	* Check for mixed line endings (e.g. Window & Linux styles in the same file)
	* Prevent committing to specified branches
		* main or v0.x...
	* Ensure JSON files are sorted and indented with tabs (you can change that if
	you wish)
	* Prevent trailing whitespace except Markdown hard line breaks (in '.md'
	files)
	* Lints CSS
	* Lints SCSS
	* Lints Markdown
	* Lints for certain non-inclusive language
	* Lints YAML
	* Lints for secrets about to be committed
	* Enforces EditorConfig settings for files in repo
	* Spell checking use [CSpell](https://cspell.org)
	* Defaults to using the following wordlists
		* A 'technology' wordlist DFD has on GitHub
		* A 'misc' wordlist DFD has on GitHub
		* A project/or repo specific wordlist (starts empty, you can populate).
	* Dictionaries to apply can be overridden for certain paths or file types
		* For example you could use a french dictionary for certain files
		* TODO: Plans are to increase the number of words in Daniel's wordlists
		and to split into 'tech slang', 'tech', 'missing words (en_CA bias)'
		for the default dictionaries, 'slang missing words', and 'french words
		(fr_CA bias)', and 'DFD words' (e.g. variable names and such used in
		repos by DFD).

## Using this template

### Initialize your new repository

1. Make sure you have [pre-commit](https://pre-commit.com) installed.
2. From the Web UI, choose this template when creating a new repository.
3. Clone the new repository to your local workstation.
4. Change to the directory created by cloning the new repo.
5. Execute `pre-commit install`
6. Execute `pre-commit install --hook-type commit-msg`
7. Execute `git commit` and fill in the necessary details
8. Correct any errors, if any (e.g. if you changed something more).
	1. Re-execute `git commit` (repeat until success).
9. Execute `git push`

### Make changes as you wish

And notice that many mistakes are flagged and need to be fixed before
you are able to commit. This helps keep things in great shape.

## Copyright and licensing

Copyright © 2022 Daniel F. Dickinson

### Textual content

Except where otherwise noted, textual components in this repository are licensed
under the Creative Commons Attribution Share-Alike 4.0 International license.

See [LICENSE](LICENSE) in this repository for that license.

### Code and configuration

Except where otherwise noted, and where applicable, code and configurations in
this repository are licensed under an MIT license.

See [LICENSE-CODE-AND-CONFIGS](LICENSE-CODE-AND-CONFIGS) in this repository for
that license.

[tabaccess]: https://www.brycewray.com/posts/2022/06/accessibility-argument-tabs-spaces/
