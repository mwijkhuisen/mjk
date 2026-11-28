# Interface icons

Exported on 2026-11-28 from the board "Foundations" of the design canvas (see `../../HANDOFF.md` §2 and §3). Each file is a 24 × 24 inline-SVG source with `fill="none"`, `stroke="currentColor"`, `stroke-width="2"`, round caps and joins and `aria-hidden="true"`; no `style`, no `id`, no `href`. The build turns them into components in `apps/web/src/components/ui/icons.tsx`, which draws at stroke 2.5 today. "Same drawing" means the existing component has this geometry at the old stroke.

| File | Meaning (canvas label) | In `icons.tsx` |
|---|---|---|
| search.svg | search | IconSearch (existing, same drawing) |
| menu.svg | menu | no |
| close.svg | close | IconCross (existing, same drawing) |
| pin.svg | pin | IconMapPin (existing, same drawing) |
| locate.svg | locate | no |
| filter.svg | filter | no |
| check.svg | check | IconCheck (existing, same drawing) |
| question.svg | question | IconQuestion (existing, same drawing) |
| external.svg | external | IconExternal (existing, same drawing) |
| globe.svg | globe | IconGlobe (existing, same drawing) |
| right.svg | right | IconChevronRight (existing, same drawing) |
| left.svg | left | no |
| down.svg | down | no |
| info.svg | info | IconInfo (existing, same drawing) |
| alert.svg | alert | no |
| bookmark.svg | bookmark | no |
| stamp.svg | stamp | no |
| star.svg | star | no |
| calendar.svg | calendar | no |
| card.svg | card | no |
| building.svg | building | no |
| closed.svg | closed | IconClosed (existing, same drawing) |
| user.svg | user | no |
| flag.svg | flag | no |
| up.svg | up | no |
| comment.svg | comment | no |
| photo.svg | photo | no |
| moon.svg | moon | no |
| list.svg | list | no |
| map.svg | map | no |
| passport.svg | passport | no |
| edit.svg | edit | no |
| trash.svg | trash | no |
| plus.svg | plus | no |
| sort.svg | sort | no |

Not on the HANDOFF list but on the canvas: `star` and `moon`. One meaning per icon: `card` is the Museumkaart, `stamp` visited, `building` a registered museum, `bookmark` the wishlist.
