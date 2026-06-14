# Hermes Agent: multi-profiles + gateway service mode

## Task 1 — Do `default`, `coder`, `personal` each need a gateway for distinct Slack bots/channels?
- Profiles isolate Hermes state (config/state/skills/memory), but a **distinct Slack bot identity** requires **distinct Slack bot tokens**.
- Therefore, to run different Slack bots per profile, run a **separate Hermes gateway per profile** so each profile uses its own Slack token set.
- Practical implication:
  - `default`: use `hermes gateway ...` (no `-p`)
  - `coder`: use `hermes -p coder gateway ...`
  - `personal`: use `hermes -p personal gateway ...`

## Task 2 — Does `hermes gateway start` for the default profile require `sudo`?
- No for the **user service**.
- `sudo` is for **installing/managing system-level services**, e.g. `sudo hermes gateway install --system`.

## Task 3 — Why run the default profile gateway as a system service (`--system`)?
Reasons:
- Survives logout (system services continue without interactive user session).
- Can start at boot (independent of user login).
Tradeoff:
- Requires `sudo` to install/manage the system unit.

## Task 4 — Can `coder` and `personal` profiles also run their gateways as system services?
- Yes.
- Use the same system-install mode per profile (i.e., install their gateways with `--system`).
- Each profile installs its own service name/file, so installations don’t clash.

## Task 5 — Switch default gateway from system service to user service
Steps:
1) Stop/uninstall the system service for `default`:
   - `sudo hermes gateway stop --system` (if needed)
   - `sudo hermes gateway uninstall --system`
2) Install the user service for `default`:
   - `hermes gateway install`
3) Start + verify:
   - `hermes gateway start`
   - `hermes gateway status` (user service)
   - `hermes gateway status --system` (should be inactive/absent)


## Task 6 - schedule daily search for new articles about agents



`xurl search "is:verified has:links agent" -n 20`

