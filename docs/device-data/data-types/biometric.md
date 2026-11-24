<!-- omit in toc -->
# Biometric (`biometric`)

{% json-schema
  schema={
    "$ref": "../../../reference/data/models/biometric/biometric.v1.yaml"
  }
/%}

A biometric is a measurement of the body's state at a point in time.

Glucose is biometric data too, but it keeps its Tidepool definitions: use [`cbg`](./cbg.md) and [`smbg`](./smbg.md) for glucose, never this type.
Every other body-state metric uses `biometric`, with `metric` naming what was measured and `amount` carrying the value and units.

## Metrics and units

| `metric` | `amount.units` |
| --- | --- |
| `heartRate`, `restingHeartRate` | `bpm` |
| `heartRateVariability` | `ms` |
| `respiratoryRate` | `breaths/min` |
| `bloodOxygen` | `%` |
| `bodyTemperature` | `celsius` |
| `bloodPressureSystolic`, `bloodPressureDiastolic` | `mmHg` |
| `bodyWeight` | `kg` |
| `steps` | `count` |
| `activeEnergy` | `kcal` |
| `sleepDuration` | `minutes` |
| `stressLevel` | `score` |

## Examples

```json {% title="Example (heart rate)" %}
{
    "type": "biometric",
    "metric": "heartRate",
    "deviceId": "DevId0987654321",
    "deviceTime": "2018-05-14T18:17:08",
    "id": "6e3ea4734056463f84f6be47621d21d7",
    "time": "2018-05-14T08:17:08.453Z",
    "timezoneOffset": 600,
    "uploadId": "SampleUploadId",
    "amount": {
      "value": 72,
      "units": "bpm"
    }
}
```
