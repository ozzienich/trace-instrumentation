# trace-instrumentation


depedency:
environment-modules


 source  /etc/profile.d/modules.sh
 





## build
```shell
cmake                                       \
    -B omnitrace-build                      \
    -D CMAKE_INSTALL_PREFIX=/opt/omnitrace  \
    -D OMNITRACE_USE_HIP=ON                 \
    -D OMNITRACE_USE_ROCM_SMI=ON            \
    -D OMNITRACE_USE_ROCTRACER=ON           \
    -D OMNITRACE_USE_PYTHON=ON              \
    -D OMNITRACE_USE_OMPT=ON                \
    -D OMNITRACE_USE_MPI_HEADERS=ON         \
    -D OMNITRACE_BUILD_PAPI=ON              \
    -D OMNITRACE_BUILD_LIBUNWIND=ON         \
    -D OMNITRACE_BUILD_DYNINST=ON           \
    -D DYNINST_BUILD_TBB=ON                 \
    -D DYNINST_BUILD_BOOST=ON               \
    -D DYNINST_BUILD_ELFUTILS=ON            \
    -D DYNINST_BUILD_LIBIBERTY=ON           \
    omnitrace-source
cmake --build omnitrace-build --target all --parallel 8
cmake --build omnitrace-build --target install
source /opt/omnitrace/share/omnitrace/setup-env.sh
```


  cmake -B omnitrace-build -DCMAKE_INSTALL_PREFIX=/opt/omnitrace  -DOMNITRACE_BUILD_DYNINST=ON -DDYNINST_BUILD_{TBB,ELFUTILS,BOOST,LIBIBERTY}=ON omnitrace-source
  cmake --build omnitrace-build --target all
cmake --build omnitrace-build --target install
  
