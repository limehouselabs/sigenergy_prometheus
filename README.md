# Prometheus exporter config for Sigenergy solar/battery systems

This repo contains a config for the Prometheus [modbus\_exporter](https://github.com/RichiH/modbus_exporter) which allows metrics to be scraped from Sigenergy solar PV/battery systems over Modbus-TCP.

The Sigenergy system needs the "Modbus TCP Server Enable" option enabled by the installer - it can't be enabled in the user-facing app.

These systems expose multiple addresses on the same Modbus port:

* the "plant" on address 247, which should be scraped with the `sigenergy_plant` module
* the "hybrid inverter" on address 1 (by default, and presumably there can be more), which is scraped with the `sigenergy_inverter` module.

The config exposes most of the more interesting metrics but it's not comprehensive.
