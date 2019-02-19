load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

rules_nixpkgs_version = "0.5.2"

rules_nixpkgs_version_is_hash = False

rules_nixpkgs_sha256 = "5a384daa57b49abf9f0b672852f1a66a3c52aecf9d4d2ac64f6de0fd307690c8"

http_archive(
    name = "io_tweag_rules_nixpkgs",
    sha256 = rules_nixpkgs_sha256,
    strip_prefix = "rules_nixpkgs-%s" % rules_nixpkgs_version,
    urls = ["https://github.com/tweag/rules_nixpkgs/archive/%s.tar.gz" % rules_nixpkgs_version] if rules_nixpkgs_version_is_hash else ["https://github.com/tweag/rules_nixpkgs/archive/v%s.tar.gz" % rules_nixpkgs_version],
)

SKYLIB_TAG = "0.6.0"
http_archive(
    name = "bazel_skylib",
    urls = ["https://github.com/bazelbuild/bazel-skylib/archive/{}.tar.gz".format(SKYLIB_TAG)],
    strip_prefix = "bazel-skylib-" + SKYLIB_TAG,
)

RULES_HASKELL_SHA = "12af32dee83ba654cc01a84a4b0f105e80c243a7"
http_archive(
    name = "io_tweag_rules_haskell",
    urls = ["https://github.com/tweag/rules_haskell/archive/{}.tar.gz".format(RULES_HASKELL_SHA)],
    strip_prefix = "rules_haskell-" + RULES_HASKELL_SHA,
)

load(
   "@io_tweag_rules_haskell//haskell:haskell.bzl",
   "haskell_register_ghc_bindists",
   "haskell_register_toolchains",
)

haskell_register_ghc_bindists(
   version = "8.2.2",
)

