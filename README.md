# Formal Verification of HTTPS/TLS 1.3 with UPPAAL

University project (FST, Université Tunis El Manar). Simplified timed-automata model of the TLS 1.3 handshake, with abstract models of two attacks: POODLE (protocol downgrade) and Heartbleed (memory leak).

## What is modelled

- Templates: Client, Server, Attacker_POODLE, Attacker_Heartbleed
- 8 CTL queries (deadlock freedom, session reachability, attack reachability, safety)
- UPPAAL-SMC probability analysis before and after the countermeasures (see report)
- Countermeasures: minimum protocol version (POODLE), payload size check (Heartbleed)

## Files

- `Rapport-TLS-UPPAAL.pdf`: full report (French)
- original model: version before the countermeasures (the attacks succeed)
- `model_with_countermeasures.xml`: model with the two countermeasures added (guard `version_negotiated >= 2`, check `heartbeat_length <= payload_size`)

## Limits

- Abstract model: no real cryptography, simplified handshake
- POODLE and Heartbleed target older SSL/TLS versions and OpenSSL 1.0.1; here they are modelled abstractly on top of the handshake, not as attacks on TLS 1.3 itself
- No real man-in-the-middle scenario

## Authors

Oussama Hkimi, Baraa Benarfi, Farah Benarbi, Rym Jlidi, Amani Arouri
