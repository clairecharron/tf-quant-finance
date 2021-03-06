# Tools to build Diffusion Models

licenses(["notice"])

package(default_visibility = ["//tf_quant_finance:__subpackages__"])

py_library(
    name = "models",
    srcs = ["__init__.py"],
    deps = [
        ":euler_sampling",
        ":generic_ito_process",
        ":heston_model",
        ":ito_process",
    ],
)

py_library(
    name = "ito_process",
    srcs = ["ito_process.py"],
    deps = [],
)

py_library(
    name = "generic_ito_process",
    srcs = ["generic_ito_process.py"],
    deps = [
        ":euler_sampling",
        ":ito_process",
        "//tf_quant_finance/math/pde",
        # tensorflow dep,
    ],
)

py_test(
    name = "generic_ito_process_test",
    size = "small",
    timeout = "moderate",
    srcs = ["generic_ito_process_test.py"],
    python_version = "PY3",
    deps = [
        "//tf_quant_finance",
        # numpy dep,
        # tensorflow dep,
    ],
)

py_library(
    name = "euler_sampling",
    srcs = ["euler_sampling.py"],
    deps = [
        "//tf_quant_finance/math/random_ops",
        # tensorflow dep,
    ],
)

py_test(
    name = "euler_sampling_test",
    size = "medium",
    timeout = "moderate",
    srcs = ["euler_sampling_test.py"],
    python_version = "PY3",
    shard_count = 5,
    deps = [
        "//tf_quant_finance",
        # absl/testing:parameterized dep,
        # numpy dep,
        # tensorflow dep,
    ],
)

py_library(
    name = "heston_model",
    srcs = ["heston_model.py"],
    deps = [
        ":generic_ito_process",
        "//tf_quant_finance/math:piecewise",
        "//tf_quant_finance/math/random_ops",
        # tensorflow dep,
    ],
)

py_test(
    name = "heston_model_test",
    size = "medium",
    timeout = "moderate",
    srcs = ["heston_model_test.py"],
    python_version = "PY3",
    shard_count = 3,
    deps = [
        ":heston_model",
        "//tf_quant_finance",
        # numpy dep,
        # tensorflow dep,
    ],
)
