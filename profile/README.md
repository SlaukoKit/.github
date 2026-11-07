<div align="center">

  <img src="https://github.com/SlaukoKit.png?size=256" alt="SlaukoKit" width="140" />

# SlaukoKit

**One person, a rented server, and a crew of AI sessions that write, check and ship the code.**

<sub>queue · workers · one reviewer · one lock · signed releases</sub>

</div>

---

Most of the code here is written by agent sessions on machines I own. They take a job
off a list, build it, check each other, run the tests, and ship it. I decide what gets
built, and I say yes to anything that leaves the building.

What makes that work isn't the model. It's the scaffolding around it: a queue, one
worker per claim, a reviewer that didn't write the change, a gate in front of every
write, and one lock for the host. The scaffolding is the interesting part of this org,
and [slaukokit.dev](https://slaukokit.dev) is where it's written up.

---

### What lives here

| Repository | What it is |
| --- | --- |
| **infra** | The fleet: queue, workers, reviews, releases |
| **network** | One remote command between machines |
| **research** | Binary analysis, live memory, schemas |
| **toolset** | MCP gateway for Gitea, OpenProject, GitHub |
| **kernel** | Game runtime: readers, Lua, overlay |

`appshell` and `payments` are supporting pieces: the shared shell the apps are built
on, and a payment provider design that is still architecture only.

---

### How it's held together

- **One owner per fact.** Extend the interface instead of shadowing it.
- **A layer must add a guarantee.** Otherwise it is a rename.
- **Tests inherit nothing.** A test that leans on another test's leftovers is a lie.
- **Derived, then proved.** A value read out of a binary is checked against the running process.
- **Fail closed.** A bad address, port or config stops startup instead of falling back.
- **Devices dial out.** No inbound ports on a workstation.

---

<div align="center">

`slk-worker` `slk-release` `slk-rpc` `retk` `devtoolset`

[**slaukokit.dev**](https://slaukokit.dev)

</div>

---

### Status

The repositories are private while the work is in development. The site carries the
long version, including the lists of what does not work yet.

MIT.
