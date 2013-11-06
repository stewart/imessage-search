# imessage-search

imessage-search is a simple utility to search your iMessage history on your Mac.

## Why?

Because Messages.app's built-in searching is ridiculously slow.

## Dependencies

- sqlite3 (`gem install sqlite3`)
- json (`gem install json` - should already be bundled with your Ruby)

## Installation

Just copy the script to somewhere in your path. `~/bin` is a great place for it.
If you don't currently have a `~/bin`, just do `mkdir ~/bin` and add `export
PATH="$HOME/bin:$PATH"` to your `.zshrc`, `.bashrc`, etc. I put mine in my
[dotfiles][]

`imessage-search` is not installable as a gem. Gems are only good for
application-specific tools.

[dotfiles]: https://github.com/stewart/dotfiles/blob/master/bin/imessage-search

## Usage

    imessage-search [search term]

## Configuration

`imessage-search` isn't capable (yet) of figuring out which phone number or
email address belongs to who, as the imessages database doesn't contain that
information.

If you put a `.imessage-identities` file in your `$HOME` directory,
`imessage-search` will attempt to load identities from it using `JSON.parse` and
map them to the results of it's search.

An example file:

    [
      {
        "name": "Alison",
        "identities": ["alison@gmail.com", "+5551123"]
      },
      {
        "name": "David",
        "identities": ["+5551234"]
      }
    ]

## License

MIT. Plain and simple. For more details, see the `LICENSE` file.
