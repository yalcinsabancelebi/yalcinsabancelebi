<div align="right">
<sub><code>yalcinsabancelebi</code></sub>
</div>

<br />

# build.<br />understand.<br />repeat.

<br />

Software, systems, and the details in between.

<a href="https://github.com/yalcinsabancelebi?tab=repositories">repositories ↗</a>&nbsp;&nbsp; / &nbsp;&nbsp;<a href="https://www.linkedin.com/in/yalcinsabancelebi">contact ↗</a>

<br />

---

<sub>[01 / perspective](#01--perspective)&nbsp;&nbsp;&nbsp; [02 / working-notes](#02--working-notes)&nbsp;&nbsp;&nbsp; [03 / questions](#03--questions)&nbsp;&nbsp;&nbsp; [04 / elsewhere](#04--elsewhere)</sub>

<br />

## 01 / perspective

I'm interested in how things work, especially when the first explanation isn't quite enough.

Most of what I enjoy building involves data, behaviour, and the space between components. I like clear interfaces, explicit trade-offs, and being able to explain why something works.

<br />

<table>
<tr>
<td width="50%" valign="top">

<sub>DESIGN</sub>

### fewer moving parts.

Small interfaces. Visible assumptions. Room to change your mind.

</td>
<td width="50%" valign="top">

<sub>IMPLEMENTATION</sub>

### more attention to them.

State transitions. Failure paths. The second attempt.

</td>
</tr>
</table>

<br />

## 02 / working notes

A few questions I like to keep close to the code.

<details>
<summary><b>01</b>&nbsp; / &nbsp;What happens twice?</summary>

<br />

A request succeeds. The response disappears. The client retries.

The interesting part is deciding what “again” should mean.

| Question | Design consequence |
| :--- | :--- |
| Can the operation be repeated safely? | Define idempotency at the right boundary. |
| Can two attempts overlap? | Make ownership and concurrency explicit. |
| Can an old result arrive late? | Decide how ordering and stale state are handled. |

A retry is part of the operation's design.

<br />

</details>

<details>
<summary><b>02</b>&nbsp; / &nbsp;Who owns the truth?</summary>

<br />

A value in a database, a cached copy, and a number on a screen can all disagree for a while.

Before choosing how to synchronize them, it helps to decide:

- which component owns the state;
- which copies are derived;
- how old a copy is allowed to be;
- what a reader should do when freshness is unknown.

Naming the owner usually makes the rest of the conversation clearer.

<br />

</details>

<details>
<summary><b>03</b>&nbsp; / &nbsp;What survives a disconnect?</summary>

<br />

Reconnecting a transport is only one step.

The application still needs to establish what was received, what was missed, and whether the previous state is useful.

```text
connection restored
    ≠
application state restored
```

That distinction can shape the protocol, the storage model, and the user experience.

<br />

</details>

<details>
<summary><b>04</b>&nbsp; / &nbsp;Can the result be explained?</summary>

<br />

An output becomes more useful when its inputs and assumptions are recoverable.

For a transformation, a model, or a business rule, I find these questions useful:

| Keep track of | So that |
| :--- | :--- |
| Input and context | The result can be interpreted. |
| Relevant version | A change can be traced. |
| Assumptions | The limits are visible. |
| An example that failed | The next iteration has something concrete to improve. |

<br />

</details>

<details>
<summary><b>05</b>&nbsp; / &nbsp;What can be removed?</summary>

<br />

An abstraction earns its place when it makes the next change easier to understand.

Sometimes the best improvement is deleting a layer, making an implicit dependency explicit, or giving one component a smaller job.

```diff
- another special case
+ a clearer boundary
```

<br />

</details>

<br />

## 03 / questions

Some topics are more interesting as questions than as labels.

<table>
<tr>
<td width="50%" valign="top">

**Systems**

Where should state live?<br />
What should happen out of order?<br />
How does a service recover?

</td>
<td width="50%" valign="top">

**Data**

What did the input leave out?<br />
Which assumptions changed?<br />
Can the conclusion be reproduced?

</td>
</tr>
<tr>
<td valign="top">

**Intelligence**

What context does the model need?<br />
Where should uncertainty remain visible?<br />
How is usefulness evaluated?

</td>
<td valign="top">

**Craft**

Can this be simpler?<br />
Will the next person understand it?<br />
What happens when it fails?

</td>
</tr>
</table>

<br />

## 04 / elsewhere

The repositories hold the implementation details.

[Browse code](https://github.com/yalcinsabancelebi?tab=repositories)&nbsp; · &nbsp;[Portfolio](https://yalcinsabancelebi.github.io)&nbsp; · &nbsp;[LinkedIn](https://www.linkedin.com/in/yalcinsabancelebi)

<br />

---

<div align="right">
<sub><a href="#readme">↑ back to top</a>&nbsp;&nbsp; / &nbsp;&nbsp;<code>y4lc1n</code></sub>
</div>
