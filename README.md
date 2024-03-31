# rmemo (Reactive Memo)

rmemo is a tiny no-fluff reactive state management library. The primitive is a reactive memo. A reactive signal is a reactive memo that has a public setter property. rmemo includes memosig, lock_memosig, & a rich api for your reactive state management needs. Features include:

* `memo_`
* `signal_`
* `memosig_`
* `lock_memosig_`
* general purpose contexts with [`ctx-core/be`](https://github.com/ctx-core/be)
* autosubscriptions
* async support
* a terse & focused api
* performance
* integration with garbage collector via WeakRef

| imports                                                    | size  |
|------------------------------------------------------------|:-----:|
| memo_                                                      | 376 B |
| memo_ + sig_                                               | 394 B |
| memo_ + sig_ + be_ + ctx_                                  | 498 B |
| memo_ + sig_ + be_ + ctx_ + be_memo_pair_ + be_sig_triple_ | 591 B |

## installation

[//]: @formatter:off
```shell
npm i ctx-core
# or
npm i rmemo
```
[//]: @formatter:on

rmemo is part of the [ctx-core](https://github.com/ctx-core/ctx-core) package. Importing `ctx-core/rmemo` will enable usage of rmemo. There is also a standalone `rmemo` package.

## usage

[//]: @formatter:off
```ts
// users.ts
import { sig_ } from 'rmemo' // or 'ctx-core/rmemo'
export const user_a$ = sig_<User[]>([])
  .add(user_a$=>
    fetch('https://my.api/users')
      .then(res=>res.json())
      .then(user_a=>user_a$._ = user_a)
      // Make sure async errors are handled
      .catch(err=>console.error(err)))
export function user__add(user:User) {
  user_a$._ = [...user_a$(), user]
}
export interface User {
  id:number
  name:string
}
```
[//]: @formatter:on

[//]: @formatter:off
```ts
// admins.ts
import { memo_ } from 'rmemo' // or 'ctx-core/rmemo'
import { user_a$ } from './users.js'
export const admin_a$ = memo_(()=>user_a$().filter(i=>i.isAdmin))
```
[//]: @formatter:on

## integration with relementjs

rmemo provides optional opt-in reactivity to [relementjs](https://github.com/relementjs/relementjs). Gives reativity to Element rendering, Element attributes/props rendering.

## how is rmemo different?

rmemo is a small & focused library. `memo_`  is like nanostore's `computed`, svelte's `derived`, solidjs' `createMemo`, & VanJS' `derive`. & `sig_` is like nanostore's `atom`, svelte's `writable`, solidjs' `createSignal`, & VanJS' `state`.

|                                                       | **rmemo** |  **nanostores**  |    **solidjs**     |    **sveltejs**    | **vanjs** |
|-------------------------------------------------------|:---------:|:----------------:|:------------------:|:------------------:|:---------:|
| **small payload**                                     |     ✅     |        ✅         |         ✅          |         ✅          |     ✅     |
| **performant**                                        |     ✅     |        ✅         |         ✅          |         ✅          |     ✅     |
| **autosubscriptions**                                 |     ✅     |        ❌         |         ✅          |         ❌          |     ✅     |
| **server side reactivity**                            |     ✅     |        ✅         |         ✅          |         ✅          |     ❌     |
| **diamond dependencies**                              |     ✅     |        ✅         |         ✅          |         ✅          |     ❌     |
| **independent from component tree**                   |     ✅     |        ✅         |  ❌ (next version)  |         ✅          |     ✅     |
| **reactive async**                                    |     ✅     | ❌ (next version) |         ✅          |         ✅          |     ❌     |
| **terse api**                                         |     ✅     |        ❌         |         ❌          |         ❌          |     ✅     |
| **contexts**                                          |     ✅     | ❌ (next version) | ✅ (component tree) | ✅ (component tree) |     ❌     |
| **Automatic Garbage Collection of derived reactives** |     ✅     | ❌  | ✅ | ❌ |     ✅     |

ctx-core is a general purpose context library. ctx-core's context functions (`be_` & `ctx__new`) are compatible with any state management library. rmemo exports the `ctx-core/be` package.

## advanced rmemos

| function                        | description                                                                                                                                                                                                                                   |
|---------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `.add(cb)`                      | Call the given cb when the memo loads. Used to define memo listeners, call async functions, and other tasks dependent on the memo. If the cb returns a reactive memo, the add function manages starting the memo.                             |
| `memosig_`                      | A memo signal & a settable memo. Changes to the parent memo resets the memosig, even after setting the `memosig._` prop.                                                                                                                      |
| `lock_memosig_`                 | A memo signal & a settable memo. Changes to the parent memo only resets the memosig when if the `lock_memosig._` setter was not set. If the `lock_memosig._` setter was set, then changes to the parent memo do not reset the `lock_memosig`. |
| `be_sig_triple_`                | Returns an array of 3 context be_ functions. sig object getter, value getter, & value setter                                                                                                                                                  |
| `id_be_sig_triple_`             | Same as `be_sig_triple_` + sets the id of the `be` function                                                                                                                                                                                   |
| `ns_id_be_sig_triple_`          | Same as `be_sig_triple_` + sets the id of the `be` function & operates on the given ctx namespace.                                                                                                                                            |
| `ns_be_sig_triple_`             | Same as `be_sig_triple_` & operates on the given ctx namespace.                                                                                                                                                                               |
| `be_memo_pair_`                 | Returns an array of 2 context be_ functions. memo object getter & value getter.                                                                                                                                                               |
| `id_be_memo_pair_`              | Same as `be_memo_pair_` + sets the id of the `be` function                                                                                                                                                                                    |
| `ns_id_be_memo_pair_`           | Same as `be_memo_pair_` + sets the id of the `be` function & operates on the given ctx namespace.                                                                                                                                             |
| `ns_be_memo_pair_`              | Same as `be_memo_pair_` & operates on the given ctx namespace.                                                                                                                                                                                |
| `be_memosig_triple_`            | Returns an array of 3 context be_ functions. memosig object getter, value getter, & value setter                                                                                                                                              |
| `id_be_memosig_triple_`         | Same as `be_memosig_triple_` + sets the id of the `be` function                                                                                                                                                                               |
| `ns_id_be_memosig_triple_`      | Same as `be_memosig_triple_` + sets the id of the `be` function & operates on the given ctx namespace.                                                                                                                                        |
| `ns_be_memosig_triple_`         | Same as `be_memosig_triple_` & operates on the given ctx namespace.                                                                                                                                                                           |
| `be_lock_memosig_triple_`       | Returns an array of 3 context be_ functions. lock_memosig object getter, value getter, & value setter                                                                                                                                         |
| `id_be_lock_memosig_triple_`    | Same as `be_lock_memosig_triple_` + sets the id of the `be` function                                                                                                                                                                          |
| `ns_id_be_lock_memosig_triple_` | Same as `be_lock_memosig_triple_`. Also sets the id of the `be` function & operates on the given ctx namespace.                                                                                                                               |
| `ns_be_lock_memosig_triple_`    | Same as `be_lock_memosig_triple_` & operates on the given ctx namespace.                                                                                                                                                                      |
| `rmemo__wait`                   | Wait for memo to match given condition with a timeout                                                                                                                                                                                         |
| `rmemo__off`                    | Turn off a memo & remove references to parent memos. Note that the parent memo references the child rmemo using `WeakRef`. This allows the child memo to not receive updates pending Garbage Collection.                                      |
| `rmemo__on`                     | Turn on a memo. Re-adds the memo to the WeakRef held by parent memos.                                                                                                                                                                         |
| `rmemo__unset`                  | Unset the memo value. Calling the memo again causes the memo to refresh.                                                                                                                                                                      |

## context (`ctx`)

Contexts are useful for managing state & disposing of state with Garbage Collection. The context holds state. Garbage Collection disposes the state by removing all active references to the `ctx`.

rmemo includes functions to support contexts using ctx-core. ctx-core uses [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection). By passing the `ctx` as an argument to a function. Most front-end libraries support `Context` components. These libraries include React, Sveltejs, Solidjs, & others. Assigning the `ctx` to the `Context` component give child components access to the `ctx`.

### context example

This example works on the browser side. There is only one instance `user_a$` & `admin_a$` to render the UI. The server handles concurrent requests. Concurrent requests disallows global or module variables to store request state. So memos stored as module variables is not concurrency safe.

A `ctx` solves this issue by storing the memo instances in the `ctx`. Each request instantiates a `ctx` via `ctx_()`. A shorted alias to `ctx__new()`.

ctx-core uses the `be_` function to define a memoized function to set a "slot" in the `ctx`.

[//]: @formatter:off
```ts
// users.ts
import { be_, type ctx_T, sig_ } from 'rmemo'
export const user_a$_ = be_(()=>
  sig_<User[]>([])
    .add(user_a$=>
      fetch('https://an.api/users')
        .then(res=>res.json())
        .then(user_a=>user_a$._ = user_a)
        .catch(err=>console.error(err))))
export function user__add(ctx:ctx_T, user:User) {
  user_a$_(ctx)._ = [...user_a$_(ctx)(), user]
}
export interface User {
  id:number
  name:string
}
```
[//]: @formatter:on

[//]: @formatter:off
```ts
// admins.ts
import { be_, memo_ } from 'rmemo'
import { user_a$_ } from './users.js'
export const admin_a$_ = be_(ctx=>
  memo_(()=>
    user_a$_(ctx)()
      .filter(i=>i.isAdmin)))
```
[//]: @formatter:on

### context with helper functions example

Calling `user_a$_(ctx)()` & `admin_a$_(ctx)()` is awkward. So rmemo provides some helper functions.

[//]: @formatter:off
```ts
// users.ts
import { be_sig_triple_, type ctx_T } from 'rmemo'
export const [
  user_a$_,
  user_a_,
  user_a__set,
] = be_sig_triple_<User[]>(
  ()=>[]
).add((ctx, user_a$)=>
  fetch('https://an.api/users')
    .then(res=>res.json())
    .then(user_a=>user_a$._ = user_a)
    .catch(err=>console.error(err)))
export function user__add(ctx:ctx_T, user:User) {
  user_a__set(ctx, [...user_a_(ctx), user])
}
export interface User {
  id:number
  name:string
}
```
[//]: @formatter:on

[//]: @formatter:off
```ts
// admins.ts
import { be_memo_pair_ } from 'rmemo'
import { type User, user_a_ } from './users.js'
export const [
  admin_a$_,
  admin_a_,
] = be_memo_pair_(ctx=>
  user_a_(ctx)
    .filter(i=>i.isAdmin))
```
[//]: @formatter:on

## Note about the Tag Vector Name Convention

You may have noticed the usage of underscore casing. And the trailing `_` for factory functions. The [Tag Vector](https://www.briantakita.me/posts/tag-vector-0-introduction) name system describes these patterns.

## motivation

I liked & used some popular reactive state management solutions. These popular libraries include nanostores, solidjs, svelte, & vanJS. I needed a general solution that I can use on the browser & server, with web UIs & domain libraries. For automating builds & deployments. These projects focus on their particular objectives. I found they were unable to support my use cases in one way or another.

An impasse in adding autosubscriptions to nanostores. An impasse in adding server-side reactive support to vanJS. Both led me to create rmemo.
