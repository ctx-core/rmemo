# rmemo

## 0.31.10

### Patch Changes

- size-limit: ^11.0.1 -> ^11.0.2
- @size-limit/preset-small-lib: ^11.0.1 -> ^11.0.2
- Updated dependencies
- Updated dependencies
  - ctx-core@5.19.1

## 0.31.9

### Patch Changes

- ctx-core: ^5.18.9 -> ^5.19.0

## 0.31.8

### Patch Changes

- ctx-core: ^5.18.8 -> ^5.18.9

## 0.31.7

### Patch Changes

- ctx-core: ^5.18.7 -> ^5.18.8

## 0.31.6

### Patch Changes

- ctx-core: ^5.18.6 -> ^5.18.7

## 0.31.5

### Patch Changes

- ctx-core: ^5.18.5 -> ^5.18.6

## 0.31.4

### Patch Changes

- ctx-core: ^5.18.4 -> ^5.18.5

## 0.31.3

### Patch Changes

- ctx-core: ^5.18.3 -> ^5.18.4

## 0.31.2

### Patch Changes

- ctx-core: ^5.18.1 -> ^5.18.2
- Updated dependencies
  - ctx-core@5.18.3

## 0.31.1

### Patch Changes

- ctx-core: ^5.18.0 -> ^5.18.1

## 0.31.0

### Minor Changes

- minor:

      + memo__bind:
      	+ _
      	+ bind

  size-limit:

      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: + 10 B

### Patch Changes

- Updated dependencies
  - ctx-core@5.18.0

## 0.30.1

### Patch Changes

- memo\_: add: fix: error when return value is nullish

  size-limit:

      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 4 B

- Updated dependencies
  - ctx-core@5.17.1

## 0.30.0

### Minor Changes

- minor:

      memo_:
      	rename internals:
      		.r→.s
      		.memor→.t
      		.f.S→.f.t
      	+ .memo_: support limiting dependent library bundle sizes by not requiring the rmemo to be imported
      	.add: no longer wraps rmemo_add_def argument with a memo_: user can return a memo from the rmemo_add_def function
      + rmemo__off__add
      rmemo__on: arguments: + off_fn?:(rmemo:rmemo_T<val_T>)=>unknown
      rmemo__on:
      rmemo__off:
      	+ <val_T> generic type
      - rmemo__add_T
      rmemo_add_def_T: arguments: - old_val

  size-limit:

      memo_: - 3 B
      memo_ sig_: - 7 B
      memo_ sig_ be_ ctx_: - 7 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 10 B

### Patch Changes

- Updated dependencies
  - ctx-core@5.17.0

## 0.29.2

### Patch Changes

- rmemo\_\_add: fix: arguments match the .add method
- Updated dependencies
  - ctx-core@5.16.2

## 0.29.1

### Patch Changes

- lock*memosig*: .get: fix: return value
- Updated dependencies

  - ctx-core@5.16.1

  size-limit:

      memo_ sig_ be_ ctx_: + 1 B

## 0.29.0

### Minor Changes

- minor:

      memo_T:
      sig_T:
      	+ .add<add_val_T>(add_def:(sig:sig_T<val_T>, prev_val:add_val_T|undefined)=>add_val_T):memo_T<val_T>
      memo_:
      sig_:
      memosig_:
      lock_memosig_:
      	arguments: - ...subscriber_a
      rmemo__subscribe→rmemo__add

  patch:

      rmemo__add: fix: add_def is not called until memo argument is called

  size-limit:

      memo_: + 20 B
      memo_ sig_: + 24 B
      memo_ sig_ be_ ctx_: + 17 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: + 27 B

### Patch Changes

- Updated dependencies
  - ctx-core@5.16.0

## 0.28.0

### Minor Changes

- minor:

      subscribers: + strong reference to return value: prevent GC
      memo_T:
      sig_T:
      	+ b?:[unknown, memo_T<unknown>][]

  size-limit:

      memo_: - 1 B
      memo_ sig_: + 1 B
      memo_ sig_ be_ ctx_: + 2 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: + 4 B

### Patch Changes

- Updated dependencies
  - ctx-core@5.15.0

## 0.27.0

### Minor Changes

- ondelete*be*: .d: fix: clear ondelete callbacks when run

### Patch Changes

- Updated dependencies
  - ctx-core@5.14.0

## 0.26.0

### Minor Changes

- minor: rmemo:

      Cancel
      nullish
      nullish__none_
      run
      sleep
      Timeout
      tup

  size-limit:

      memo_ sig_ be_ ctx_: - 1 B

### Patch Changes

- Updated dependencies
  - ctx-core@5.13.0

## 0.25.1

### Patch Changes

- ctx-core: ^5.11.0 -> ^5.12.0

## 0.25.0

### Minor Changes

- minor:

      + rmemo__on: aliased by on
      + rmemo__off: aliased by off

  size-limit:

      memo_ sig_ be_ ctx_: + 1 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 3 B

### Patch Changes

- Updated dependencies
  - ctx-core@5.11.0

## 0.24.0

### Minor Changes

- minor:

      + circular_rmemo_T
      + circular_memo_T
      + circular_sig_T
      + circular_lock_memosig_T

### Patch Changes

- Updated dependencies
  - ctx-core@5.10.0

## 0.23.1

### Patch Changes

- be*memo_pair*:
  be*sig_triple*:

      fix: jsdoc type

- Updated dependencies
- Updated dependencies
- Updated dependencies
- Updated dependencies
- Updated dependencies
  - ctx-core@5.9.0

## 0.23.0

### Minor Changes

- rmemo\_\_wait:

      always calls promise_timeout
      + .cancel(val:rmemo_val_T<_rmemo_T>)

### Patch Changes

- Updated dependencies
- Updated dependencies
  - ctx-core@5.8.0

## 0.22.0

### Minor Changes

- rmemo\_\_wait: arguments: + error?:Error
- minor:

      + relysjs__build_id:
      	+ relysjs__build_id$_
      	+ relysjs__build_id_
      	+ relysjs__build_id__set
      + relysjs__ready:
      	+ relysjs__ready$_
      	+ relysjs__ready_
      + relysjs__ready__wait

### Patch Changes

- Updated dependencies
- Updated dependencies
  - ctx-core@5.7.0

## 0.21.1

### Patch Changes

- ctx-core: ^5.6.0 -> ^5.6.1

## 0.21.0

### Minor Changes

- minor: rmemo: + be

  patch: be: arguments: fix: + config?:be_config_T<ns_T>

### Patch Changes

- Updated dependencies
- Updated dependencies
- Updated dependencies
  - ctx-core@5.6.0

## 0.20.0

### Minor Changes

- - subscribe
- - - rmemo\_\_subscribe

  size-limit:

      memo_ sig_: + 1 B
      memo_ sig_ be_ ctx_: + 2 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: + 3 B

### Patch Changes

- Updated dependencies
- Updated dependencies
  - ctx-core@5.5.0

## 0.19.8

### Patch Changes

- rmemo\_\_wait: fix: prevent early GC of internal memo
- Updated dependencies
  - ctx-core@5.4.1

## 0.19.7

### Patch Changes

- ctx-core: ^5.3.1 -> ^5.4.0

## 0.19.6bu

### Patch Changes

- ctx-core: ^5.3.0 -> ^5.3.1

## 0.19.5

### Patch Changes

- ctx-core: ^5.2.3 -> ^5.3.0

## 0.19.4

### Patch Changes

- rmemo: fix: imports
- Updated dependencies
  - ctx-core@5.2.3

## 0.19.3

### Patch Changes

- ctx-core: ^5.2.1 -> ^5.2.2

## 0.19.2

### Patch Changes

- ctx-core: ^5.2.0 -> ^5.2.1

## 0.19.1

### Patch Changes

- ctx-core: ^5.1.0 -> ^5.2.0

## 0.19.0

### Minor Changes

- minor:

      exports:
      	+ ./cli-args
      	+ ./env
      + ctx__clear
      + ondelete_be_
      + ondelete_be__val__new_T
      be_: disable circular reference guard:
      	can be enabled by running @ctx-core/preprocess with DEBUG env variable:
      		see test: 'be_|circular dependency|DEBUG=1'
      + CACHE_VERSION
      	+ CACHE_VERSION$_
      	+ CACHE_VERSION_
      	+ CACHE_VERSION__set
      + NODE_ENV
      	+ NODE_ENV$_
      	+ NODE_ENV_
      	+ NODE_ENV__set
      + VERSION
      	+ VERSION$_
      	+ VERSION_
      	+ VERSION__set
      + arg_a__pick
      + default_arg_a_
      + param_dfn_T
      + dfn_flag_r_
      + flag_a_
      + flag_r_
      + flag_r__pick
      + flag_r_arg_a_
      + flag_r_param_name_
      + flag_regex
      + import_meta_env_
      + import_meta_env__ensure
      + is_development
      	+ is_development$_
      	+ is_development_
      + is_production
      	+ is_production$_
      	+ is_production_
      + is_staging
      	+ is_staging$_
      	+ is_staging_
      + missing_env__throw
      + param_dfn_a_reducer
      + param_dfn_split_regex
      + param_name_r_param_val_a_
      + param_r_
      + parseFloat_andor_

  size-limit:

      be_: - 5 B
      be_ ctx_: - 2 B
      be_ ns_ctx_: - 1 B
      be_ ctx_ ns_ctx_: - 1 B
      memo_ sig_ be_ ctx_: - 4 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 4 B

- minor:

      + ctx__clear
      + ondelete_be_
      + ondelete_be__val__new_T

  size-limit:

      memo_ sig_ be_ ctx_: - 4 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 4 B

## 0.18.3

### Patch Changes

- tsx: ^4.6.2 -> ^4.7.0
- ctx-core: ^5.0.2 -> ^5.1.0

## 0.18.2

### Patch Changes

- ctx-core: ^5.0.1 -> ^5.0.2

## 0.18.1

### Patch Changes

- ctx-core: ^5.0.0 -> ^5.0.1

## 0.18.0

### Minor Changes

- minor: + Ctx ns (namespace):

      be_:
      Be:
      be_o_T:
      be_config_T
      Ctx:
      	generics: + ns_T
      	+ ns:ns_T
      	- is_source_
      be__has_:
      be_map__find:
      be__val_:
      be_lock_memosig_triple_:
      be_lock_memosig_triple_T:
      be_memo_pair_:
      be_memo_pair_T:
      be_memosig_triple_:
      be_memosig_triple_T:
      be_sig_triple_:
      be_sig_triple_T:
      	generics: + ns_T
      be: generics:
      	+ ns_T
      	+ ctx_T
      ctx__set:
      ctx__delete:
      	generics:
      		+ ns_T
      		+ ctx_T
      	arguments: + ns?:string
      ctx__new:
      ctx_:
      	returns Ctx<''>
      + BeMap
      + BeMapO
      + Ctx_wide_T
      + Ctx_s_T
      + Ctx_s_wide_T
      + ctx__be_T
      + ctx__get_T
      + ctx__set_T
      + ns_ctx__new
      rmemo: bundle size optimizations: .includes instead of .indexOf
      exports: + ./test
      + Expect
      + Equal
      TupleExclude: fix: type error
      + TupleMemberExtends
      + TupleValues
      + TupleConcat
      + TupleToUnion
      - be___T
      - be__return_T

  size-limit:

      memo_: - 4 B
      memo_ sig_: - 5 B
      memo_ sig_ be_ ctx_: - 34 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 35 B

### Patch Changes

- Updated dependencies
  - ctx-core@5.0.0

## 0.17.2

### Patch Changes

- ctx-core: ^4.18.0 -> ^4.19.0

## 0.17.1

### Patch Changes

- rmemo_T: fix: + |lock_memosig_T<val_T>
- Updated dependencies
- Updated dependencies
  - ctx-core@4.18.0

## 0.17.0

### Minor Changes

- lock*memosig*: \_=: sets .lock = 1 to prevent the memo_def from running
- - lock_memosig_T

### Patch Changes

- Updated dependencies
- Updated dependencies
  - ctx-core@4.17.0

## 0.16.1

### Patch Changes

- ctx-core: ^4.15.0 -> ^4.16.0

## 0.16.0

### Minor Changes

- minor:

      + lock_memosig_
      + be_lock_memsig_
      + be_lock_memsig_T

  size-limit:

      memo_ sig_: + 1 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 3 B

### Patch Changes

- Updated dependencies
  - ctx-core@4.15.0

## 0.15.2

### Patch Changes

- - globalThis\__be_memo_pair_ type declaration
- Updated dependencies
  - ctx-core@4.14.1

## 0.15.1

### Patch Changes

- ctx-core: ^4.13.0 -> ^4.14.0

## 0.15.0

### Minor Changes

- minor:

      be_:
      	store val into ctx as an id string or id as the be_...not both
      	fix: be with an id can be transplied multiple times & use the same ctx val as another transpiled be with the same id
      Be: id: string|Be

  size-limit:

      memo_ sig_ be_ ctx_: - 12 B
      memo_ sig_ be_ ctx_ be_memo_pair_ be_sig_triple_: - 9 B

### Patch Changes

- Updated dependencies
  - ctx-core@4.13.0

## 0.14.0

### Minor Changes

- globalThis\__be_: arguments match be\_

  size-limit:

      be_ ctx_: - 2 B

### Patch Changes

- Updated dependencies
  - ctx-core@4.12.0

## 0.13.6

### Patch Changes

- globalThis\__be_: fix: arguments type: + config?:be_config_T
- Updated dependencies
  - ctx-core@4.11.4

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
