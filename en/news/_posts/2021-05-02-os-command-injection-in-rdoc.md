---
layout: news_post
title: "CVE-2021-31799: A command injection vulnerability in RDoc"
author: "aycabta"
translator:
date: 2021-05-02 09:00:00 +0000
tags: security
lang: en
---

There is a vulnerability about Command Injection in RDoc which is bundled in Ruby.
It is recommended that all Ruby users update RDoc to the latest version that fixes this issue.

## Details

The following vulnerability has been reported.

* [CVE-2021-31799](https://nvd.nist.gov/vuln/detail/CVE-2021-31799)

RDoc used to call `Kernel#open` to open a local file. If a Ruby project has a file whose name starts with `|` and ends with `tags`, the command following the pipe character is executed. A malicious Ruby project could exploit it to run an arbitrary command execution against a user who attempts to run `rdoc` command.

Ruby users whose version of RDoc is affected by this issue should update to the latest version of RDoc.

## Affected Versions

* All releases of RDoc from 3.11 to 6.3.0

## How to Update

Run the following command to update RDoc to the latest version (6.3.1 or later) to fix the vulnerability.

```
gem install rdoc
```

## Credits

Thanks to [Alexandr Savca](https://hackerone.com/chinarulezzz) for reporting the issue.

## History

* Originally published at 2021-05-02 09:00:00 UTC