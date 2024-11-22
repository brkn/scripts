# Scripts

Dumb cute little scripts I've created over the last couple of years.

- [copper](#copper) - Fix RuboCop violations automatically
- [firefox-history-analysis](#firefox-history-analysis) - Analyze Firefox browsing habits
- [pomodoro](#pomodoro) - Timer for focused work sessions
- [self-control](#self-control) - Block distracting websites
- [zeitwerk-check](#zeitwerk-check) - Run Zeitwerk checks on Rails 6 projects
- [files-sorted-by-last-commit](#files-sorted-by-last-commit) - List files by last commit date
- [git-dirs-exec](#git-dirs-exec) - Run a command in each direct subfolder git repo

### copper

Ruby script that automates fixing RuboCop violations:

- Reads `.rubocop_todo.yml`, auto-fixes violations one by one, then creates commits/branches for each fix.
- **Requirements:** [Ruby](#elixir-ruby), RuboCop, git
- **Usage:** Run `copper [max_number_of_commits]` in a Ruby project with a `.rubocop_todo.yml` file.

### firefox-history-analysis

Elixir script that shows your Firefox browsing habits:

- Shows most visited sites in a graphic chart and allows you to export it as CSV.
- **Requirements:** [Elixir](#elixir-ruby), Firefox browser, [Livebook](#livebook)
- **Usage:** Open `firefox-history-analysis.livemd` in Livebook and run cells to analyze your Firefox history.

### pomodoro

Shell script for running pomodoro:

- Runs a timer for focused work. Blocks distracting sites during work. Logs work sessions to daily notes. Plays sound when time's up.
- Note: This script relies on `self-control` script. Comment out that line if you don't want to use it.
- **Requirements:** [timer](#timer), [self-control](#self-control)
- **Usage:** Run `pomodoro <duration> "<task_name>"` to start a focused work session.

### self-control

Ruby script to block distracting websites:

- Blocks sites by categories (games, social, video). Edit the hardcoded hash of sites for your liking.
- **Requirements:** [Ruby](#elixir-ruby), [SelfControl.app](#self-control-app)
- **Usage:** Run `self-control <duration> [category...]` to block sites (e.g., `./scripts/self-control 1h social video`).

### zeitwerk-check

At the time of writing I was working with bunch of ruby ~6 apps, maybe this would work with newer versions too? Try it,
let me know. Bash script that runs Zeitwerk checks on Rails 6 projects:

- Finds all Rails 6 projects in subdirectories, then runs `zeitwerk:check` on each, then shows colored output for pass/fail.
- **Requirements:** [fd](#fd), [ag](#ag), Ruby on Rails 6 apps that you want to fix. Needs to be called at your `repos/` folder or wherever your folder is for all the repos.
- **Usage:** Run `zeitwerk-check` in a directory containing Rails projects.

### git-dirs-exec

Bash script to run a command in each direct subfolder git repo:

- Finds git repositories up to 2 levels deep and runs given command in each.
- **Usage:** Run `git-dirs-exec <command>` to execute command in all git repos.

### files-sorted-by-last-commit

Ruby script to sort files by their last commit date:

- Lists all Ruby files in git repo sorted by last commit date.
- **Requirements:** [Ruby](#elixir-ruby)
- **Usage example:** Only list most recent ten: `files-sorted-by-last-commit | head -n10`


## Setup

1. Clone the repo
2. Add repo root to your PATH or use scripts with `./scripts/script-name`
3. Make scripts executable: `chmod +x ./scripts/script-name`
4. Install requirements for scripts you want to use

## Referenced Tools

### Self Control App

- [Website](https://selfcontrolapp.com/)
- [Source](https://github.com/SelfControlApp/selfcontrol)
- Install: `brew install selfcontrol`

### Timer

- Install: `brew install timer`

### RuboCop

- [Website](https://rubocop.org/)
- Install: Add to your Gemfile or `gem install rubocop`

### Livebook

- [Website](https://livebook.dev/)
- Install: `brew install livebook`

### fd

- [Source](https://github.com/sharkdp/fd)
- Install: `brew install fd`

### ag

- [Source](https://github.com/ggreer/the_silver_searcher)
- Install: `brew install ag`

### Elixir, Ruby

These are languages. If you don't care about the version managing, you can install them like this:
- `brew install ruby`
- `brew install erlang elixir`

But ideally you should know these languages. These scripts won't be much use to you if you don't know how to work with them.
