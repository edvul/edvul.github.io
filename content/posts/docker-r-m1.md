---
title: "Docker R M1"
date: 2021-06-13T14:13:08-07:00
---

# Docker, R, M1, etc.

My goal is to build a minimal docker image on which I can auto-grade student homework.  My previous arrangement used a very shoddy sandbox, and I wanted the security and reliability of a pre-built image.

My requirements for this image are that it can run a reasonably modern version of R, including some tidyverse packages, lme4, rstan, and a few other libraries.  

One complication is that I am using an M1 macbook, and I will eventually want this image to run on an x86 server.  

## Step -1: mysterious failure.

I tried the following basic Dockerfile, following the instructions [here](https://github.com/r-hub/r-minimal):

Taken from the [examples](https://github.com/r-hub/r-minimal/blob/master/examples/dplyr/Dockerfile): 
```
FROM rhub/r-minimal

RUN installr -d dplyr
```

This can launch the initial image, and installs most of the system dependencies without any fuss, but fails after downloading the last package.

{{< expand >}}
```
#6 16.17 Installing 18 packages: dplyr, ellipsis, generics, glue, lifecycle, magrittr, R6, rlang, tibble, tidyselect, vctrs, pillar, fansi, pkgconfig, cli, crayon, utf8, purrr

[...lot of successful downloading of the aforementioned packages...]

#6 26.64 INSTALL: applet not found
#6 26.64 Error in system2(cmd0, args, env = env, stdout = outfile, stderr = outfile,  :
#6 26.64   (converted from warning) error in running command
#6 26.64 Calls: <Anonymous> ... with_rprofile_user -> with_envvar -> force -> force -> i.p -> system2
#6 26.65 Execution halted
#6 26.68 Failed to install dplyr
```
{{< /expand >}}

### replication with lme4

Same failure arises when trying to install lme4, or babynames package, or  just rlang, or praise as shown [here](https://github.com/r-hub/r-minimal).



## Next steps

- try building on x86 machine.



