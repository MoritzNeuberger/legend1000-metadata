# Fiber modules

This directory holds a single dummy record, `S9999`. It is a template, like the
`S9999T` array in `../sipms` and the `V99999Z` diode.

- `name` → fiber module identifier, in the format `SXXYY`, where `XX` is the
  zero-padded string number and `YY` the zero-padded module number on that
  string
- `type` → fiber module type. LEGEND-1000 instruments each string with its own
  fiber shroud, so the only value is `single_string`
- `geometry` → fiber-module-dependent geometrical information
  - `tpb` → TetraPhenyl-Butadiene evaporated layer characteristics
    - `thickness_in_nm` → thickness of the layer, which can vary between modules
- `batch` → manufacturing batch. Things like K-40 contamination can change
  between batches
