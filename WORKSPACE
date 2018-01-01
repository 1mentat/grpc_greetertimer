workspace(name = "org_pubref_grpc_greetertimer")

# This is necessary as the java proto target pulls in rules_protobuf
# example/helloworld/proto:BUILD file that has a reference to
# csharp_proto_library.  csharp target aren't actually used in this
# repo directly.
git_repository(
    name = "io_bazel_rules_dotnet",
    commit = "98ae4fe638b33a0d5cbb8d874a4c451d95e8c592",  # Jan 1, 2018
    remote = "https://github.com/bazelbuild/rules_dotnet.git",
)

load("@io_bazel_rules_dotnet//dotnet:csharp.bzl", "csharp_repositories")

csharp_repositories(use_local_mono = True)

git_repository(
    name = "org_pubref_rules_node",
    remote = "https://github.com/pubref/rules_node.git",
    tag = "v0.4.1",
)

load("@org_pubref_rules_node//node:rules.bzl", "node_repositories")

node_repositories()

# ================================================================

http_archive(
    name = "io_bazel_rules_closure",
    sha256 = "25f5399f18d8bf9ce435f85c6bbf671ec4820bc4396b3022cc5dc4bc66303609",
    strip_prefix = "rules_closure-0.4.2",
    urls = [
        "http://mirror.bazel.build/github.com/bazelbuild/rules_closure/archive/0.4.2.tar.gz",
        "https://github.com/bazelbuild/rules_closure/archive/0.4.2.tar.gz",
    ],
)

load("@io_bazel_rules_closure//closure:defs.bzl", "closure_repositories")

closure_repositories()

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

git_repository(
    name = "org_pubref_rules_protobuf",
    remote = "https://github.com/pubref/rules_protobuf.git",
    tag = "v0.8.1",
)

# load("@org_pubref_rules_protobuf//go:rules.bzl", "go_proto_repositories")

# go_proto_repositories()

# load("@org_pubref_rules_protobuf//java:rules.bzl", "java_proto_repositories")

# java_proto_repositories()

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
