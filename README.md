# Git LFS mirror of `ports.ubuntu.com`

This git repository contains a mirror of
[ports.ubuntu.com](https://ports.ubuntu.com/), with external objects
stored using [Git LFS](https://git-lfs.com/).

This repository was created using rsync from
`rsync.ports.ubuntu.com::ubuntu-ports` on 2024-04-19.  The goal is to
keep it in sync with `ports.ubuntu.com` going forward.

## Cloning

The Git LFS objects are not available via GitLab, therefor to clone
this repository successfully you will need to disable Git LFS smudging
using the `GIT_LFS_SKIP_SMUDGE=1` environment variable like this:

```
GIT_LFS_SKIP_SMUDGE=1 git clone https://gitlab.com/debdistutils/archives/ubuntu/ports.ubuntu.com.git
```

Be careful about size: The git pack to download is currently about
286MB and the unpacked checkout will be around 9GB.

# Signature Verification

Commits are signed using [my PGP
key](https://blog.josefsson.org/2019/03/21/openpgp-2019-key-transition-statement/)
with fingerprint:

```
pub   ed25519 2019-03-20 [SC]
      B1D2 BD13 75BE CB78 4CF4  F8C4 D73C F638 C53C 06BE
```

Alternatively, the new dedicated importer key with the following
fingerprint:

```
sec   rsa3072 2024-06-15 [SC]
      A6DB 3F7E A841 C2E2 1D5E  72A1 0BC2 D729 80EC B489
uid   Apt archive Git LFS importer <apt2gitlfs@snapt.debian.net>
```

You may view git log and verify commit signatures them as follows:

```
git log --show-signature
```

To verify a single commit use something like this:

```
$ git verify-commit a35bcfcf6e6ec0cc624f6aa5f9ea785bea0220f6
gpg: Signature made Tue Apr 30 13:45:17 2024 CEST
gpg:                using EDDSA key A3CC9C870B9D310ABAD4CF2F51722B08FE4745A2
gpg: Good signature from "Simon Josefsson <simon@josefsson.org>" [ultimate]
$ 
```

## Contact

The maintainer is [Simon Josefsson](https://blog.josefsson.org/).
