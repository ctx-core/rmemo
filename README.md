[//]: @formatter:off
# rmemo (Reactive Memo)

rmemo is a tiny no-fluff state management library using reactive memos & reactive signals for the server & browser. This includes:

* reactive memos
* reactive signals
* autosubscriptions
* async support
* a terse & focused api
* performance
* integration with garbage collector

| imports                                                    | size  |
|------------------------------------------------------------|:-----:|
| memo_                                                      | 372 B |
| memo_ + sig_                                               | 391 B |
| memo_ + sig_ + be_ + ctx_                                  | 499 B |
| memo_ + sig_ + be_ + ctx_ + be_memo_pair_ + be_sig_triple_ | 589 B |

## installation

```shell
npm i ctx-core
# or
npm i rmemo
```

rmemo is part of the ctx-core package so installing the ctx-core package & using the `ctx-core/rmemo` export will enable usage of rmemo. There is also a standalone `rmemo` package which exports `ctx-core/rmemo`

## usage

```ts
// users.ts
import { sig_ } from 'rmemo' // or 'ctx-core/rmemo'
export const user_a$ = sig_<User[]>([])
  .add(user_a$=>
    fetch('https://my.api/users')
      .then(res=>res.json())
      .then(user_a=>user_a$._ = user_a))
export function user__add(user:User) {
  user_a$._ = [...user_a$(), user]
}
export interface User {
  id:number
  name:string
}
```

```ts
// admins.ts
import { memo_ } from 'rmemo' // or 'ctx-core/rmemo'
import { user_a$ } from './users.js'
export const admin_a$ = memo_(()=>user_a$().filter(i=>i.isAdmin))
```

## integration with relementjs

rmemo provides optional reactivity to [relementjs](https://github.com/relementjs/relementjs). To use rmemo with  

## how is rmemo different?

rmemo is a small & focused library. It supports `memo_` (like nanostores `computed`, svelte `derived`, solidjs `createMemo`, & VanJS `derive`) & `sig_` (like nanostore `atom`, svelte `writable`, solidjs `createSignal`, & VanJS `state`).

|                                     | **rmemo** |  **nanostores**  |    **solidjs**     |    **sveltejs**    | **vanjs** |
|-------------------------------------|:---------:|:----------------:|:------------------:|:------------------:|:---------:|
| **small payload**                   |     ✅     |        ✅         |         ✅          |         ✅          |     ✅     |
| **performant**                      |     ✅     |        ✅         |         ✅          |         ✅          |     ✅     |
| **autosubscriptions**               |     ✅     |        ❌         |         ✅          |         ❌          |     ✅     |
| **server side reactivity**          |     ✅     |        ✅         |         ✅          |         ✅          |     ❌     |
| **diamond dependencies**            |     ✅     |        ✅         |         ✅          |         ✅          |     ❌     |
| **independent from component tree** |     ✅     |        ✅         |  ❌ (next version)  |         ✅          |     ✅     |
| **reactive async**                  |     ✅     | ❌ (next version) |         ✅          |         ✅          |     ❌     |
| **terse api**                       |     ✅     |        ❌         |         ❌          |         ❌          |     ✅     |
| **contexts**                        |     ✅     | ❌ (next version) | ✅ (component tree) | ✅ (component tree) |     ❌     |

Since ctx-core is a general purpose context library, ctx-core's context functions (`be_` & `ctx__new`) are compatible with all of these libraries. ctx-core context functions are included in the rmemo package.

## context

Contexts are useful for managing state & disposing of state with Garbage Collection. The current context can be filled with state. When it's time to dispose of the state, one can use Garbage Collection as long as all active references to the `ctx` are removed.

rememo includes functions to support contexts using ctx-core. ctx-core uses [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection). The `ctx` is typically passed as an argument into the function being called. If the front-end library supports `Context` components, as React, Sveltejs, Solidjs, & others do, the `ctx` can be assigned to the `Context` component.


### context example

The above example works on the browser side, since there is only one instance `user_a$` & `admin_a$` to render the UI. The server can handle multiple requests concurrency. Defining module level rmemos is not concurrency safe. Concurrent requests will result in data from one request spilling over into another request.

A `ctx` solves this issue by storing the rmemo instances in the `ctx`. Each request instantiates a `ctx` via `ctx_()`.

ctx-core usese the `be_` function to define a memoized function to set a "slot" in the `ctx`.

```ts
// users.ts
import { be_, type ctx_T, sig_ } from 'rmemo'
export const user_a$_ = be_(()=>
  sig_<User[]>([])
    .add(user_a$=>
      fetch('https://an.api/users')
        .then(res=>res.json())
        .then(user_a=>user_a$._ = user_a)))
export function user__add(ctx:ctx_T, user:User) {
  user_a$_(ctx)([...user_a$_(ctx)(), user])
}
export interface User {
  id:number
  name:string
}
```

```ts
// admins.ts
import { be_, memo_ } from 'rmemo'
import { user_a$_ } from './users.js'
export const admin_a$_ = be_(ctx=>
  memo_(()=>
    user_a$_(ctx)()
      .filter(i=>i.isAdmin)))
```

### context with helper functions example

Calling `user_a$_(ctx)()` & `admin_a$_(ctx)()` is a bit awkward. rmemo provides some helper functions.

```ts
// users.ts
import { be_sig_triple_, type ctx_T } from 'rmemo'
export const [
  user_a$_,
  user_a_
  user_a__set,
] = be_sig_triple_<User[]>(
  ()=>[]
).add((ctx, user_a$)=>
  fetch('https://an.api/users')
    .then(res=>res.json())
    .then(user_a=>user_a$._ = user_a))
export function user__add(ctx:ctx_T, user:User) {
  user_a__set(ctx, [...user_a_(ctx), user])
}
export interface User {
  id:number
  name:string
}
```

```ts
// admins.ts
import { be_memo_pair_ } from 'rmemo'
import { type User, user_a_ } from './users.js'
// uses the function argument to instantiate a rmemo
export const [
  admin_a$_,
  admin_a_,
] = be_memo_pair_(ctx=>
  user_a_(ctx)
    .filter(i=>i.isAdmin))
```

## Note about the Tag Vector Name Convention

You may have noticed that underscore casing is used & the trailing `_` for factory functions. This is from the development of the [Tag Vector](https://www.briantakita.me/posts/tag-vector-0-introduction) name convention.

## motivation

I'm a fan of reactive state management solutions provided by nanostores, solidjs, svelte, & vanJS. I wanted one of these solutions to be a general solution that I can use on the browser & server, with web UIs & domain libraries. Each of these projects are focused on their particular objectives. I found they were unable to support my use cases in one way or another.

Between an impasse in adding autosubscriptions to nanostores & adding server-side reactive support to vanJS, I created rmemo.
