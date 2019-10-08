
workspace(name = "base")

EXTR = "external_rules"

local_repository(
    name = "rules_python",
    path = "%s/rules_python" % EXTR,
)

load("@rules_python//python:repositories.bzl", "py_repositories")
py_repositories()

local_repository(
    name= "bazel_skylib",
    path = "%s/bazel-skylib" % EXTR,
)

local_repository(
    name = "io_bazel_rules_go",
    path = "%s/rules_go/" % EXTR,
)


local_repository(
    name = "bazel_gazelle",
    path = "%s/bazel-gazelle/" % EXTR,
)

local_repository(
    name = "rules_jvm_external",
    path = "external_rules/rules_jvm_external/",
)

local_repository(
    name = "io_bazel_rules_docker",
    path = "%s/rules_docker/" % EXTR,
)

load(
    "@io_bazel_rules_docker//repositories:repositories.bzl",
    container_repositories = "repositories",
)

load(
    "@io_bazel_rules_docker//repositories:deps.bzl",
    container_deps = "deps",
)
container_deps()

#load(
#    "@rules_jvm_external//:defs.bzl",
#    "maven_install",
#)

container_repositories()

#maven_install(
#    artifacts = [
#        "junit:junit:4.12",
#        "android.arch.lifecycle:common:1.1.1",
#        "android.arch.lifecycle:viewmodel:0.1.1",
#        "androidx.test.espresso:espresso-web:3.1.1",
#        "com.android.support:design:27.0.2",
#    ],
#    repositories = [
#        "https://maven.google.com", 
#        "https://repo1.maven.org/maven2",
#    ],
#    generate_compat_repositories = True,
#)

#load("@maven//:compat.bzl", "compat_repositories")
#compat_repositories()

load(
    "@io_bazel_rules_docker//container:container.bzl",
    "container_pull",
)

container_pull(
    name = "ubuntu_base",
    registry = "docker.io",
    repository = "library/ubuntu",
    digest = "sha256:1bbdea4846231d91cce6c7ff3907d26fca444fd6b7e3c282b90c7fe4251f9f86",
)
