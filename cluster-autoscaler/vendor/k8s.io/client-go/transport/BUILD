package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_test(
    name = "go_default_test",
    srcs = [
        "cache_test.go",
        "round_trippers_test.go",
        "token_source_test.go",
        "transport_test.go",
    ],
    embed = [":go_default_library"],
    deps = ["//vendor/golang.org/x/oauth2:go_default_library"],
)

go_library(
    name = "go_default_library",
    srcs = [
        "cache.go",
        "config.go",
        "round_trippers.go",
        "token_source.go",
        "transport.go",
    ],
    importmap = "k8s.io/kubernetes/vendor/k8s.io/client-go/transport",
    importpath = "k8s.io/client-go/transport",
    deps = [
        "//staging/src/k8s.io/apimachinery/pkg/util/net:go_default_library",
        "//vendor/golang.org/x/oauth2:go_default_library",
        "//vendor/k8s.io/klog:go_default_library",
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
        "//staging/src/k8s.io/client-go/transport/spdy:all-srcs",
    ],
    tags = ["automanaged"],
)
