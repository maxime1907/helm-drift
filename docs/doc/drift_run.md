## drift run

Identifies drifts from a selected chart or release.

### Synopsis

It lists all configuration drifts that are part of the specified chart or release, if one exists.

```
drift run [RELEASE] [CHART] [flags]
```

### Examples

```
  helm drift run prometheus-standalone path/to/chart/prometheus-standalone -f ~/path/to/override-config.yaml
  helm drift run prometheus-standalone --from-release
```

### Options

```
      --consider-hooks                      when this is enabled, the flag 'ignore-hooks' holds no value
      --custom-diff KUBECTL_EXTERNAL_DIFF   custom diff command to use instead of default, the command passed here would be set under KUBECTL_EXTERNAL_DIFF.More information can be found here https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#diff
  -d, --disable-error-on-drift              enabling this would disable exiting with error if drifts were identified (works only when --summary is enabled)
      --from-release                        enable the flag to identify drifts from a release instead (disabled by default, works with command 'run' not with 'all')
  -h, --help                                help for run
      --ignore-hooks strings                list of hooks to ignore while identifying the drifts (default [hook-succeeded,hook-failed])
  -j, --json                                enable the flag to render drifts in json format (disabled by default)
      --kind strings                        kubernetes resource names to limit the drift identification (--kind takes higher precedence over --name)
      --name string                         name of the kubernetes resource to limit the drift identification
      --regex string                        regex used to split helm template rendered (default "---\\n# Source:\\s.*.")
      --report                              when enabled the summary report would be rendered on to a file (this works only if --yaml or --json is enabled along with summary)
      --skip strings                        kubernetes resource names to skip the drift identification (ex: --skip Deployments)
      --skip-cleaning                       enable the flag to skip cleaning the manifests rendered on to disk
      --skip-validation                     enable the flag if prerequisite validation needs to be skipped
      --summary                             if enabled, prints a quick summary in table format without printing actual drifts
      --temp-path string                    path on disk where the helm templates would be rendered on to (the same would be used be used by 'kubectl diff') (default "/Users/nikhil.bhat/.helm-drift/templates")
  -y, --yaml                                enable the flag to render drifts in yaml format (disabled by default)
```

### Options inherited from parent commands

```
  -l, --log-level string         log level for the plugin helm drift (defaults to info) (default "info")
      --no-color                 enabling this would render summary with no color
      --set stringArray          set values on the command line (can specify multiple or separate values with commas: key1=val1,key2=val2)
      --set-file stringArray     set values from respective files specified via the command line (can specify multiple or separate values with commas: key1=path1,key2=path2)
      --set-string stringArray   set STRING values on the command line (can specify multiple or separate values with commas: key1=val1,key2=val2)
      --skip-tests               setting this would set '--skip-tests' for helm template command while generating templates
  -f, --values ValueFiles        specify values in a YAML file (can specify multiple) (default [])
```

### SEE ALSO

* [drift](drift.md)	 - A utility that helps in identifying drifts in infrastructure

###### Auto generated by spf13/cobra on 25-Jul-2023
