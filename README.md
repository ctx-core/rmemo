# rmemo (Reactive Memo)
rmemo is a tiny (377B) no-fluff state management library using reactive memos & reactive signals for the server & 
browser. This includes:

* reactive memos
* reactive signals
* autosubscriptions
* async support
* a terse & focused api
* performance
* integration with garbage collector

## usage

```ts
import { rmemo_, rsig_ } from 'rmemo'

export const user_a$ = rsig_<User[]>([], async user_a$ => {
	user_a$(await fetch('https://an.api/users').then(res => res.json()))
})

export function user__add(user: User) {
  user_a$([...user_a$(), user])
  // also supports ._ getters & setters
  // user_a$._ = [...user_a$._, user]
}
```
```ts
// store/admins.ts
import { rmemo_ } from 'rmemo'
import { user_a$ } from './users.js'

export const admin_a$ = rmemo_(() => user_a$().filter(i => i.isAdmin))
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

|                                     | **rmemo**  |   **nanostores**   |    **solidjs**     |  **sveltejs**  |  **vanjs**  |
|-------------------------------------|:----------:|:------------------:|:------------------:|:--------------:|:-----------:|
| **small payload**                   |     ✅      |         ✅          |         ✅          |       ✅        |      ✅      |
| **performant**                      |     ✅      |         ✅          |         ✅          |       ✅        |      ✅      |
| **autosubscriptions**               |     ✅      |         ❌          |         ✅          |       ❌        |      ✅      |
| **server side reactivity**          |     ✅      |         ✅          |         ✅          |       ✅        |      ❌      |
| **diamond dependencies**            |     ✅      |         ✅          |         ✅          |       ✅        |      ❌      |
| **independent from component tree** |     ✅      |         ✅          |  ❌ (next version)  |       ✅        |      ✅      |
| **reactive async**                  |     ✅      |  ❌ (next version)  |         ✅          |       ❌        |      ❌      |
| **terse api**                       |     ✅      |         ❌          |         ❌          |       ❌        |      ✅      |
| **ecosystem of libraries**          |     ❌      |         ✅          |         ✅          |       ✅        |      ✅      |

It will not support contexts. A general purpose context library, such as ctx-core fulfills that need in a more 
effective manner. Note that ctx-core can be used with any of these libraries.
