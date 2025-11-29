CMD ENTRYPOINT
==========
1. CMD instruction can be overriden.
2. ENTRYPOINT can't be overriden, if we try it will go and append that leads to failure
3. CMD can be used to supply the default args to ENTRYPOINT. You can always override the default args at run time
