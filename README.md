# rmemo (Reactive Memo)

rmemo is a tiny no-fluff state management library using reactive memos & reactive signals for the server &
browser. This includes:

- reactive memos
- reactive signals
- autosubscriptions
- async support
- a terse & focused api
- performance
- integration with garbage collector

| imports                     | size |
|-----------------------------|:----:|
| rmemo_                      | 356B |
| rmemo_ + rsig_              | 380B |
| rmemo_ + rsig_ + be_ + ctx_ | 771B |

## usage

```ts
import { rmemo_, rsig_ } from 'rmemo'
export const user_a$ = rsig_<User[]>([], user_a$=>
	fetch('https://an.api/users').then(res=>res.json()).then(user_a$))
export function user__add(user:User) {
	user_a$([...user_a$(), user])
	// also supports ._ getters & setters
	// user_a$._ = [...user_a$._, user]
}
```

```ts
// store/admins.ts
import { rmemo_ } from 'rmemo'
import { user_a$ } from './users.js'
export const admin_a$ = rmemo_(()=>user_a$().filter(i=>i.isAdmin))
```

*Integrations with front-end frameworks pending...*

## motivation

I'm a fan of reactive state management solutions provided by nanostores, solidjs, svelte, & vanJS. I wanted one of
these solutions to be a general solution that I can use on the browser & server, with web UIs & domain libraries.
Each of these projects are focused on their particular objectives. I found they were unable to support my use cases
in one way or another.

Between an impasse in adding autosubscriptions to nanostores & adding server-side reactive support to vanJS, I
created rmemo.

## how is rmemo different?

rmemo is a small & focused library. It supports `rmemo_` (like nanostores `computed`, svelte `derived`,
solidjs `createMemo`, & VanJS `derive`) & `rsig_` (like nanostore `atom`, svelte `writable`, solidjs
`createSignal`, & VanJS `state`).

|                                     | **rmemo** |  **nanostores**  |    **solidjs**     |    **sveltejs**    | **vanjs** |
|-------------------------------------|:---------:|:----------------:|:------------------:|:------------------:|:---------:|
| **small payload**                   |     ✅     |        ✅         |         ✅          |         ✅          |     ✅     |
| **performant**                      |     ✅     |        ✅         |         ✅          |         ✅          |     ✅     |
| **autosubscriptions**               |     ✅     |        ❌         |         ✅          |         ❌          |     ✅     |
| **server side reactivity**          |     ✅     |        ✅         |         ✅          |         ✅          |     ❌     |
| **diamond dependencies**            |     ✅     |        ✅         |         ✅          |         ✅          |     ❌     |
| **independent from component tree** |     ✅     |        ✅         |  ❌ (next version)  |         ✅          |     ✅     |
| **reactive async**                  |     ✅     | ❌ (next version) |         ✅          |         ❌          |     ❌     |
| **terse api**                       |     ✅     |        ❌         |         ❌          |         ❌          |     ✅     |
| **contexts**                        |     ✅     | ❌ (next version) | ✅ (component tree) | ✅ (component tree) |     ❌     |

Since ctx-core is a general purpose context library, ctx-core's context functions (`be_` & `ctx__new`) are
compatible with all of these libraries.
ctx-core context functions are included in the rmemo package.

## context

Contexts are useful for managing state & disposing of state with Garbage Collection. The current context can be
filled with state. When it's time to dispose of the state, one can use Garbage Collection as long as all references
to the context are removed.

rememo includes functions to support contexts using ctx-core. ctx-core uses [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).
The `ctx` is typically passed as an argument into the function being called. If the front end library supports 
`Context` components, as React, Sveltejs, Solidjs, & others do, the `ctx` can be set on the `Context` component.

A `ctx` is a Map or a nested array of maps.

```ts
export declare type MapCtx = Map<Be<unknown>|string|symbol, unknown>
export interface NestedMapCtx extends Array<NestedMapCtx|MapCtx> {
}
export type Ctx = MapCtx|NestedMapCtx
```

Most of the time, a `MapCtx` is used. A `NestedMapCtx` can be used to compose `MapCtx` to support cases such as 
domain-specific contexts & private contexts.

### context example

The above example works on the browser side, since there is only one instance `user_a$` & `admin_a$` to render the 
UI. The server can handle multiple requests concurrency. Defining module level rmemos is not concurrency safe. 
Concurrent requests will result in data from one request spilling over into another request.

A `ctx` solves this issue by storing the rmemo instances in the `ctx`. Each request instantiates a `ctx` via `ctx_()`.

ctx-core usese the `be_` function to define a memoized function to set a "slot" in the `ctx`.

```ts
import { be_, type Ctx, rsig_ } from 'rmemo'
export const user_a$_ = be_(()=>
	rsig_<User[]>([], user_a$=>
		fetch('https://an.api/users').then(res=>res.json()).then(user_a$)))
export function user__add(ctx:Ctx, user:User) {
	user_a$_(ctx)([...user_a$_(ctx), user]) [[]]
}
```

```ts
// store/admins.ts
import { be_, rmemo_ } from 'rmemo'
import { user_a$ } from './users.js'
export const admin_a$_ = be_(ctx=>
	rmemo_(()=>user_a$_(ctx)().filter(i=>i.isAdmin)))
```

Calling `user_a$_(ctx)()` & `admin_a$_(ctx)()` is a bit awkward. rmemo also provides some helper functions.

```ts
import { be_rsig_triple_, type Ctx, rsig_ } from 'rmemo'
export const [
	user_a$_,
	user_a_
	user_a__set,
] = be_rsig_triple_(()=>[],
  user_a$=>fetch('https://an.api/users').then(res=>res.json()).then(user_a$))
export function user__add(ctx:Ctx, user:User) {
	user_a__set(ctx, [...user_a_(ctx), user])
}
```

```ts
// store/admins.ts
import { rmemo_, be_rmemo_pair_ } from 'rmemo'
import { user_a_ } from './users.js'
// uses the function argument to instantiate a rmemo
export const [
	admin_a$_,
	admin_a_,
] = be_rmemo_pair_(ctx=>user_a_(ctx).filter(i=>i.isAdmin))
```

Adding contexts requires some additional code...particularly with the helper functions. The value of the trade off 
is a simpler function to return the memoized value.  Instead of `user_a$_(ctx)()`, one can call `user_a_(ctx)`.
