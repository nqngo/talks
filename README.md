# Collections of presentations

This repo is a collection of talks given over the years.

### 2022
- One Key to Rule Them All - GPG + SSH + FIDO2 + MFA + Zero Trust with Yubikey: [Part 1](https://talks.nhat.ngo.cx/2022-yubikey-one), [Part 2](https://talks.nhat.ngo.cx/2022-yubikey-two)
- Introduction to Openstack: [Slide](https://talks.nhat.ngo.cx/2022-openstack-intro)
- Introduction to Ceph: [Slide](https://talks.nhat.ngo.cx/2022-ceph-intro)
- OpenStack Swift - Operators Workshop: [Slide](https://talks.nhat.ngo.cx/2022-swift-ops-workshop)

### 2023

- Private Skies: Design, Deploy, Build Private Cloud Infrastructure: [Slide](https://talks.nhat.ngo.cx/2023-private-cloud)
- Introduction to Secrets Management: [Slides](https://talks.nhat.ngo.cx/2023-secrets-management-intro)

### 2024

- ITPA Guest Talk: Cracking the Cybersecurity Industry: [Slides](https://talks.nhat.ngo.cx/2024-itpa-cybersec) 

## Library

Built with [Reveal.js](https://revealjs.com) using plain CSS and HTML.

If you are keen on using the same workflow:
- Clone this repo.
- Run `git submodule update --init --recursive`.
- Symlink `index.html` to your latest slide.
- Then you can simply use `github-pages` to publish `index.html`

To update `reveal.js` dependencies:
- Go to `reveal.js` submodule.
- `git fetch`
- `git switch $version --detach` where `$version` is what you want to use. Eg: `5.1.0`

## License
 
MIT licensed.
Copyright (C) 2021- Nhat Ngo.
