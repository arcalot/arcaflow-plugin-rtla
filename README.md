# Realtime Linux Analysis (RTLA) Plugin

This plugin runs the `rtla timerlat hist` tool to collect CPU latency data from the
target system and then generates a structured output of the results.

## Using the plugin

> [!NOTE]
> Unless a `duration` input value is provided, this plugin runs indefinitely until
> explicitly cancelled. When used as a stand-alone plugin outside of an Arcaflow
> workflow, the data collection can be stopped with `Ctrl-c`. When used in an Arcaflow
> workflow, the `stop_if` option should be used to send the `cancel` signal to the
> plugin based on the status of another plugin.

> [!NOTE]
> This plugin requires privilege escalation and a bind mount of the `/sys/kernel/debug`
> directory in order to collect data.

Get a maintained build from
[quay.io/arcalot/arcaflow-plugin-rtla](https://quay.io/repository/arcalot/arcaflow-plugin-rtla),
or build the container locally:
```
podman build . -t arcaflow-plugin-rtla
```

Run with the provided example input:
```
podman run -i --rm --privileged -v /sys/kernel/debug:/sys/kernel/debug arcaflow-plugin-rtla -f - < configs/timerlat_example.yaml
```

# Autogenerated Input/Output Documentation by Arcaflow-Docsgen Below

<!-- Autogenerated documentation by arcaflow-docsgen -->
## Run RTLA Timerlat (`run-timerlat`)

Runs the RTLA Timerlat data collection and then processes the results into a machine-readable format

### Input

<table><tbody>
<tr><th>Type:</th><td><code>scope</code></td><tr><th>Root object:</th><td>TimerlatInputParams</td></tr>
<tr><th>Properties</th><td><details><summary>bucket-size (<code>int</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>histogram bucket size</td></tr><tr><th>Description:</th><td width="500">Set the histogram bucket size (default 1)</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
            </details><details><summary>cpus (<code>list[<code>int</code>]</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>cpus</td></tr><tr><th>Description:</th><td width="500">Run the tracer only on the given cpus</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>list[<code>int</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>List items</summary>
        <table><tbody><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
    </details>
</td></tr></tr>
</tbody></table>
            </details><details><summary>duration (<code>int</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>timerlat duration seconds</td></tr><tr><th>Description:</th><td width="500">Duration of the session in seconds</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
            </details><details><summary>entries (<code>int</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>histogram entries</td></tr><tr><th>Description:</th><td width="500">Set the number of entries of the histogram (default 256)</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td><tr><th>Minimum:</th><td>10</td></tr><tr><th>Maximum:</th><td>9999999</td></tr>
</tr>
</tbody></table>
            </details><details><summary>house-keeping (<code>list[<code>int</code>]</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>house-keeping cpus</td></tr><tr><th>Description:</th><td width="500">Run rtla control threads only on the given cpus</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>list[<code>int</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>List items</summary>
        <table><tbody><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
    </details>
</td></tr></tr>
</tbody></table>
            </details><details><summary>nano (<code>bool</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>display nanoseconds</td></tr><tr><th>Description:</th><td width="500">Display data in nanoseconds</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>bool</code></td></tr>
</tbody></table>
            </details><details><summary>period (<code>int</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>timerlat period</td></tr><tr><th>Description:</th><td width="500">Timerlat period in μs</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
            </details><details><summary>user-threads (<code>bool</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>use user threads</td></tr><tr><th>Description:</th><td width="500">Use rtla user-space threads instead of kernel-space timerlat threads</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>bool</code></td></tr>
</tbody></table>
            </details></td></tr>
<tr><td colspan="2"><details><summary><strong>Objects</strong></summary><details><summary>TimerlatInputParams (<code>object</code>)</summary>
            <table><tbody><tr><th>Type:</th><td><code>object</code></td><tr><th>Properties</th><td><details><summary>bucket-size (<code>int</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>histogram bucket size</td></tr><tr><th>Description:</th><td width="500">Set the histogram bucket size (default 1)</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
        </details><details><summary>cpus (<code>list[<code>int</code>]</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>cpus</td></tr><tr><th>Description:</th><td width="500">Run the tracer only on the given cpus</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>list[<code>int</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>List items</summary>
        <table><tbody><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
    </details>
</td></tr></tr>
</tbody></table>
        </details><details><summary>duration (<code>int</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>timerlat duration seconds</td></tr><tr><th>Description:</th><td width="500">Duration of the session in seconds</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
        </details><details><summary>entries (<code>int</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>histogram entries</td></tr><tr><th>Description:</th><td width="500">Set the number of entries of the histogram (default 256)</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td><tr><th>Minimum:</th><td>10</td></tr><tr><th>Maximum:</th><td>9999999</td></tr>
</tr>
</tbody></table>
        </details><details><summary>house-keeping (<code>list[<code>int</code>]</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>house-keeping cpus</td></tr><tr><th>Description:</th><td width="500">Run rtla control threads only on the given cpus</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>list[<code>int</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>List items</summary>
        <table><tbody><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
    </details>
</td></tr></tr>
</tbody></table>
        </details><details><summary>nano (<code>bool</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>display nanoseconds</td></tr><tr><th>Description:</th><td width="500">Display data in nanoseconds</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>bool</code></td></tr>
</tbody></table>
        </details><details><summary>period (<code>int</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>timerlat period</td></tr><tr><th>Description:</th><td width="500">Timerlat period in μs</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
        </details><details><summary>user-threads (<code>bool</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>use user threads</td></tr><tr><th>Description:</th><td width="500">Use rtla user-space threads instead of kernel-space timerlat threads</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>bool</code></td></tr>
</tbody></table>
        </details></td></tr>
</tr>
</tbody></table>
        </details></details></td></tr></tr>

</tbody></table>

### Outputs


#### error

<table><tbody>
<tr><th>Type:</th><td><code>scope</code></td><tr><th>Root object:</th><td>ErrorOutput</td></tr>
<tr><th>Properties</th><td><details><summary>error (<code>string</code>)</summary>
                <table><tbody><tr><th>Required:</th><td>Yes</td></tr><tr><th>Type:</th><td><code>string</code></td></tr>
</tbody></table>
            </details></td></tr>
<tr><td colspan="2"><details><summary><strong>Objects</strong></summary><details><summary>ErrorOutput (<code>object</code>)</summary>
            <table><tbody><tr><th>Type:</th><td><code>object</code></td><tr><th>Properties</th><td><details><summary>error (<code>string</code>)</summary>
        <table><tbody><tr><th>Required:</th><td>Yes</td></tr><tr><th>Type:</th><td><code>string</code></td></tr>
</tbody></table>
        </details></td></tr>
</tr>
</tbody></table>
        </details></details></td></tr></tr>

</tbody></table>

#### success

<table><tbody>
<tr><th>Type:</th><td><code>scope</code></td><tr><th>Root object:</th><td>TimerlatOutput</td></tr>
<tr><th>Properties</th><td><details><summary>latency_hist (<code>list[<code>map[<code>string</code>,<code>int</code>]</code>]</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>latency histogram</td></tr><tr><th>Description:</th><td width="500">Histogram of latencies</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>list[<code>map[<code>string</code>,<code>int</code>]</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>List items</summary>
        <table><tbody><tr><th>Type:</th><td><code>map[<code>string</code>,<code>int</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>Key type</summary>
        <table><tbody><tr><th>Type:</th><td><code>string</code></td></tr>
</tbody></table>
    </details>
</td></tr>
<tr><td colspan="2">
    <details>
        <summary>Value type</summary>
        <table><tbody><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
    </details>
</td></tr>
</tr>
</tbody></table>
    </details>
</td></tr></tr>
</tbody></table>
            </details><details><summary>stats_per_col (<code>list[<code>map[<code>string</code>,<code>any</code>]</code>]</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>statistics per column</td></tr><tr><th>Description:</th><td width="500">Latency statistics per captured column</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>list[<code>map[<code>string</code>,<code>any</code>]</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>List items</summary>
        <table><tbody><tr><th>Type:</th><td><code>map[<code>string</code>,<code>any</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>Key type</summary>
        <table><tbody><tr><th>Type:</th><td><code>string</code></td></tr>
</tbody></table>
    </details>
</td></tr>
<tr><td colspan="2">
    <details>
        <summary>Value type</summary>
        <table><tbody><tr><th>Type:</th><td><code>any</code></td></tr>
</tbody></table>
    </details>
</td></tr>
</tr>
</tbody></table>
    </details>
</td></tr></tr>
</tbody></table>
            </details><details><summary>time_unit (<code>string</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>latency unit</td></tr><tr><th>Description:</th><td width="500">Time unit for latency values</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>string</code></td></tr>
</tbody></table>
            </details><details><summary>total_irq_latency (<code>reference[LatencyStats]</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>total irq latency</td></tr><tr><th>Description:</th><td width="500">Total IRQ latency</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>reference[LatencyStats]</code></td><tr><th>Referenced object:</th><td>LatencyStats</td></tr></tr>
</tbody></table>
            </details><details><summary>total_thr_latency (<code>reference[LatencyStats]</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>total thread latency</td></tr><tr><th>Description:</th><td width="500">Total thread latency</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>reference[LatencyStats]</code></td><tr><th>Referenced object:</th><td>LatencyStats</td></tr></tr>
</tbody></table>
            </details><details><summary>total_usr_latency (<code>reference[LatencyStats]</code>)</summary>
                <table><tbody><tr><th>Name:</th><td>total usr latency</td></tr><tr><th>Description:</th><td width="500">Total user latency</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>reference[LatencyStats]</code></td><tr><th>Referenced object:</th><td>LatencyStats</td></tr></tr>
</tbody></table>
            </details></td></tr>
<tr><td colspan="2"><details><summary><strong>Objects</strong></summary><details><summary>LatencyStats (<code>object</code>)</summary>
            <table><tbody><tr><th>Type:</th><td><code>object</code></td><tr><th>Properties</th><td><details><summary>avg (<code>int</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>average latency</td></tr><tr><th>Description:</th><td width="500">Average latency value</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
        </details><details><summary>count (<code>int</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>number of measurements</td></tr><tr><th>Description:</th><td width="500">Number of latency measurements</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
        </details><details><summary>max (<code>int</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>maximum latency</td></tr><tr><th>Description:</th><td width="500">Maximum latency value</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
        </details><details><summary>min (<code>int</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>minimum latency</td></tr><tr><th>Description:</th><td width="500">Minimum latency value</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
        </details></td></tr>
</tr>
</tbody></table>
        </details><details><summary>TimerlatOutput (<code>object</code>)</summary>
            <table><tbody><tr><th>Type:</th><td><code>object</code></td><tr><th>Properties</th><td><details><summary>latency_hist (<code>list[<code>map[<code>string</code>,<code>int</code>]</code>]</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>latency histogram</td></tr><tr><th>Description:</th><td width="500">Histogram of latencies</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>list[<code>map[<code>string</code>,<code>int</code>]</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>List items</summary>
        <table><tbody><tr><th>Type:</th><td><code>map[<code>string</code>,<code>int</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>Key type</summary>
        <table><tbody><tr><th>Type:</th><td><code>string</code></td></tr>
</tbody></table>
    </details>
</td></tr>
<tr><td colspan="2">
    <details>
        <summary>Value type</summary>
        <table><tbody><tr><th>Type:</th><td><code>int</code></td>
</tr>
</tbody></table>
    </details>
</td></tr>
</tr>
</tbody></table>
    </details>
</td></tr></tr>
</tbody></table>
        </details><details><summary>stats_per_col (<code>list[<code>map[<code>string</code>,<code>any</code>]</code>]</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>statistics per column</td></tr><tr><th>Description:</th><td width="500">Latency statistics per captured column</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>list[<code>map[<code>string</code>,<code>any</code>]</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>List items</summary>
        <table><tbody><tr><th>Type:</th><td><code>map[<code>string</code>,<code>any</code>]</code></td><tr><td colspan="2">
    <details>
        <summary>Key type</summary>
        <table><tbody><tr><th>Type:</th><td><code>string</code></td></tr>
</tbody></table>
    </details>
</td></tr>
<tr><td colspan="2">
    <details>
        <summary>Value type</summary>
        <table><tbody><tr><th>Type:</th><td><code>any</code></td></tr>
</tbody></table>
    </details>
</td></tr>
</tr>
</tbody></table>
    </details>
</td></tr></tr>
</tbody></table>
        </details><details><summary>time_unit (<code>string</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>latency unit</td></tr><tr><th>Description:</th><td width="500">Time unit for latency values</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>string</code></td></tr>
</tbody></table>
        </details><details><summary>total_irq_latency (<code>reference[LatencyStats]</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>total irq latency</td></tr><tr><th>Description:</th><td width="500">Total IRQ latency</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>reference[LatencyStats]</code></td><tr><th>Referenced object:</th><td>LatencyStats</td></tr></tr>
</tbody></table>
        </details><details><summary>total_thr_latency (<code>reference[LatencyStats]</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>total thread latency</td></tr><tr><th>Description:</th><td width="500">Total thread latency</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>reference[LatencyStats]</code></td><tr><th>Referenced object:</th><td>LatencyStats</td></tr></tr>
</tbody></table>
        </details><details><summary>total_usr_latency (<code>reference[LatencyStats]</code>)</summary>
        <table><tbody><tr><th>Name:</th><td>total usr latency</td></tr><tr><th>Description:</th><td width="500">Total user latency</td></tr><tr><th>Required:</th><td>No</td></tr><tr><th>Type:</th><td><code>reference[LatencyStats]</code></td><tr><th>Referenced object:</th><td>LatencyStats</td></tr></tr>
</tbody></table>
        </details></td></tr>
</tr>
</tbody></table>
        </details></details></td></tr></tr>

</tbody></table>
<!-- End of autogenerated documentation -->
