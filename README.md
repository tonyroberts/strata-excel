[![GitHub version](https://badge.fury.io/gh/conventional-changelog%2Fstandard-version.svg)](https://ci.appveyor.com/project/TonyRoberts/strata-excel)
[![Build status](https://ci.appveyor.com/api/projects/status/k8dul9mkbyjura1a?svg=true)](https://ci.appveyor.com/project/TonyRoberts/strata-excel)

# Strata-Excel

Strata-Excel provides Excel bindings to OpenGamma's Strata open source analytics and market risk library.

Strata can be found at https://github.com/OpenGamma/Strata.

## Using Strata-Excel

Strata-Excel uses Jinx, the Excel Java Add-in.

Jinx can be obtained from https://exceljava.com.

Once Jinx is installed the Strata-Excel JAR file must be added to the jinx.ini config file, along with the OpenGamma Strata library and dependencies.

```ini
[JAVA]
classpath =
  <path of strata-excel JAR file>
  <strata and dependencies>/*.jar
```

## Building Strata-Excel

The source code can be cloned using git from GitHub:

```
  git clone https://github.com/exceljava/strata-excel.git
```

The projects use Apache Maven as the build system. Version 3.5.0 or later is required. Simply run this command to compile and install the source code locally:

```
  mvn install
```

Note that Strata-Excel is based on Java SE 8. Version 8u40 or later is required to compile the code.

## Extending Strata-Excel

Strata-Excel wraps the Strata types and methods to expose them to Excel.

These wrappers are generated automatically from the Strata source code via the Python script 'tools/generate_jinx_wrappers.py'
and package 'tools/gencode'.

In order to add new types and methods to the Strata-Excel wrapper code, update the config files in 'tools/gencode/config' and run
'tools/generate_jinx_wrappers.py. The folder structure of the config directory mirrors the Strata source.

Python 3.6 is required to build the wrappers.
