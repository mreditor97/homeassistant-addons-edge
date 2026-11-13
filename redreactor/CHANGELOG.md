# Changelog since 0.1.6
- Update the edge app to redreactor 0.1.9a599 
- Update the edge app to redreactor 0.1.9a598 
- ⬆️ Update home-assistant/cli to v5.7.0 (#75)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- Update the edge app to redreactor 0.1.9a597 
- Update the edge app to redreactor 0.1.9a596 
- Update the edge app to redreactor 0.1.9a595 
- Update the edge app to redreactor 0.1.9a594 
- 🔧 Tighten the options schema to the service's start-up limits (#73) 
- 🔧 Require a birth message payload when one is set

The service refuses an empty homeassistant.status_online at start-up.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQAKkStd5ijSre5PTJ 
- Merge branch 'claude/project-thread-juto9j' of https://github.com/mreditor97/app-redreactor into claude/project-thread-juto9j 
- Add Home Assistant birth message topic and payload options

Lets the add-on set homeassistant.status_topic and status_online, which
Red Reactor listens on to resend discovery and its latest readings after
Home Assistant restarts.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQsfvjYJ2W7KWfxYaK 
- 🔧 Tighten the options schema to the service's start-up limits

The service now refuses these at start-up, so the Supervisor rejects them
when they are saved instead of the app stopping with an error later:

- homeassistant.discovery_interval from 1 to 86400 seconds
- mqtt.broker with no spaces, when it is set
- hostname.pretty, system.shutdown and system.restart not blank

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQAKkStd5ijSre5PTJ 
- ⬆️ Update ghcr.io/home-assistant/aarch64-base-python Docker tag to v3.15 (#72)

Co-authored-by: renovate[bot] <29139614+renovate[bot]@users.noreply.github.com> 
- Update the edge app to redreactor 0.1.9a593 
- Update the edge app to redreactor 0.1.9a592 
- Update the edge app to redreactor 0.1.9a591 
- Update the edge app to redreactor 0.1.9a590 
- Update the edge app to redreactor 0.1.9a589 
- Update the edge app to redreactor 0.1.9a588 
- Use the Samsung INR18650-35E as the battery curve example in the docs (#71) 
- Use the Samsung 35E curve as the docs example, not a default

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNRqPmjstcz34BstSJ4 
- Move the s6 user bundle to user-bundles.d (#70) 
- Default the battery curve to the Samsung INR18650-35E

Read off the 0.2A discharge trace in the lygte-info.dk review, with the
level as the share of the 3.40Ah the cell gave down to 2.8V. Clearing the
curve still gives a straight line between the voltage minimum and maximum.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNRqPmjstcz34BstSJ4 
- Move the s6 user bundle to user-bundles.d

s6-overlay 3.2.3.2 reads the user and user2 bundles from
/etc/s6-overlay/user-bundles.d and warns at boot when they are still
defined under /etc/s6-overlay/s6-rc.d. Register the redreactor service
in user-bundles.d/user/contents.d instead. The bundle's type file comes
from s6-overlay itself, and the service definition stays in s6-rc.d.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQ1Thz4HC53nwNuU6v 
- Add the battery settings to the app configuration (#69) 
- Merge remote-tracking branch 'origin/master' into claude/project-thread-j840eg

# Conflicts:
#	redreactor/translations/en.yaml 
- Give the release pin commit a subject line only (#68) 
- Label every app option in the translations, with TLS capitalised (#67) 
- Add the battery settings to the app configuration

The internal resistance, readings averaged and voltage curve can now be set
in the app options and are passed to Red Reactor at start. The curve is
entered as voltage and level points, as the options can't hold a list of
lists, and converted to [voltage, level] pairs. An empty curve is left out.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNRqPmjstcz34BstSJ4 
- Give the release pin commit a subject line only

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Label every app option in the translations, with TLS capitalised

Home Assistant showed the nested MQTT options by their raw keys, so the
TLS group appeared as lowercase "tls". Add field names and descriptions
for every nested option, and fix the "incase" typo.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNNM8qEbNyLpT78rQzV 
- Update the edge app to redreactor 0.1.9a587

https://github.com/mreditor97/redreactor/releases/tag/0.1.9a587 
- Push the release pin with DISPATCH_TOKEN (#66) 
- Push the release pin with DISPATCH_TOKEN

master only takes changes through a pull request, so the GITHUB_TOKEN
push was rejected. DISPATCH_TOKEN's owner can bypass that rule, and a
push with it starts Deploy, so the edge build no longer needs starting
by hand.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Name app releases with a leading v and add What's changed notes (#65) 
- Add the What's changed notes to app releases

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Name app releases with a leading v

The tag stays X.Y.Z or X.Y.Z-beta.N; the release title gets a leading v,
matching the release-drafter name-template.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Migrate the release-drafter config off deprecated fields (#64) 
- Migrate the release-drafter config off deprecated fields

Category labels move under 'when', and the version-resolver labels move
into 'type: version-resolver' categories, with a fallback category for
the old 'default: patch'. The resolved versions stay the same.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Release stable, beta and edge apps from redreactor releases (#63) 
- Rename the Redreactor workflow to Release

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Use the existing DISPATCH_TOKEN for app releases

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Release a stable app for each redreactor stable release

On a stable redreactor-release dispatch, pin requirements.txt to the new
PyPI version and create the next X.Y.Z app release, which Deploy
publishes to homeassistant-apps.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Combine the Edge and Beta workflows into one

A single Redreactor workflow handles the redreactor-release dispatch for
both channels: it pins requirements-<channel>.txt to the wheel on the
redreactor pre-release, then starts Deploy (edge) or creates the next app
pre-release (beta).

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Release a beta app for each redreactor beta

A new Beta workflow receives the redreactor-beta dispatch, pins
redreactor/requirements-beta.txt to the beta's wheel, and creates the
next X.Y.Z-beta.N app pre-release, which Deploy publishes to
homeassistant-apps-beta. Beta app builds install requirements-beta.txt.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Install the edge alpha from its GitHub pre-release wheel

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Keep the token out of the Edge checkout

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Build the edge app with the latest redreactor alpha

A new Edge workflow receives the redreactor-edge dispatch from the
redreactor master build, pins redreactor/requirements-edge.txt to that
alpha, commits it to master and starts Deploy, which publishes the edge
app to homeassistant-apps-edge as before.

The Dockerfile installs requirements-edge.txt only for edge builds
(versioned by a short commit hash), so stable and beta keep installing
the release in requirements.txt. Renovate leaves the edge pin alone.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQbR7fsAzefajkx6U7 
- Drop the unused SYS_ADMIN capability (#62) 
- Add Home Assistant birth message topic and payload options (#61) 
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
- Add Home Assistant birth message topic and payload options

Lets the add-on set homeassistant.status_topic and status_online, which
Red Reactor listens on to resend discovery and its latest readings after
Home Assistant restarts.

Co-Authored-By: Claude Opus 5.5 <noreply@anthropic.com>
Claude-Session: https://claude.ai/code/session_01NpHVNQsfvjYJ2W7KWfxYaK 
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
