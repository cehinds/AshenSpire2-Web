# Procedural audio provenance

All files in `Unity/Assets/Resources/Audio/` are original procedural synthesis created for this project. `Tools/generate_audio.py` uses only Python standard-library modules (`wave`, `math`, `random`, `struct`, and `hashlib`). It downloads, embeds, or samples no third-party audio or source recordings.

## Format and reproduction

- PCM WAV, mono, signed 16-bit, 44,100 Hz.
- The eight short effects are smoothly enveloped and remain below a measured peak of 0.65.
- `ambient.wav` is a 10-second softly voiced tonal bed intended to loop; its tones and amplitude modulation share an exact 10-second period.
- Synthesis is reproducible with fixed seed `0xA5E215` for the seeded noise used by the step and attack effects.
- Run `python Tools/generate_audio.py` to create the files when they are absent. Run `python Tools/generate_audio.py --force` to replace the generated files after changing the synthesis source.
- The generator validates WAV encoding, sample rate, duration, peak, and the ambient loop join. It prints each file's SHA-256.

## Generated assets

| Key / file | Intended use | Duration | Peak | SHA-256 |
|---|---|---:|---:|---|
| `click.wav` | Short, soft UI confirmation | 0.100 s | 0.17697 | `fd2d258c6004d7ce9aefda864141fb4336f416e4a1a8cdf202e95e11310fd27a` |
| `step.wav` | Muted footstep | 0.220 s | 0.19138 | `535963040e30faad54726de4c083e91afad7f2a0ad3df8394eb0bb7d16be48d8` |
| `attack.wav` | Soft weapon sweep and impact | 0.340 s | 0.27222 | `39a53a0a82f9ddaca0a732d826816d6a34521e2b20ef25f7ab8c1a30af45a951` |
| `spell.wav` | Rising, gentle spell tone | 0.720 s | 0.16492 | `70c14f841fa71ec7dc148e271956bc22dfdadfe37b6cebef7bbbde113d60d9d5` |
| `guard.wav` | Damped low guard impact with a short ring | 0.340 s | 0.21201 | `53412a595b6bb1c0f903c2d3e328bdcba766b3faa51570a313675d693132fa01` |
| `heal.wav` | Gentle ascending healing notes | 0.880 s | 0.15662 | `5ea3e24e3f54c429a2d1820a35f0c315124ae2f80a8cd9e286d368c1b0af1ad6` |
| `reward.wav` | Warm ascending reward chime | 1.340 s | 0.26700 | `67a6c527098bc3cd0d53b9365d5387efa2bdf496c72a245fb1751e628414cd5f` |
| `defeat.wav` | Quiet descending defeat chord | 1.480 s | 0.21011 | `230332780fc2b382ba6d60fd99b7a54dfdbf0eebabade66e5db72f843aa00dee` |
| `ambient.wav` | Low, loopable fantasy ambience | 10.000 s | 0.11386 | `b7c4d3b7e8949ae4f067f3a788344366d22a6c2a1ff274425dea3a6a1e82b229` |

These values describe the checked-in generated output. Any synthesis change should regenerate the hashes and refresh this table.
