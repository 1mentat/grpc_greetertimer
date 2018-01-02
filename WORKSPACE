workspace(name = "org_pubref_grpc_greetertimer")

git_repository(
    name = "grpc_java",
    remote = "https://github.com/grpc/grpc-java.git",
    tag = "v1.7.1",
)

load("@grpc_java//:repositories.bzl", "grpc_java_repositories")

grpc_java_repositories()

# ================================================================

git_repository(
    name = "io_bazel_rules_go",
    remote = "https://github.com/bazelbuild/rules_go.git",
    tag = "0.8.1",
)

load("@io_bazel_rules_go//go:def.bzl", "go_rules_dependencies", "go_register_toolchains", "go_repository")

go_rules_dependencies()

go_register_toolchains()

# ================================================================

go_repository(
    name = "org_golang_google_grpc",
    commit = "65c901e45820d9c7555afc14337b82cf53ea3e42",
    importpath = "google.golang.org/grpc",
)

go_repository(
    name = "org_golang_x_net",
    commit = "d866cfc389cec985d6fda2859936a575a55a3ab6",
    importpath = "golang.org/x/net",
)
