### How do I Capture Performence Counters?



## To Create a Counter Set
```
logman create counter EL-BASELINE -f bincirc -max 500 -si 2 -o "C:\perflogs\EL-BASELINE" -cf "perf-baseline.config"
```

## To Start a Counter Set
```
logman start EL-BASELINE
```
## To Stop a Counter Set
```
logman stop EL-BASELINE
```
## To Delete a Counter Set
```
logman delete EL-BASELINE
```


## TODO automate



## References
https://blogs.technet.microsoft.com/askperf/2008/05/13/two-minute-drill-logman-exe/
