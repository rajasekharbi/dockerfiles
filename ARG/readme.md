ARG
===
ARG can be the first instruction in an exceptional case i.e to supply the version to the base image.. after FROM instruction we can't access ARG variable

ARG vs ENV
==========
1. ENV is used to supply the key value pairs for the container/runtime
2. ARG is used to supply the values to variables at build time.
3. ARG can't be accessible inside container.