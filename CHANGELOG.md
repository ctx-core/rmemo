# rmemo

## 0.13.5

### Patch Changes

- globalThis\__be_: fix: id argument + config argument

  size-limit:

      browser-only hydrate + helpers + rmemo + ctx: + 1 B

- globalThis\__be_: fix: id argument + config argument
- Updated dependencies
  - ctx-core@4.11.3

## 0.13.4

### Patch Changes

- ctx-core: ^4.11.1 -> ^4.11.2

## 0.13.3

### Patch Changes

- ctx-core: ^4.11.0 -> ^4.11.1

## 0.13.2

### Patch Changes

- ctx-core: ^4.10.1 -> ^4.11.0

## 0.13.1

### Patch Changes

- be*memosig_triple*: fix: import
- Updated dependencies
  - ctx-core@4.10.1

## 0.13.0

### Minor Changes

- minor:

      + .on: Call the rmemo & enable updates from it's parents.
      + .off: Disable updates from the rmemo's parents.

  size-limit:

      memo_: + 2 B
      memo_ sig_: + 1 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 2 B

### Patch Changes

- Updated dependencies
  - ctx-core@4.10.0

## 0.12.1

### Patch Changes

- fix: sig*,memosig*: subscribers are notified if sig is set before read

  size-limit:

      memo_: - 4 B
      memo_ sig_: - 3 B
      memo_ sig_ be_ ctx_: - 5 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: + 3 B

- Updated dependencies
  - ctx-core@4.9.1

## 0.12.0

### Minor Changes

- minor:

      + be_memosig_triple_,be_memosig_triple_T
      + sig argument in definition
      	a memo's ._ setter is active

  size-limit:

      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 8 B

### Patch Changes

- Updated dependencies
  - ctx-core@4.9.0

## 0.11.2

### Patch Changes

- ctx-core: ^4.8.1 -> ^4.8.2

## 0.11.1

### Patch Changes

- memo\_: fix: run all listeners when a listener is garbage collected

  size-limit:

      memo_: - 2 B
      memo_ sig_: - 3 B
      memo_ sig_ be_ ctx_: - 8 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 19 B

- Updated dependencies
  - ctx-core@4.8.1

## 0.11.0

### Minor Changes

- tags,tagsNS:

  nullish attributes are removed
  nullish props are set to ''

  size-limit:

      isomorphic browser: base: + 10 B
      isomorphic browser: fragment: + 15 B
      isomorphic server: base: + 3 B
      isomorphic server: fragment: + 3 B
      browser-only minimal: + 1 B
      browser-only hydrate + helpers: + 12 B
      browser-only hydrate + helpers + rmemo: + 8 B
      browser-only hydrate + helpers + rmemo + ctx: + 3 B
      isomorphic (base) browser helpers + hydrate + helpers + rmemo + ctx: + 11 B
      isomorphic (fragment) browser helpers + hydrate + helpers + rmemo + ctx: + 10 B
      server-only minimal: - 2 B
      server-only render doc + helpers: + 3 B
      server-only render doc + helpers + rmemo: - 1 B
      server-only render doc + helpers + rmemo + ctx: + 2 B
      isomorphic (base) browser helpers + doc_html_ + helpers + rmemo + ctx: + 2 B
      isomorphic (fragment) browser helpers + doc_html_ + helpers + rmemo + ctx: + 6 B

### Patch Changes

- Updated dependencies
  - ctx-core@4.8.0

## 0.10.0

### Minor Changes

- - rmemo\_\_wait

### Patch Changes

- Updated dependencies
  - ctx-core@4.7.0

## 0.9.3

### Patch Changes

- be*memo_pair*: subscriber receives a memosig argument: allows memosig.\_ = val in subscriber
- Updated dependencies
  - ctx-core@4.6.3

## 0.9.2

### Patch Changes

- minor: be*memo_pair*,be*sig_triple*: subscriber functions have get a ctx passed in:

      be_memo_pair_: (ctx:Ctx, memo:memo_T)
      be_sig_pair_: (ctx:Ctx, memo:sig_T)

  size-limit:

      memo_ sig_: + 1 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: + 17 B

- Updated dependencies
  - ctx-core@4.6.2

## 0.9.1

### Patch Changes

- fix: type inference:

      be_memo_triple_
      be_memo_triple_T
      be_sig_triple_
      be_sig_triple_T

- Updated dependencies
  - ctx-core@4.6.1

## 0.9.0

### Minor Changes

- minor:

      memo_T,sig_T:
       .rmr→.r
       .rmrs→.memor

  patch:

      rmemo_:
      	undefined value: set .key = undefined to cache value: prevent refresh from being called again
      	performance: lazily instantiate WeakRef
      	size optimization: move memo.memor = after memo.f.* =
      	rmemo_: if statements instead of &&/||

  size-limit:

      memo_: + 1 B
      memo_ sig_: - 7 B
      memo_ sig_ be_ ctx_: - 3 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 7 B

### Patch Changes

- Updated dependencies
  - ctx-core@4.6.0

## 0.8.1

### Patch Changes

- tsx: ^4.4.0 -> ^4.5.0

## 0.8.0

### Minor Changes

- minor: domain integrity: convert memo* & sig* matches memo interface: remove val argument from function:

      increases rmemo's bundle size & decreases downstream package (reljs) bundle size
      r_rmemo_→memo_:
      	.(): - val argument
      	+ readonly ._
      rw_rmemo_→sig_:
      	.(): - val argument
      	+ ._
      rwr_rmemo_→memosig_
      be_r_rmemo_pair_→be_memo_pair_
      be_r_rmemo_pair_T→be_memo_pair_T
      be_rw_rmemo_triple_→be_sig_triple_
      be_rw_rmemo_triple_T→be_sig_triple_T

  patch:

      memo_: performance optimization: array instead to Set:
      	memo.rmrs
      	refresh.s
      	refresh.S
      memo_T: rmrs is not optional

### Patch Changes

- Updated dependencies
  - ctx-core@4.5.0

## 0.7.1

### Patch Changes

- tsx: ^4.3.0 -> ^4.4.0

## 0.7.0

### Minor Changes

- memo\_: - .go
- - rwr*rmemo*: rw*rmemo* with a rmemo*def argument: same arguments as memo* but writable

### Patch Changes

- rw*rmemo*: use .val instead of .\_s & .\_v to query stored val:

      - ._s
      - ._v

- r*rmemo*: def: conditional logic: fix: keep reference to all parents to prevent parent GC
- Updated dependencies
- Updated dependencies
- Updated dependencies
- Updated dependencies
  - ctx-core@4.4.0

## 0.6.2

### Patch Changes

- rmemo: fix: types:

      r_rmemo_T<val_T>,rw_rmemo_T<val_T>: fix type:
      	object type instead of function
      	+ .get
      	+ .set
      - r_rmemo_o_T
      - r_rmemo_o_T

- Updated dependencies
  - ctx-core@4.3.1

## 0.6.1

### Patch Changes

- tsx: ^4.1.4 -> ^4.2.0

## 0.6.0

### Minor Changes

- r*rmemo*,rw*rmemo*: convert function to object: use .\_ getter/setter for value:

      ._rS→._rs

- r*rmemo*:

      .onset→._s: private callback
      move .go+._rs after ._ getter/setter
      + .get
      + .set

### Patch Changes

- rmemo\_: inline memo.\_r
- r*rmemo*: - cur_ref !== \_r check: redundant
- Updated dependencies
- Updated dependencies
- Updated dependencies
- Updated dependencies
  - ctx-core@4.3.0

## 0.5.1

### Patch Changes

- r*rmemo*: .\_r: fix: reference to memo instance:

      r_rmemo_ signal_: - 4 B
      r_rmemo_ signal_ be_ ctx_: + 3 B

- Updated dependencies
  - ctx-core@4.2.1

## 0.5.0

### Minor Changes

- renames:

      rmemo_→r_rmemo_
      read_rmemo_T->r_rmemo_T
      read_rmemo_o_T->r_rmemo_o_T
      rsig_→rw_rmemo_
      readwrite_rmemo_T→rw_rmemo_T
      readwrite_rmemo_o_T→rw_rmemo_o_T
      be_rmemo_pair_→be_r_rmemo_pair_
      be_rmemo_pair_T→be_r_rmemo_pair_T
      be_rsig_triple_→be_rw_rmemo_triple_
      be_rsig_triple_T→be_rw_rmemo_triple_T

  r*rmemo*: store value in .val instead of .\_a

  size-limit:

      r_rmemo_: - 22 B
      r_rmemo_ signal_: - 22 B
      r_rmemo_ signal_ be_ ctx_: - 23 B
      r_rmemo_ signal_ be_ ctx_ be_rmemo_pair_ be_rsig_triple_: - 24 B

### Patch Changes

- Updated dependencies
  - ctx-core@4.2.0

## 0.4.4

### Patch Changes

- be*rmemo_pair*,be*rsig_triple*: subscriber_a_THEN_config: fix: type
- Updated dependencies
  - ctx-core@4.1.1

## 0.4.3

### Patch Changes

- ctx-core: ^4.0.0 -> ^4.1.0

## 0.4.2

### Patch Changes

- tsx: ^4.1.3 -> ^4.1.4
- README: update sizes

## 0.4.1

### Patch Changes

- Updated dependencies
- Updated dependencies
- Updated dependencies
- Updated dependencies
- Updated dependencies
- Updated dependencies
  - ctx-core@4.0.0

## 0.4.0

### Minor Changes

- - rmemo_val_T
- rmemo helper functions:

  - be*rmemo_pair*
  - be_rmemo_pair_T
  - be*rsig_triple*
  - be_rsig_triple_T
  - val\__be_rmemo_pair_
  - val\_\_be_rmemo_pair_T
  - val\__be_rsig_triple_
  - val\__be_rsig_triple_T
    size-limit:
    rmemo_ signal* be* ctx\_: + 12B

### Patch Changes

- Updated dependencies
- Updated dependencies
  - ctx-core@3.4.0

## 0.3.9

### Patch Changes

- README: feature chart: - independent from UI library

## 0.3.8

### Patch Changes

- rmemo\_: remove extra return:

      rmemo_: - 1B
      rmemo_ signal_ be_ ctx_: - 6B

- Updated dependencies
  - ctx-core@3.3.3

## 0.3.7

### Patch Changes

- rmemo\_: cur_ref.l: ternery instead of bitwise:

      rmemo_: - 2B
      rmemo_ signal_: - 7B
      rmemo_ signal_ be_ ctx_: - 6B

- Updated dependencies
  - ctx-core@3.3.2

## 0.3.6

### Patch Changes

- rmemo size-limit: ctx\_ instead of ctx\_\_new
- Updated dependencies
  - ctx-core@3.3.1

## 0.3.5

### Patch Changes

- README: imports|size table: all sizes are in bytes (B)

## 0.3.4

### Patch Changes

- README: imports|size table instead of bullet list

## 0.3.3

### Patch Changes

- README: feature table: + independent from UI library

## 0.3.2

### Patch Changes

- CHANGELOG: header: fix: rmemo instead of @ctx-core/rmemo

## 0.3.1

### Patch Changes

- README: feature chart: - ecosystem of libraries:

      ctx-core is a small ecosystem of libraries:
      	all of the compared reactive libraries have ecosystems of varying size:
      		admittedly, rmemo's ecosystem is small & is based on ctx-core...yet is effective

## 0.3.0

### Minor Changes

- rmemo: export all/be\_ & all/ctx:

      + be_
      + globalThis__be_
      + be__is_source__
      + be__set
      + ctx__set
      + be__delete
      + ctx__delete
      + be__has_
      + be__ctx_
      + be__val_
      + source__map_ctx_
      + be__debug
      + ctx__new
      + is_ctx_

### Patch Changes

- Updated dependencies
  - ctx-core@3.3.0

## 0.2.3

### Patch Changes

- ctx-core: ^3.2.1 -> ^3.2.2

## 0.2.2

### Patch Changes

- fix: subscriber_a is lazy:

      rmemo: + 7B
      rmemo signal: + 8B

- Updated dependencies
  - ctx-core@3.2.1

## 0.2.1

### Patch Changes

- tsx: ^4.1.2 -> ^4.1.3

## 0.2.0

### Minor Changes

- rmemo\_: returns r_rmemo_T<val_T>
- rsig\_: returns rw_rmemo_T<val_T>
- - rw_rmemo_T<val_T>,r_rmemo_T<val_T>
- - read_r_rmemo_o_T

### Patch Changes

- r_rmemo_o_T: - val
- Updated dependencies
- Updated dependencies
- Updated dependencies
- Updated dependencies
- Updated dependencies
  - ctx-core@3.2.0

## 0.1.1

### Patch Changes

- ctx-core: ^3.0.0 -> ^3.1.0

## 0.1.0

### Minor Changes

- initial version:

  basic readme
  tests in place
  major release pending:
  more documentation
  integration with ctx-core (including front-end component library)
