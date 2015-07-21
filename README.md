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

### Open today's directory in a file browser
```bash
today open
```

### Change directory to today
** Requires `today` to be sourced **
```bash
today cd
```

### Print the last "today" directory
It could be yesterday, it could be older (upto a year older infact)
```
$ today last
/Users/matt/today/2015-07-20
```

### Not done with yesterday's directory?
Link today's directory with the last "today" directory
```
$ today link
/Users/matt/today/2015-07-21
$ ls -l $TODAYDIR
lrwxr-xr-x 1 matt staff 10 Jul 21 11:52 /Users/matt/today/2015-07-21 -> 2015-07-20
```

### List contents of today's directory
```
$ today ls
notes.md
$ today ls -l
total 4
-rw-r--r-- 1 matt staff 24 Jul 21 12:29 notes.md
```
Any arguments passed after ls are passed through directly to the system's `ls`.

## Customising today

It is possible to change a number of settings by writing a `~/.todayrc` file.
```bash
DATEFORMAT='%Y/%m/%d' #defaults to %Y-%m-%d
TODAYROOT=~/Documents/notes #defaults to ~/today
NOTESUFFIX=.txt #defaults to .md
```
