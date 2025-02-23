# Delft3d_practice
Some codes for D3D

## Compilation
- Follow the guide in [this article](https://gist.github.com/H0R5E/c4af6db788b227de702a12e01b64cf46).
- Worked Linux distros: CentOS.
- Configuration command: `./configure CC="${HOME}/d3d_local/bin/mpicc" CXX="${HOME}/d3d_local/bin/mpicxx" MPICXX="${HOME}/d3d_local/bin/mpicxx" F77="${HOME}/d3d_local/bin/mpif77" MPIF77="${HOME}/d3d_local/bin/mpif77" FC="${HOME}/d3d_local/bin/mpifort" MPIFC="${HOME}/d3d_local/bin/mpifort" CPPFLAGS="-I${HOME}/d3d_local/include" NETCDF_CFLAGS="-I${HOME}/d3d_local/include -I${HOME}/d3d_local/include" NETCDF_LIBS="-L${HOME}/d3d_local/lib -lnetcdf" CFLAGS='-O2 ' CXXFLAGS='-O2 ' AM_FFLAGS='-lifcoremt -liomp5' FFLAGS='-O1 --with-mpi' AM_FCFLAGS='-lifcoremt -liomp5' FCFLAGS='-O1 --with-mpi' AM_LDFLAGS='-lifcoremt -liomp5' --prefix="${HOME}/Downloads/delft3dfm-68819/src" 2>&1 | tee c.txt`.
- Intel api 2022 (the latest version wouldn't work).
