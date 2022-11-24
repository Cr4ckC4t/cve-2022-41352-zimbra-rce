# (CVE-2022-41352) Zimbra Unauthenticated RCE

> CVE-2022-41352 is an arbitrary file write vulnerability in Zimbra mail servers due to the use of a vulnerable `cpio` version.

- [CVE-2022-41352 (NIST.gov)](https://nvd.nist.gov/vuln/detail/CVE-2022-41352)
- [CVE-2022-41352 (Rapid7 Analysis)](https://attackerkb.com/topics/1DDTvUNFzH/cve-2022-41352/rapid7-analysis)

**Affected [Zimbra versions](https://wiki.zimbra.com/wiki/Zimbra_Releases):**
- Zimbra <9.0.0.p27
- Zimbra <8.8.15.p34

(Refer to the [patch notes](https://wiki.zimbra.com/wiki/Zimbra_Security_Advisories) for more details.)

**Remediation:**

In order to fix the vulnerability apply the latest patch (9.0.0.p27 and 8.8.15.p34 respectively) - or install `pax` and restart the server.

**Usage:**

You can either use flags or manipulate the default configuration in the script manually (config block at the top).
Use `-h` for help.
```bash
$ python cve-2022-41352.py -h

$ vi cve-2022-41352.py
# Change the config items.

$ python cve-2022-41352.py manual
# This will create an attachment that you can then send to the target server.
# The recipient does not necessarily have to exist - if the email with the attachment is parsed by the server the arbitrary file write in cpio will be triggered.
```

**Example:**

![example](https://user-images.githubusercontent.com/63863112/201727401-76a05e0c-d55d-4752-966f-49f2301113f1.png)
(The above screenshot shows a wrong output for the email body but that has been fixed.)

**Demo:**

https://user-images.githubusercontent.com/63863112/201446602-20d9adbb-d138-4d6b-bca7-5bec80d75972.mp4
