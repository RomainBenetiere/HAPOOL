# HAPOOL

This repository contains Home Assistant configuration for managing a swimming pool. It uses YAML packages under `packages/raspipool` and custom components in `custom_components`.

## Variables

Below is a list of input helpers defined in the `packages/` folder. The table notes the entity ID and the file where it is declared.

| Entity ID | Description | File |
|-----------|-------------|------|
| `input_number.e_fc_adjust` | Adjustment factor for estimated free chlorine | `packages/raspipool/fc.yaml` |
| `input_number.fc_target` | Target free chlorine level (ppm) | `packages/raspipool/fc.yaml` |
| `input_number.ph_target` | Target pH value | `packages/raspipool/ph.yaml` |
| `input_number.capacity` | Pool capacity in m³ | `packages/raspipool/settings.yaml` |
| `input_number.quality` | Pool water quality level | `packages/raspipool/settings.yaml` |
| `input_number.turbo` | Percentage of high speed pump runtime | `packages/raspipool/settings.yaml` |
| `input_number.out_of_order` | Days before pump cycle resumes | `packages/raspipool/pump.yaml` |
| `input_number.cycle` | Pump cycle duration (minutes) | `packages/raspipool/pump.yaml` |
| `input_number.second_cycle` | Percentage of a second daily cycle | `packages/raspipool/pump.yaml` |
| `input_number.pump_on_for` | Manual pump runtime (hours) | `packages/raspipool/pump.yaml` |
| `input_number.notify_cycles` | Number of filtration cycles before alert | `packages/raspipool/flow.yaml` |
| `input_number.bleach_tank` | Remaining volume of bleach | `packages/raspipool/bleach.yaml` |
| `input_number.bleach_concentration` | Concentration of bleach (%) | `packages/raspipool/bleach.yaml` |
| `input_number.bleach_speed` | Bleach pump speed (ml/min) | `packages/raspipool/bleach.yaml` |
| `input_number.notify_bleach_high` | Threshold for high bleach usage | `packages/raspipool/bleach.yaml` |
| `input_number.notify_bleach_tank` | Alert level for bleach tank volume | `packages/raspipool/bleach.yaml` |
| `input_number.bleach_inject` | Amount of bleach to inject (ml) | `packages/raspipool/bleach.yaml` |
| `input_number.muriatic_tank` | Remaining volume of muriatic acid | `packages/raspipool/muriatic.yaml` |
| `input_number.muriatic_concentration` | Concentration of muriatic acid (%) | `packages/raspipool/muriatic.yaml` |
| `input_number.muriatic_speed` | Acid pump speed (ml/min) | `packages/raspipool/muriatic.yaml` |
| `input_number.notify_muriatic_high` | Threshold for high acid usage | `packages/raspipool/muriatic.yaml` |
| `input_number.notify_muriatic_tank` | Alert level for acid tank volume | `packages/raspipool/muriatic.yaml` |
| `input_number.muriatic_inject` | Amount of acid to inject (ml) | `packages/raspipool/muriatic.yaml` |
| `input_boolean.notify_seasson` | Enable seasonal notifications | `packages/raspipool/notifications.yaml` |
| `input_boolean.turbo` | Enable dual-speed pump | `packages/raspipool/settings.yaml` |
| `input_boolean.factory_started` | Marks first-time configuration | `packages/raspipool/settings.yaml` |
| `input_boolean.lock_bleach` | Block bleach injection | `packages/raspipool/switches.yaml` |
| `input_boolean.lock_muriatic` | Block acid injection | `packages/raspipool/switches.yaml` |
| `input_datetime.cycle_start` | Start time of filtration cycle | `packages/raspipool/settings.yaml` |
| `input_datetime.recirculation` | Recirculation duration | `packages/raspipool/settings.yaml` |
| `input_datetime.cummulated_flow_start` | Date when flow accumulation began | `packages/raspipool/flow.yaml` |
| `counter.minutes_fonctionnement` | Turbo pump runtime counter | `packages/raspipool/settings.yaml` |

These helpers are referenced in the automations within the same YAML files to manage pumps, chemical dosing, and notifications.

