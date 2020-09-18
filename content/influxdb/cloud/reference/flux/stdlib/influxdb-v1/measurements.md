---
title: v1.measurements() function
description: The v1.measurements() function returns a list of measurements in a specific bucket.
aliases:
  - /influxdb/cloud/reference/flux/functions/influxdb-v1/measurements/
menu:
  influxdb_cloud_ref:
    name: v1.measurements
    parent: InfluxDB v1
weight: 301
influxdb/cloud/tags: [measurements]
related:
  - /influxdb/cloud/query-data/flux/explore-schema/
  - /{{< latest "influxdb" "v1" >}}/query_language/schema_exploration#show-measurements, SHOW MEASUREMENTS in InfluxQL
---

The `v1.measurements()` function returns a list of measurements in a specific bucket.
The return value is always a single table with a single column, `_value`.

```js
import "influxdata/influxdb/v1"

v1.measurements(bucket: "example-bucket")
```

## Parameters

### bucket
The bucket from which to list measurements.

_**Data type:** String_

## Function definition
```js
package v1

measurements = (bucket) =>
  tagValues(bucket: bucket, tag: "_measurement")
```

_**Used functions:**
[v1.tagValues()](/influxdb/cloud/reference/flux/stdlib/influxdb-v1/tagvalues)_