load("@io_bazel_rules_go//proto:def.bzl", "go_grpc_library")

go_grpc_library(
    name = "greetertimer_go_grpc",
    importpath = "github.com/pubref/grpc_greetertimer/proto",
    proto = "//java:greetertimer_proto",
)

load("@io_bazel_rules_go//go:def.bzl", "go_binary")

go_binary(
    name = "client",
    srcs = [
        "main.go",
    ],
    deps = [
        ":greetertimer_go_grpc",
        "@org_golang_google_grpc//:go_default_library",
        "@org_golang_x_net//context:go_default_library",
    ],
)
