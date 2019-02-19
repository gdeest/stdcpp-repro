package(default_visibility = ["//visibility:public"])

load(
  "@io_tweag_rules_haskell//haskell:haskell.bzl",
  "haskell_binary",
  "haskell_toolchain",
  "haskell_import",
)

haskell_toolchain(
  name = "ghc",
  version = "8.4.3",
  tools = "@ghc//:bin",
)

haskell_import(name = "base")

haskell_binary(
  name = "hsbin",
  src_strip_prefix = "hs",
  srcs = glob(['hs/**/*.hs']),
  deps = [
    "base",
    "cclib",
  ],
)

cc_library(
  name = "cclib",
  srcs = ["cc/lib.cpp"],
  hdrs = ["cc/lib.h"],
  strip_include_prefix = "cc/",
  linkstatic = True,
)
