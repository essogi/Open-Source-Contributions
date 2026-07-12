### Open-Source Contributions

**Wine — wined3d state tracking regression fix** (upstreamed, 2025)
[wine/wine@`079f26ea`](https://gitlab.winehq.org/wine/wine/-/commit/079f26eab087b7f19fb6bde00e985f8f571e54f7)

A release introduced a Direct3D implementation regression in the cult-classic Dungeon Siege. Characters no longer held their weapons; they were stuck at their feet. That suggested a transformation matrix wasn't being updated to move the weapon from the character's root bone to their hands. I found the commit that introduced it with git-bisect, and traced the bug to the stale model-view matrix. The fix was to mark the data as dirty so the state would update. Weapons were once again placed correctly.
