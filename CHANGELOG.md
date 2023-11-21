# rmemo

## 0.5.1

### Patch Changes

- r*rmemo*: .\_r: fix: reference to r_rmemo instance:

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
