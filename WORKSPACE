workspace(name = "envoy")

load("//bazel:api_binding.bzl", "envoy_api_binding")

envoy_api_binding()

load("//bazel:api_repositories.bzl", "envoy_api_dependencies")

envoy_api_dependencies()

load("//bazel:repositories.bzl", "envoy_dependencies")

envoy_dependencies()

load("//bazel:repositories_extra.bzl", "envoy_dependencies_extra")

envoy_dependencies_extra()

load("//bazel:dependency_imports.bzl", "envoy_dependency_imports")

envoy_dependency_imports()

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

commit = "91ee2c572998bb3c64d532afcda207eb8acb3604"
http_archive(
    name = "rpi_bazel",
    url = "https://github.com/mjbots/rpi_bazel/archive/{}.zip".format(commit),
    sha256 = "cf39b74d366dc40652fecedd3ca97f87a739807bc6da9532d55c26fcf8b103ff",
    strip_prefix = "rpi_bazel-{}".format(commit),
    patches = ["//bazel:rpi_bazel_loc.patch"],
    patch_args = ["-p1"],
)
load("@rpi_bazel//tools/workspace:default.bzl",
     rpi_bazel_add = "add_default_repositories")
rpi_bazel_add()
