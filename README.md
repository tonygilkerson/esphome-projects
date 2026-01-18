# esphome-projects

My ESPHome Projects

## Next

Plan: Send typed text from HA to ESPHome
TL;DR — Preferred approach: use a Home Assistant input_text helper + an ESPHome api action that accepts a string and publishes it to a text_sensor (no extra broker, low latency, secure via api.encryption).

Steps
* Add an api.actions handler, a globals string, and a text_sensor to cover-controller.yaml so the device can receive and store text.
* Create an input_text helper in Home Assistant (input_text.garage_message) for user input.
* Add an HA automation that triggers on input_text.garage_message change and calls the generated esphome.<node>_<action> service to send the text.