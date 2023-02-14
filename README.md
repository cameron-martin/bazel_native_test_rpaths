The test in the subdirectory fails when using the hermetic linux sandbox or remote execution:

```
$ bazel test //... --config=hermetic
//:rootdir_test                                                 (cached) PASSED in 0.1s
//test:subdir_test                                                       FAILED in 0.1s

/execroot/native_test_rpaths/bazel-out/k8-fastbuild/bin/test/foo.exe.runfiles/native_test_rpaths/test/foo.exe: error while loading shared libraries: liblibbar_Udynamic.so: cannot open shared object file: No such file or directory

$ bazel test //...
//:rootdir_test                                                 (cached) PASSED in 0.1s
//test:subdir_test                                                       PASSED in 0.1s
```