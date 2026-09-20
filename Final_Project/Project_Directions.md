# Optional project direction modules

Choose an application that interests you and fits the [common project requirements](Final_Project_Brief.md).
These modules suggest useful end-actions and questions to investigate. They are self-paced idea
resources, not prescribed builds. There is no quiz, proposal, or separate module submission.
You may combine directions or propose another application through your final implementation.

Every direction begins with sensor input, a new on-device model, and a justified gate. The
sequences below describe the action after that gate. Model scores alone are not an end-action.
Links provide implementation references; they do not certify a particular model, library, or
complete project on the course hardware. Check compatibility with the pinned course toolchain.

## Physical actuation

A detected condition could position a small indicator, open a model-scale mechanism, or change
a low-voltage device state. Architecture: accepted event → bounded actuator command → physical
state. Extra components may include an actuator, driver, and suitable supply; they are not
assumed to be in the course kit. A GPIO signal is not an actuator power supply.

Decide the allowed positions/states, actuation duration, repeat behavior, and default state.
Consider uncertain input, reset during motion, and blocked or disconnected mechanisms. Record
command-to-motion delay and the physical outcome, including a suppressed action. Keep the
application small enough that testing the model and gate remains central.

Reference: [Seeed pin multiplexing and interfaces](https://wiki.seeedstudio.com/xiao_esp32s3_pin_multiplexing/).

## Remote processing

An accepted local event could request image interpretation, a bounded analysis, or an external
processing job. Architecture: event → network request → processing result → validated application
action. A language or vision-language model is one possible service, not a requirement.
A local computer can host processing while the XIAO still performs the required first inference.

Decide which data must leave the device, what the response means, and how to validate it. Bound
payloads, waits, retries, and paid-service usage. Give events identities so retries do not cause
unintended duplicate actions. Test disconnection, timeout, and malformed output. Measure both
local gate delay and remote processing delay. Do not claim live-service success from a mock run.

References: [Espressif network API](https://docs.espressif.com/projects/arduino-esp32/en/latest/api/network.html)
and [Wi-Fi API](https://docs.espressif.com/projects/arduino-esp32/en/latest/api/wifi.html).

## Mobile interaction

A local event could change a phone application's state, add a useful event to its history, or
request the user's attention. Architecture: event → message/endpoint → phone interface →
acknowledgement. A phone-accessible web interface can keep the scope smaller than a native app.
You need a phone/browser or app and a tested communication path.

Decide what the user sees, what counts as receipt versus completed action, and how to distinguish
new events from stale state. Test reconnection, duplicates, and an unavailable interface. If using
system notifications, investigate platform support and user permissions before committing to that
scope. Show a meaningful state change, not only the arriving score.

References: [MDN Notifications API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API)
and [Espressif Wi-Fi API](https://docs.espressif.com/projects/arduino-esp32/en/latest/api/wifi.html).

## Computer interaction

A recognized condition could control a presentation, a media application, or a bounded desktop
workflow. Architecture: event → computer-side receiver → allowed application command. A computer
receiver can translate serial or network messages; the model itself still runs on the XIAO.
Use an application with a documented control interface rather than relying on arbitrary keyboard
focus. Direct USB/Bluetooth integration is optional and requires its own compatibility check.

Choose a small command set and define how the intended application receives it. Consider repeated
input, a closed target application, or lost connection. Measure event-to-command delay and show
that a non-target condition leaves the application unchanged. Prevent a held input from advancing
an entire presentation.

Reference: [Espressif network API](https://docs.espressif.com/projects/arduino-esp32/en/latest/api/network.html).
Consult the chosen application's official interface documentation for its command contract.

## Event-triggered recording

A model could detect a relevant event and preserve a short sensor recording or image sequence
for later inspection. Architecture: event → bounded capture → saved artifact → review. Storage
may be on the device or an attached computer. Decide storage capacity and any additional media
requirements before choosing a capture format.

Define what the recording is useful for, its duration, timestamp, and event identity. Decide
whether retriggers extend, replace, or start a new capture. Test full/unavailable storage and
capture interruption. Measure the delay to capture and verify the saved artifact can be opened.
A file containing only model scores does not establish a useful recording application by itself.
Document permission and retention for any recorded people or private surroundings.

Reference: [Seeed XIAO ESP32-S3 Sense hardware overview](https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/).
Consult the storage library matching the chosen hardware and pinned core before implementation.

## Adaptive sensing

A low-cost detector could enable a higher sampling rate or a more detailed second analysis when
needed. Architecture: local gate → sensing/analysis mode change → useful observation → return
to idle. The second stage may be local or remote. Identify a concrete benefit such as capturing
a transient event at higher detail.

Decide what changes, how long the active mode lasts, and how the system returns to idle. Check
that switching modes does not interrupt the required inference path or exhaust memory. Compare
response time and measured resource use across gate settings. If measuring energy is unavailable,
report active time or invocation counts accurately rather than inventing power savings. Show that
the selected mode produces useful output beyond a status flag.

Reference: [Espressif network API](https://docs.espressif.com/projects/arduino-esp32/en/latest/api/network.html)
for a remote second stage. Reuse A4's distinction between measurements and tool estimates.

## Local feedback and guidance

A classified condition could select an actionable light, sound, or vibration pattern. Architecture:
event → feedback state → user response or acknowledgement. An existing-kit LED interaction can
provide a modest scope if it communicates a useful application state and has meaningful gate and
recovery behavior. Sound and vibration may require additional components.

Define the message the user should understand and what they should do next. Consider persistence,
acknowledgement, ambiguous input, and access without relying on color alone. Measure response delay
and test whether repeated detections behave as intended. Distinguish a designed feedback state
from simply showing whichever class currently has the largest score.

Reference: [Seeed pin multiplexing and interfaces](https://wiki.seeedstudio.com/xiao_esp32s3_pin_multiplexing/).

## Device-to-device coordination

One device could detect an event and ask a second device to change a bounded state. Architecture:
local gate → event message → receiver action → acknowledgement. Additional hardware and a tested
communication path are needed; the course does not assume a second board in every kit.

Decide event identity, message content, timeout, and receiver behavior after restart. Distinguish
message transmission, receipt, and completed action. Test dropped communication and duplicate
messages, and show that a retry cannot repeat an action unexpectedly. Limit the scope to one
receiving action before considering a larger network.

References: [Espressif Wi-Fi API](https://docs.espressif.com/projects/arduino-esp32/en/latest/api/wifi.html)
and [network API](https://docs.espressif.com/projects/arduino-esp32/en/latest/api/network.html).
