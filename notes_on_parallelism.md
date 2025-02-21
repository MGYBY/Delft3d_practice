# No-coupling case
File structure: dimr_config.xml config file and dflowfm folder (created by GUI, the case setup file is `FlowFM.mdu`).

The files in `C:\Program Files\Deltares\Delft3D FM Suite 2025.01 HMWQ\plugins\DeltaShell.Dimr\kernels\x64\lib` should be copied to . and .\output paths.

Take 6 processes running in parallel as example:

*in cmd:*
```
cd dflowfm
set dimrdir="C:\Program Files\Deltares\Delft3D FM Suite 2025.01 HMWQ\plugins\DeltaShell.Dimr\kernels"
call %dimrdir%\x64\bin\dflowfm-cli.exe --partition:ndomains=6:icgsolver=6 FlowFM.mdu
cd ..
call %dimrdir%\x64\bin\run_dimr_parallel.bat 6 dimr_config.xml
```

In dimr_config.xml:

```
<?xml version="1.0" encoding="iso-8859-1"?>
<dimrConfig xmlns="http://schemas.deltares.nl/dimrConfig" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://schemas.deltares.nl/dimrConfig http://content.oss.deltares.nl/schemas/d_hydro-1.00.xsd">
    <documentation>
        <fileVersion>1.00</fileVersion>
        <createdBy>Deltares, Coupling team</createdBy>
        <creationDate>2015-05-20T07:56:32+01</creationDate>
    </documentation>
    <control>
        <start name="dflowfm"/>
    </control>
    <component name="dflowfm">
        <library>dflowfm</library>
        <process>0 1 2 3 4 5</process>
        <mpiCommunicator>DFM_COMM_DFMWORLD</mpiCommunicator>
        <workingDir>dflowfm</workingDir>
        <inputFile>FlowFM.mdu</inputFile>
    </component>
</dimrConfig>
```
