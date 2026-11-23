# OBD Engine Analyser

A single-page web app that connects to an ELM327 OBD-II adapter and helps work out why the check engine light is on.

## Features
- Live data: RPM, coolant temp, short/long-term fuel trims (both banks), load, MAF, MAP, IAT, throttle, timing, O2 sensors, battery voltage, fuel system status
- Stored, pending and permanent fault codes with plain-English descriptions and likely causes
- Freeze frame (conditions when the code set) and readiness monitors
- "Why is the light on?" diagnosis: cross-checks codes against live data (idle vs 2,500 rpm trim pattern, coolant/thermostat, charging voltage, MAF plausibility, O2 switching)
- Clear codes (with confirmation), CSV data log export
- Demo car mode (simulated V6 with a vacuum leak) for trying it without an adapter

## How to use
1. Open `index.html` in Chrome or Edge on a PC/Mac.
2. Bluetooth Classic adapter: pair it in Windows first, then choose the COM port option. USB adapter: plug in and choose the same option (default 38400 baud).
3. Bluetooth LE adapters (e.g. Vgate iCar Pro BLE, OBDLink CX) also work from Chrome on Android.
4. Ignition on / engine running → Connect. Warm the engine, idle 1 minute, then hold ~2,500 rpm for 30 s for the best diagnosis.

Not supported: iPhone/Safari (no Web Serial or Web Bluetooth). Reads the engine ECU only (not transmission/ABS modules).
