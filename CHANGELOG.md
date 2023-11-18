# rmemo

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
      + be__has__ctx_
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

- rmemo\_: returns read_rmemo_T<val_T>
- rsig\_: returns readwrite_rmemo_T<val_T>
- - readwrite_rmemo_T<val_T>,read_rmemo_T<val_T>
- - read_rmemo_o_T

### Patch Changes

- rmemo_o_T: - val
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
