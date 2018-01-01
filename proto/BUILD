load("@io_bazel_rules_go//proto:def.bzl", "go_grpc_library")

proto_library(
    name = "greetertimer_proto",
    srcs = [
        "greetertimer.proto",
    ],
)

go_grpc_library(
    name = "go_default_library",
    importpath = "github.com/pubref/grpc_greetertimer/proto",
    proto = ":greetertimer_proto",
    visibility = ["//visibility:public"],
)
