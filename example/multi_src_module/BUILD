load("@bazel_skylib//:bzl_library.bzl", "bzl_library")
load("//cc_module:defs.bzl", "cc_module", "cc_module_binary")

package(default_visibility = ["//visibility:public"])

licenses(["notice"])

cc_module(
    name = "spanish_english_dictionary",
    src = "spanish_english_dictionary.cc",
    impl_srcs = [
        "spanish_english_dictionary_impl.cc",
    ],
    copts = [
        "-fmodules-ts",
        "-std=c++20",
    ],
)

cc_module(
    name = "speech",
    src = "speech.cc",
    impl_srcs = [
        "speech_impl.cc",
    ],
    copts = [
        "-fmodules-ts",
        "-std=c++20",
    ],
    impl_deps = [
        ":spanish_english_dictionary",
    ],
)

cc_module_binary(
    name = "a.out",
    srcs = [
        "main.cc",
    ],
    deps = [
        ":speech",
    ],
    copts = [
        "-fmodules-ts",
        "-std=c++20",
    ],
)
