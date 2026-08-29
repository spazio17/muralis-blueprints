# Muralis blueprints

Home Assistant automation blueprints for panels running [Muralis](https://muralis.spazio17.org),
an Android kiosk launcher for a wall-mounted tablet.

Muralis publishes its controls and sensors over MQTT discovery, so a panel arrives in Home
Assistant as a device with buttons, switches, a battery level and the rest. These blueprints are
the two things people end up wanting from such a panel, written once so nobody has to work them
out again.

| Blueprint | What it does |
| --- | --- |
| [`screen-presence.yaml`](screen-presence.yaml) | Wakes the panel when someone is in the room and blanks it once the room has been empty for a while. |
| [`battery-band.yaml`](battery-band.yaml) | Charges the tablet only between two thresholds, instead of leaving it at 100 percent forever. |

## Installing one

In Home Assistant, go to **Settings → Automations & scenes → Blueprints**, choose **Import
blueprint**, and paste the URL of the file above. Or use the buttons on
[muralis.spazio17.org](https://muralis.spazio17.org#recipes), which open the same dialog with the
URL already filled in.

Home Assistant imports blueprints from GitHub, GitHub gists and the Home Assistant forums, which
is why these live in a repository rather than being served from the website.

## Picking the entities

Every blueprint asks you to pick entities rather than type entity ids, and that is deliberate. A
panel set up before the app was renamed carries ids beginning `kiosk_`, a newer one `muralis_`,
and the same tablet can carry both if it has been through the rename. Picking from the list means
you never have to know which.

## Licence

These blueprints are released under the MIT licence, so you can copy them, change them and use
the result however you like. The Muralis app itself is not open source; see its
[terms](https://muralis.spazio17.org/terms/).
