---
layout: post
title:  'git-secret-tell'
date:   2019-02-10 15:21:28 -0500
permalink: git-secret-tell
categories: command
---
git-secret-tell - adds a person, who can access private data.
===============================================================

## SYNOPSIS

    git secret tell [-m] [-d dir] [emails]...


## DESCRIPTION
`git-secret-tell` receives an email addresses as an input, searches for the `gpg`-key in the `gpg`'s 
`homedir` by these emails, then imports a person's public key into the `git-secret`'s inner keychain. 
From this moment this person can encrypt new files with the keyring which contains their key,
but they cannot decrypt the old files, which were already encrypted without their key. 
The files should be re-encrypted with the new keyring by someone who has the unencrypted files.

**Do not manually import secret key into `git-secret`**. Anyways, it won't work with any of the secret-keys imported.


## OPTIONS

    -m  - takes your current `git config user.email` as an identifier for the key.
    -d  - specifies `--homedir` option for the `gpg`, basically use this option if your store your keys in a custom location.
    -h  - shows help.


## MANUAL

Run `man git-secret-tell` to see this note.


## SEE ALSO

[git-secret-init(1)](http://git-secret.io/git-secret-init), [git-secret-add(1)](http://git-secret.io/git-secret-add), 
[git-secret-hide(1)](http://git-secret.io/git-secret-hide), [git-secret-reveal(1)](http://git-secret.io/git-secret-reveal), 
[git-secret-cat(1)](http://git-secret.io/git-secret-cat), [git-secret-killperson(1)](http://git-secret.io/git-secret-killperson)