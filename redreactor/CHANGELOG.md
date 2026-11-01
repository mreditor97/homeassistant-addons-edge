# Changelog since 0.1.6
- Drop the unused SYS_ADMIN capability (#62) 
- Add TLS, sensor and discovery options; document new Red Reactor features (#60) 
- Fix base image drift, exec the service and auto-configure MQTT (#58) 
- Drop the unused SYS_ADMIN capability

Nothing in the add-on or the Red Reactor service uses it: I2C goes
through the /dev/i2c-1 device mapping, CPU stats come from read-only
sysfs, and shutdown/restart go through the Supervisor API. The add-on
docs say to only add capabilities the software really uses, as many
lower the security rating.

hassio_api and hassio_role: manager stay, since the Supervisor's
manager role is the one that covers the host endpoints used for
shutdown and restart.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQYHMX5epbTVMa9kNL 
- Remove the battery runtime limit from the docs

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQAKkStd5ijSre5PTJ 
- Merge option type restrictions (#59) and align the new options

ina.address now allows 3 to 119, matching the service's start-up check.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQAKkStd5ijSre5PTJ 
- Add TLS, sensor and discovery options, document new Red Reactor features

- mqtt.tls options, with the /ssl folder mapped read-only for certificates
- ina.address and ina.monitor_interval (optional)
- homeassistant.discovery toggle (optional)
- Document the shutdown level, runtime limit, power and charging entities

Needs a redreactor release with these features before requirements.txt
is bumped.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQAKkStd5ijSre5PTJ 
- Restrict add-on option types to what the service accepts

The hostname is used as an MQTT topic level, so reject /, + and #.
Intervals must be positive, as 0 would spin the discovery timer.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNPGZ2ghYmuZDU86zfP 
- Fix base image drift, exec the service and auto-configure MQTT

- Build from 3.14-alpine3.22 in build.yaml to match the Dockerfile
  (it was still on the end-of-life alpine3.17), update the pinned build
  dependencies to their Alpine 3.22 versions and point Renovate's
  repology lookups at alpine_3_22.
- exec the Python process so it receives the stop signal from s6.
- Fail the build if the HA CLI download fails (curl -f), instead of
  saving an HTML error page as /usr/bin/ha.
- Make the MQTT options optional and fill any left empty from the
  Supervisor's MQTT service, add an optional client_id, and set
  exit_on_fail false so the app keeps retrying the broker.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQb2Z1A2t6zzynBCxu 
- ⬆️ Update home-assistant/cli to v5.6.0 (#57)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- Restrict workflow permissions and replace workflow_run trigger (#56) 
- 🔒 Restrict workflow token permissions and avoid workflow_run

Fix zizmor code-scanning findings:
- excessive-permissions: default every workflow to no permissions and
  grant each job only what the reusable workflow it calls declares.
- dangerous-triggers: replace the workflow_run trigger in deploy.yaml with
  push to master and published releases, running CI then deploy as
  dependent jobs (mirrors the hassio-addons app-example). ci.yaml now
  runs on pull requests and manual dispatch only.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01VpoEuBAuro3EAkZgHqh67c 
- Rename add-on to app (#55) 
- 📌 Pin shared workflows to hassio-addons/workflows v4.0.0

Replace the @main and untagged commit references with the v4.0.0
release commit so every run uses a known, versioned workflow.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01VpoEuBAuro3EAkZgHqh67c 
- 🔥 Remove 32-bit architecture support

The shared hassio-addons CI no longer builds armhf, armv7 or i386, so
drop them from app configs, build files, Renovate matchers and the
architecture badges. aarch64 and amd64 remain supported.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01VpoEuBAuro3EAkZgHqh67c 
- 🎨 Move workflow pin comment onto its own line

Prettier collapses the space before a trailing comment to one, while
yamllint requires two; a standalone comment satisfies both.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01VpoEuBAuro3EAkZgHqh67c 
- 🔒 Pin shared app workflows to a commit

Pin hassio-addons app-ci/app-deploy reusable workflows to a commit
hash, as required by zizmor's unpinned-uses policy.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01VpoEuBAuro3EAkZgHqh67c 
- 🚚 Rename add-ons to apps

Home Assistant renamed add-ons to apps in 2026.2. Update user-facing
wording, repository references and shared workflow names to match.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01VpoEuBAuro3EAkZgHqh67c 
- ⬆️ Update home-assistant/cli to v5.5.0 (#51)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- ⬆️ Update home-assistant/cli to v5.4.0 (#50)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- ⬆️ Update home-assistant/cli to v5.3.1 (#49)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- ⬆️ Update home-assistant/cli to v5.3.0 (#48)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- ⬆️ Update home-assistant/cli to v5.2.0 (#47)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- ⬆️ Update redreactor to v0.1.8 (#46) 
- ⬆️ Update redreactor to v0.1.8 
