# checklist

Believe in power of checklists! This is a small tool to manipulate
checklists from command line.

Dependencies: python3

## File format

checklist stores checklist in plaintext file with in simple format:

```
- [x] this item is complete
- [ ] this item is not complete
```

That's it.

## Installation

1. Grab `checklist` from the repo and download it to `~/bin/`.
2. `chmod +x ~/bin/checklist`
3. Make sure that ~/bin is in your path (e.g., run `echo $PATH`)

To update, just drop a new file over the old and repeat the procedure.

## Usage

See `checklist -h` for list of options. Two main usage patterns:

```sh
$ checklist # see remaining items
$ checklist check 5 # check item on line 5 as done (undo, if item was already done)
```

I write checklists by hand in text editor, but there is also a command to add an item:

```
$ checklist add Enter text of the item
```

There is also `--all`, that forces checklist to display all items, including items that
are already done. This is useful for reviewing the process.

And you can also specify checklist file:

```
$ checklist -f ./deploy_checklist.txt check 2
```

## Combining with other tools

How many items do I still have to do?

```
$ checklist | wc -l
```

Is there anything still left to do about `alpaca` server?

```
$ checklist -f servers.txt | grep alpaca
```

How can I use it from vim?

```
:!checklist
```

How can I copy the remaining items to clipboard (I'm on macOS)?

```
$ checklist | pbcopy
```

### License

checklist is MIT licensed.

