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

size chart:

- rmemo_: 358B
- rmemo_ + rsig_ : 387B
- rmemo_ + rsig_ + be_ + ctx__new: 771B

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
| **ecosystem of libraries**          |     ❌     |        ✅         |         ✅          |         ✅          |     ✅     |

Since ctx-core is a general purpose context library, ctx-core's context functions (`be_` & `ctx__new`) are 
compatible with all of these libraries.
ctx-core context functions are included in the rmemo package.
