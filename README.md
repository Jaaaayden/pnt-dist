# pnt-dist

Releases of PokerNow Tracker: the install page, the wheel and `latest.json`.
Install from **<https://jaaaayden.github.io/pnt-dist/>**.

## This build or the Chrome Web Store one?

There are two builds of PokerNow Tracker. This one is the **testing build**: new
features land here first, and the ones that work move to the
[Chrome Web Store version](https://chromewebstore.google.com/detail/pokernow-tracker/pnanljjehgbnafkhfnklijgclngelbcp)
later.

| | [Chrome Web Store](https://chromewebstore.google.com/detail/pokernow-tracker/pnanljjehgbnafkhfnklijgclngelbcp) | This build |
|---|---|---|
| Who it's for | Anyone: install and play | Friends testing what's next |
| New features | Once they've been tested here | First, with every release |
| Install | One click | Python 3.11+, pipx, `pnt setup`, then load the extension unpacked |
| Where the tracker runs | Inside the extension | A companion app: a small server on your computer |
| Where your hands live | This Chrome profile's extension storage; removing the extension deletes them | A SQLite file you can open, back up or copy (`pnt where`) |
| `pnt` command line | – | ✓ |
| Updates | Chrome updates it | `pnt update`, or the HUD's update banner |

### Only in this build, for now

- **Stat outliers**: the Stats page tints a rate that's clearly off the pool:
  amber when high, teal when low.
- **Chart tab dots**: a dot marks each chart tab that has a read on the player.
- **Results counters**: the Review, Tagged, Bad beats and Session tabs count what you
  haven't looked at yet, e.g. 3 unreviewed hands from the last 14 days.
- **Line explorer ◆**: marks the lines where a player is worth ≥1 bb/100 against
  the pool.
- **Line explorer graphs**: fold equity by bet size, stab folds by board texture,
  river bluff % by size, c-bet by texture.

Experimental means they can change, move or go away between releases.

## The companion app

In this build the companion app *is* the tracker: the extension is only the HUD
and the recorder, and it reads everything from the server at
<http://127.0.0.1:52000>. `pnt setup` installs that server to start with your
computer (Windows, macOS; run `pnt serve` yourself on Linux).

The Store version has no companion. It runs the same tracker inside the
extension (Python compiled to WebAssembly), so there's nothing else to install,
but you give up:

- the `pnt` commands (`pnt range`, `pnt tags`, `pnt review`, ...);
- a database file outside Chrome that survives removing the extension;
- native speed on a long history.

## Can I use both?

Pick one per Chrome profile. Both record every PokerNow table you open, and
they don't share hands. To move, import the same PokerNow log exports into the
other one.
