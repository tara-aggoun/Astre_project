# ASTRE project

## Chronograms

Studies of different programs execution with bus / L1 cache / CPU / Memory / Arbiter interactions in chronograms form.

## Modelisation with Nusmv

The current models are:
- mono_proc_simple.smv: architecture with 1 cache / cpu, without memorization, the cache only forward the cpu requests.
- mono_proc_mem.smv: same architecture as before, but with memorization in the L1 cache.
- multi_proc_2.smv: architecture with 2 caches / cpus (about 20 min to verify all the specs).
- multi_proc_3.smv: architecture with 3 caches / cpus (after more than 10 hours, 0 spec verified... ;-;).

### Testing the models

Running the specifications:

```bash
nusmv models/mono_proc_simple.smv # mono processor without memorization
nusmv models/mono_proc_mem.smv # mono processor with memorization
nusmv models/multi_proc_2.smv # multi processors with 2 processor
nusmv models/mono_proc_3.smv # multi processors with 3 processor
```

#### Interactive mode

```bash
nusmv -int models/mono_proc_simple.smv
# start interactive mode
# command can be run interactively with -i instead of -r
go
pick_state -r # pick a random state
print_current_state -v # show current state, verbose
simulate -r -k 10 # generates a random sequence of 10 steps
show_traces -t # show the number of traces
show_traces 1 -v # show the first trace, verbose
```

