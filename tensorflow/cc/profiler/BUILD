load("//tensorflow:tensorflow.bzl", "tf_cuda_cc_test")

package(
    default_visibility = ["//visibility:public"],
    licenses = ["notice"],  # Apache 2.0
)

tf_cuda_cc_test(
    name = "profiler_test",
    srcs = ["profiler_test.cc"],
    tags = [
        "no_gpu",  # b/77649654
        "no_rocm",  # stream level tracing not supported on ROCm
    ],
    deps = [
        ":profiler",
        "//tensorflow/cc:cc_ops",
        "//tensorflow/core:core_cpu",
        "//tensorflow/core:framework",
        "//tensorflow/core:lib",
        "//tensorflow/core:protos_all_cc",
        "//tensorflow/core:tensorflow",
        "//tensorflow/core:test",
        "//tensorflow/core:test_main",
    ],
)

cc_library(
    name = "profiler",
    srcs = ["profiler.cc"],
    hdrs = ["profiler.h"],
    deps = [
        "//tensorflow/core:lib",
        "//tensorflow/core:protos_all_cc",
        "//tensorflow/core/profiler:protos_all_cc",
        "//tensorflow/core/profiler:tfprof_options",
        "//tensorflow/core/profiler/internal:tfprof_stats",
    ],
)
