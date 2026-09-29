# SiPM arrays

This directory holds a single dummy record, `S9999T`. It is a template: the real
arrays are meant to be derived from it by name, the way `V99999Z` stands in for
every germanium diode. `Legend1000Metadata` does not expand SiPM names yet, so
for now only `S9999T` resolves.

- `name` → SiPM array identifier, in the format `SXXYYE`, where `XX` is the
  zero-padded string number, `YY` the zero-padded module number on that string
  and `E` the end of the fiber module the array reads out: `T` (top) or `B`
  (bottom). `SXXYY` is the name of the fiber module, see `../fibers`. Both ends
  of a module are separate arrays, and `Legend1000Metadata` looks a record up by
  the channel name, not by the module name
- `wafer` → SiPM wafer information
  - `id` → wafer string identifier
  - `row` → physical row on the wafer where the SiPMs are taken from
- `pulse_shape` → shape of the decaying tail
  - `1` → single exponential with ~1 μs time constant
  - `2` → double exponential, fast (~10 ns) + slow (~1 μs)
  - `3` → double exponential, fast (~100 ns) + very slow (~10 μs)
- `cable_length_in_cm` → signal/power cable length. Relevant for noise/signal
  propagation characteristics
- `characterization`
  - `recommended_voltage_in_V` → recommended operational voltage
  - `breakdown_voltage_in_V` → breakdown voltage
  - `dark_count_rate_in_Hz` → dark count rate
  - `afterpulsing_prob` → probability of an afterpulse (charge trapping in the
    microcells)
  - `crosstalk_prob` → probability of optical crosstalk in the SiPM array
