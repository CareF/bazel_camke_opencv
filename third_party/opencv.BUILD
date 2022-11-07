load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

licenses(["notice"])

package(default_visibility = ["//visibility:public"])

filegroup(
    name = "all_srcs",
    srcs = glob(["**"]),
    visibility = ["//visibility:private"],
)

cmake(
    name = "opencv",
    generate_args = [
        "-GNinja",
    ],
    cache_entries = {
        "BUILD_LIST": "core",
    },
    lib_source = ":all_srcs",
    out_include_dir = "include/opencv4",
    out_shared_libs = [
        "libopencv_core.so.406",
    ],
    visibility = ["//visibility:public"],
)
