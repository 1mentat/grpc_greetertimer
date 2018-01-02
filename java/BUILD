load("@grpc_java//:java_grpc_library.bzl", "java_grpc_library")

proto_library(
    name = "greetertimer_proto",
    srcs = [
        "src/main/proto/greetertimer.proto",
    ],
    visibility = ["//visibility:public"],
)

java_proto_library(
    name = "greetertimer_java_proto",
    deps = [":greetertimer_proto"],
)

java_grpc_library(
    name = "greetertimer_java_grpc",
    srcs = [":greetertimer_proto"],
    deps = [":greetertimer_java_proto"],
)

java_library(
    name = "greetertimer_library",
    testonly = 1,
    srcs = glob(
        ["src/main/java/**/*.java"],
    ),
    resources = glob(
        ["src/main/resources/**"],
    ),
    deps = [
        ":greetertimer_java_grpc",
        ":greetertimer_java_proto",
        ":greetertimer_proto",
        "@org_pubref_rules_protobuf//examples/helloworld/proto:java",
        "@com_google_api_grpc_proto_google_common_protos//jar",
        "@com_google_code_findbugs_jsr305//jar",
        "@com_google_guava_guava//jar",
        "@com_google_protobuf_java//:protobuf_java",
        "@com_google_protobuf_java//:protobuf_java_util",
        "@grpc_java//core",
        "@grpc_java//protobuf",
        "@grpc_java//stub",
    ],
)

java_binary(
    name = "server",
    testonly = 1,
    main_class = "org.pubref.grpc.greetertimer.GreeterTimerServer",
    runtime_deps = [
        ":greetertimer_library",
        "@grpc_java//netty",
    ],
)

java_binary(
    name = "client",
    testonly = 1,
    main_class = "org.pubref.grpc.greetertimer.GreeterTimerClient",
    runtime_deps = [
        ":greetertimer_library",
        "@grpc_java//netty",
    ],
)
