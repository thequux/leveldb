package(default_visibility = ["//visibility:public"])

config_setting(
    name = "osx_x86_64",
    constraint_values = [
        "@bazel_tools//platforms:osx",
        "@bazel_tools//platforms:x86_64",
    ],
    visibility = ["//visibility:public"],
)

config_setting(
    name = "linux_x86_64",
    constraint_values = [
        "@bazel_tools//platforms:linux",
        "@bazel_tools//platforms:x86_64",
    ],
    visibility = ["//visibility:public"],
)

cc_library(
    name = "port",
    hdrs = glob(["*.h"]),
    defines = select({
        ":osx_x86_64": [
            "LEVELDB_PLATFORM_POSIX=1",
            "LEVELDB_IS_BIG_ENDIAN=0",
        ],
        ":linux_x86_64": [
            "LEVELDB_PLATFORM_POSIX=1",
            "LEVELDB_IS_BIG_ENDIAN=0",
        ],
        "//conditions:default": [],
    }),
)
