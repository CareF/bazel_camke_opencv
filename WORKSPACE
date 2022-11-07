load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

_RULES_FOREIGN_CC_VERSION = "0.9.0"
_OPENCV_VERSION = "4.6.0"

http_archive(
    name = "rules_foreign_cc",
    sha256 = "2a4d07cd64b0719b39a7c12218a3e507672b82a97b98c6a89d38565894cf7c51",
    strip_prefix = "rules_foreign_cc-%s" % _RULES_FOREIGN_CC_VERSION,
    urls = [
        "https://bwh.qingtiantruck.com/externalcache/bazelbuild/rules_foreign_cc/%s.tar.gz" % _RULES_FOREIGN_CC_VERSION,
        "https://github.com/bazelbuild/rules_foreign_cc/archive/%s.tar.gz" % _RULES_FOREIGN_CC_VERSION,
    ],
)

load("@rules_foreign_cc//foreign_cc:repositories.bzl", "rules_foreign_cc_dependencies")

rules_foreign_cc_dependencies()

http_archive(
    name = "opencv",
    build_file = "//third_party:opencv.BUILD",
    patch_args = ["-p1"],
    patches = ["//third_party:disable_download.patch"],
    sha256 = "1ec1cba65f9f20fe5a41fda1586e01c70ea0c9a6d7b67c9e13edf0cfe2239277",
    strip_prefix = "opencv-4.6.0",
    urls = [
        "https://github.com/opencv/opencv/archive/refs/tags/%s.tar.gz" % _OPENCV_VERSION,
    ],
)
