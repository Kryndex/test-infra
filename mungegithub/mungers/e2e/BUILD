package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_test(
    name = "go_default_test",
    srcs = [
        "e2e_test.go",
        "resolved_test.go",
    ],
    embed = [":go_default_library"],
    importpath = "k8s.io/test-infra/mungegithub/mungers/e2e",
    deps = [
        "//mungegithub/options:go_default_library",
        "//vendor/k8s.io/contrib/test-utils/utils:go_default_library",
    ],
)

go_library(
    name = "go_default_library",
    srcs = [
        "e2e.go",
        "resolved.go",
    ],
    importpath = "k8s.io/test-infra/mungegithub/mungers/e2e",
    deps = [
        "//mungegithub/mungers/flakesync:go_default_library",
        "//mungegithub/options:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/sets:go_default_library",
        "//vendor/k8s.io/contrib/test-utils/utils:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//mungegithub/mungers/e2e/fake:all-srcs",
    ],
    tags = ["automanaged"],
)
