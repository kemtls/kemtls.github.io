---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "KEMTLS Implementations"
subtitle: ""
summary: ""
authors: ['thom']
tags: []
categories: []
date: 2024-02-20T16:17:48+01:00
lastmod: 2024-02-20T16:17:48+01:00
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

KEMTLS has been independently implemented by several people.
In this post, we briefly describe some of them.
Note that these implementations followed the academic description of KEMTLS, which differs from the AuthKEM draft in some small ways.

Please let us know if you know of other implementations that we should list here!

## Experimental integration into Rustls

The original implementations by Thom Wiggers were based on Rustls.
This is the code that was used for the experiments and benchmarks that we reported on in the papers.
This code can be found at https://github.com/thomwiggers/kemtls-experiment/.
The most recent version is the ``thesis`` branch which was used for Thom's PhD thesis.

## Integration into Go's `crypto/ssl` stack

For the experiments on a [real-world network]({{< ref "publication/measuring-kemtls" >}}), Sofía Celi and Thom Wiggers implemented KEMTLS in Go.
This code was archived at https://github.com/kemtls/cloudflare-go-kemtls.

## Experimental integration into Botan

The [Botan](https://botan.randombit.net) C++ library for TLS experimented with post-quantum cryptography.
As part of their work, they built an experimental integration of KEMTLS.
This can be found at https://github.com/neXenio/botan/pull/20.

## WolfSSL integration

For the experiments with [KEMTLS in embedded settings]({{< ref "publication/kemtls-embedded" >}}), Ruben Gonzalez integrated KEMTLS in WolfSSL.
This implementation, as well as the measurement scripts, can be found at https://github.com/rugo/wolfssl-kemtls-experiments/tree/paperv1.
