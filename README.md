# DFD template

Daniel's main template with pre-commit hooks from [pre-commit.com][precommit]

## ARCHIVED

This module is no longer maintained (archived for historical purposes), and will not receive updates, even security updates.

## Metadata

### Status

[![pre-commit.ci
status](https://results.pre-commit.ci/badge/github/danielfdickinson/dfd-template/main.svg)](https://results.pre-commit.ci/latest/github/danielfdickinson/dfd-template/main)

### Demo and/or documentation site or page

Not yet created: it may never be. _([Note 3](docs/README-NOTES.md#note-3))_

### Repository URL

<https://github.com/danielfdickinson/dfd-template>

## Features and default configuration

**Note**: The default is fairly opinionated (it _is_ primarily for DFD, after
all), but can be overridden.

* Uses [EditorConfig][edconf] for an editor neutral default styling
_([Note 1](docs/README-NOTES.md#note-1))_
* Uses pre-commit to do (among other things) linting and spell checking prior
to a commit succeeding.
* For this repository we also apply the pre-commit as part of the CI pipeline
to ensure users have actually used pre-commit locally.
* Hooks we use (by purpose, not name; for the name refer to
[the pre-commit config](.pre-commit-config.yaml) in this repo). This can be
configured (at the least) to be skipped for certain files or regular
expressions (python3 regex).
	* Prevent large files from being committed
	* Prevent case-only differences in filenames
	* Prevent having a 'docstring' after code
	* Require that non-binary executables have a 'shebang'
	* Require JSON files load without error (in Python)
	* Require that files with a 'shebang' are executable
	* Prevent committing files with git merge conflict 'leftovers' (e.g. missed
	markers)
	* Ensure there are no dangling symlinks
	* Ensure TOML files load without error (in Python)
	* Ensure references to files in remote repositories are permalinks (e.g.
	references to a file in a repo on GitHub).
	* Ensure XML files load without error (in Python)
	* Prevent commit with symlinks changed to files with the content to which it
	was pointing
	* Detects committing many types of private keys
	* Sort specified files alphabetically if they are not already such (will
	fail the commit if a change is made).
	* Remove a UTF-8 byte order marker
	* Prevent addition of new git submodules
	* Check for mixed line endings (e.g. Window & Linux styles in the same file)
	* Prevent committing to specified branches
		* main or v0.x...
	* Ensure JSON files are sorted and indented with tabs (you can change that
	if you wish)
	* Prevent trailing whitespace except Markdown hard line breaks (in '.md'
	files)
	* Lints CSS
	* Lints SCSS
	* Lints Markdown
	* Lints for certain non-inclusive language
	* Lints YAML
	* Lints for secrets about to be committed
	* Enforces EditorConfig settings for files in repo
	* Spell checking uses [CSpell][cspell]
	* Defaults to using the following word lists
		* A 'technology' word list DFD has on GitHub
		* A 'misc' word list DFD has on GitHub
		* A project/or repo specific word list (starts empty, you can populate).
	* Dictionaries to apply can be overridden for certain paths or file types
		* For example you could use a french dictionary for certain files
		* TODO: Plans are to increase the number of words in Daniel's word lists
		and to split into 'tech slang', 'tech', 'missing words (en_CA bias)'
		for the default dictionaries, 'slang missing words', and 'french words
		(fr_CA bias)', and 'DFD words' (e.g. variable names and such used in
		repos by DFD).

## Using this template

### Initialize your new repository

1. Make sure you have [pre-commit][precommit] installed.
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

## Getting help, discussing, and/or modifying

* [Support and general questions](docs/SUPPORT.md)
* [Bugs and feature requests](docs/SUPPORT.md)
* [Contributing modifications to the repository](docs/CONTRIBUTING.md)

-------

## Colophon

* [Copyright and licensing](COPYING.md)
* [Inspirations, information, and source material](docs/ACKNOWLEDGEMENTS.md)
* [Notes](docs/README-NOTES.md)

[cspell]: https://cspell.org
[edconf]: https://editorconfig.org/
[precommit]: https://pre-commit.com
