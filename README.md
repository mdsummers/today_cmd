# `today_cmd`

A simple script to create and manipulate a directory for loose files made on a particular day.

```
$ tree ~/today/
/Users/matt/today/
├── 2015-07-15
│   └── notes.md
└── 2015-07-19
    └── commandresults
```

## Getting started

Clone the repo.
```bash
git clone https://github.com/mdsummers/today_cmd.git
cd today_cmd
```

You can chose to either source the `today` script in your `.bashrc`/`.bash_profile` or install it as a standalone script. 
### Option A: Source `today` function - Preferred

Linux
```bash
echo '. /path/to/today_cmd/today' >> ~/.bashrc
. ~/.bashrc
```
On the Mac
```bash
echo '. /path/to/today_cmd/today' >> ~/.bash_profile
. ~/.bash_profile
```

### Option B: Run `today` as script
Make a symlink under your user's `bin` directory for today
```bash
ln -s /path/to/today_cmd/today ~/bin/today
```

## Usage
### Make a directory for today

```
$ today
/Users/matt/today/2015-07-15
```

### Write or amend a set of notes for today
Opens a file called `notes.md` under today's directory using the default editor.
```bash
today notes
```

### Change directory to today
** Requires `today` to be sourced **
```bash
today cd
```

## Customising today

It is possible to change a couple of settings by writing a `~/.todayrc` file.
```bash
DATEFORMAT='%Y/%m/%d' #defaults to %Y-%m-%d
TODAYROOT=~/Documents/notes #defaults to ~/today
```