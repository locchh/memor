# Donald Hebb & Hebbian Theory

This is the idea the whole project grows from. The note covers who Hebb was, his
four big ideas, the one flaw in his theory that matters most for engineering, and
how all of it maps onto building memory for an AI agent.

## The man

**Donald Hebb** (1904–1985) was a Canadian psychologist, often called *"the father
of neuropsychology and neural networks."* In 1949 he wrote a book — *The Organization
of Behavior* — arguing that the way we think and behave comes down to **how neurons
in the brain connect to each other**. That was a bold claim at the time, and almost
everything below traces back to that single book.

## The four big ideas

### 1. The learning rule — "fire together, wire together"

Hebb's core claim, in his own words:

> *"When an axon of cell A is near enough to excite a cell B and repeatedly or
> persistently takes part in firing it, some growth process or metabolic change
> takes place in one or both cells such that A's efficiency, as one of the cells
> firing B, is increased."*

In plain terms: **if neuron A keeps helping to fire neuron B, the link from A to B
gets stronger.** This is famous as *"neurons that fire together wire together."*

One detail is easy to miss: the order matters. A has to fire *first* and help
*cause* B to fire — not just light up at the same moment. So the rule is really
about cause and timing, not mere coincidence. (Neuroscience didn't confirm this
timing detail in the lab until about 50 years later.)

There's no equation you need here. The rule is just: **the more often two things
activate together, the stronger the connection between them becomes.**

### 2. Cell assemblies — the unit of memory

When a group of neurons keeps firing together, they bind into a **cell assembly** —
a team of neurons that acts as one unit. That team is what stores a single concept,
image, or memory. (The old word for such a stored memory trace is an **engram**.)

Because the neurons in the team are all wired to each other, lighting up *part* of
the team re-lights the *whole* team. That's how a fragment of a cue brings back a
full memory — you smell something and a whole scene comes back. Hebb's model is the
reason that works.

### 3. Phase sequences — the shape of a train of thought

One cell assembly firing can trigger the next one, which triggers the next — a chain
of assemblies igniting one another in order. Hebb called this a **phase sequence**.
His striking claim: **a train of thought just *is* one of these chains.** Memory
isn't only storage; it's also the ordered links between stored things.

### 4. Reverberation — how short-term memory holds on

Before a connection becomes permanent, Hebb said, activity just keeps **looping
around the assembly** — the neurons fire each other in a circle, holding the pattern
alive for a short while. That loop is his explanation for **short-term memory**. And
if the loop runs long enough, it drives the slow physical change that turns the
pattern into **long-term memory**. This was an early version of what we now call
memory consolidation.

## The flaw that matters most for engineering

**Hebb's rule, on its own, is unstable — it breaks itself.**

Here's why: a strong connection makes neurons fire together more, which makes the
connection even stronger, which makes them fire together even more... It's a runaway
loop. Left alone, connections strengthen without limit until *everything* is wired to
*everything*, and the system can no longer tell anything apart.

Later researchers fixed this, and every fix does the same basic thing: it adds a way
to **hold connections in check and let unused ones fade**. Some connections must get
*weaker*, not just stronger. The brain also caps the total wiring so it can't all
max out at once.

**The lesson:** a working "fire together, wire together" system is only *half* about
strengthening. The other half is actively weakening and forgetting. Endless piling-on
is a bug, not a feature.

## What "Hebbian" actually means

A **Hebbian** system is one that learns by strengthening the link between two things
that activate together. What it knows lives in **the strength of its connections**,
and those strengths change based on **what tends to happen at the same time**.

| Hebbian learning | *Not* Hebbian learning |
|---|---|
| Local — uses only the two things being connected | Needs an outside "you got it wrong" signal (like most neural-net training) |
| No correct answer required | Learns from labeled, known-right examples |
| Driven by "what shows up together" | Driven by "what reduces the error" |

## Why this is the right starting point for an agent-memory project

Hebb's brain ideas line up almost one-to-one with the problems an AI memory system
has to solve:

| Hebb's idea | The agent-memory version | Where it shows up in the tools we studied |
|---|---|---|
| Things that activate together get linked | Facts that come up together get linked | mem0 links entities; cognee & zep build connection edges |
| Cell assembly (one stored memory) | One saved memory item | every tool's "memory" or "observation" |
| A fragment re-lights the whole memory | A partial query pulls back the full memory | all of them — this is just *search/recall* |
| Phase sequence (ordered chain) | Links that capture order and cause between memories | zep/Graphiti's time-ordered links |
| Looping holds it, then makes it permanent | Short-term context gets promoted to long-term | mem0 session→user; cognee's improve step; claude-mem's end-of-session compression |
| Without forgetting, it breaks | Memory must prune, de-duplicate, and expire | mem0 de-dup; zep expiring facts; cognee's forget step |

**The deepest point:** Hebb's own model only works once you add the *forgetting* half.
The simple "log everything" tools (claude-mem, engram) are great at piling memories up
but have no real way to un-link or forget. The graph-based tools (especially zep, which
can mark a fact as no-longer-true) honor the *full* picture — memory that both
strengthens **and** actively forgets.

### One important caveat: it's an inspiration, not a literal copy

These memory tools are **search-and-storage systems**, not actual Hebbian networks.
None of them keep a connection strength that quietly grows with repetition and fades
with disuse — and that fading-and-growing strength is the one thing that would make
something *truly* Hebbian.

The real Hebbian part of an AI is the language model's own weights — but those are
**frozen** once the model is trained and can't update while it's running. The memory
tools exist *precisely because* the model can't keep learning on the fly.

So treat Hebb as a **guiding star** for design — *associate, sequence, consolidate,
forget* — rather than a blueprint to copy. The day a tool gives its connections a real,
co-activation-driven strength that grows and decays, that's the day it becomes Hebbian
in fact and not just in spirit.
