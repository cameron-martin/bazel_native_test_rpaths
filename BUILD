load("@bazel_skylib//rules:native_binary.bzl", "native_test")

cc_binary(
    name = "foo",
    srcs = ["foo.c"],
    dynamic_deps = [":bar_dynamic"],
    deps = [":bar"],
    visibility = ["//visibility:public"],
)

cc_library(
    name = "bar",
    srcs = ["bar.c"],
    hdrs = ["bar.h"],
    visibility = ["//visibility:public"],
)

cc_shared_library(
    name = "bar_dynamic",
    roots = [":bar"],
    visibility = ["//visibility:public"],
)

native_test(
    name = "rootdir_test",
    src = "//:foo",
    out = "foo.exe",
)
