## pxc logs node

Print Portworx logs for specified nodes

### Synopsis

Print Portworx logs for specified nodes

```
pxc logs node [NAME] [flags]
```

### Examples

```

  # Return Portworx logs from all nodes
  pxc logs node --all-nodes

  # Return Portworx logs from  node abc
  pxc logs node abc

  # Begin streaming the Portworx logs from  node abc
  pxc logs node -f  abc

  # Apply filters to only the most recent 20 log lines and display the matched lines
  pxc logs node --tail=20 abc

  # Display all log lines that has either error or warning on node abc
  pxc logs node abc --filter "error,warning"

  # Show all Portworx logs from node abc written in the last hour
  pxc logs node --since=1h node
```

### Options

```
      --all-nodes              If specified, logs from all nodes will be displayed
      --filter string          Comma seperated list of strings to search for. Log line will be printed if any one of the strings match. Note that if --tail is specified the filter is applied on only those many lines.
  -f, --follow                 Specify if the logs should be streamed.
  -h, --help                   help for node
      --ignore-errors          If watching / following Portworx logs, allow for any errors that occur to be non-fatal
      --limit-bytes int        Maximum bytes of logs to return. Defaults to no limit.
      --max-log-requests int   Specify maximum number of concurrent logs to follow. Defaults to 5. (default 5)
  -p, --previous               If true, print the logs for the previous instance of the container in a pod if it exists.
  -n, --px-namespace string    Kubernetes namespace in which Portworx is installed (default "kube-system")
      --show-pod-info          Include pod info on each line in the log output
      --since duration         Only return logs newer than a relative duration like 5s, 2m, or 3h. Defaults to all logs. Only one of since-time / since may be used.
      --since-time string      Only return logs after a specific date (RFC3339). Defaults to all logs. Only one of since-time / since may be used.
      --tail int               Lines of recent log file to work on. Defaults to -1, showing all log lines. All filters will be applied on top of these lines (default -1)
      --timestamps             Include timestamps on each line in the log output
```

### Options inherited from parent commands

```
      --config string    Config file (default is $HOME/.pxc/config.yml)
      --context string   Force context name for the command
      --v int32          [0-4] Log level verbosity
```

### SEE ALSO

* [pxc logs](pxc_logs.md)	 - Print Portworx logs

###### Auto generated by spf13/cobra on 6-Nov-2019