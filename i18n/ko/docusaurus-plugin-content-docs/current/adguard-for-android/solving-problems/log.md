---
title: How to collect debug logs
sidebar_position: 2
---

:::정보

This article is about AdGuard for Android, a multifunctional ad blocker that protects your device at the system level. To see how it works, [download the AdGuard app](https://agrd.io/download-kb-adblock)

:::

:::note

Data and/or files provided in logs are processed in accordance with [the AdGuard Privacy Policy](https://adguard.com/en/privacy.html).

:::

In this article, we'll guide you through the process of collecting debug logs, an essential troubleshooting step for solving complex issues that may potentially arise. Debug logs provide detailed insight into the inner workings of AdGuard for Android. If the AdGuard support team asks you to provide debug logs, simply follow these instructions.

:::note

AdGuard는 사용자의 개인정보를 보호하기 위해 최선을 다하고 있습니다. We strictly follow our [Privacy Policy](https://adguard.com/privacy/android.html) and do not collect any private information about users. 지원팀에 로그를 보내기 전에 파일에 전달하고 싶지 않은 추가 정보가 포함되어 있는지 확인하세요. 이러한 정보가 포함되어 있는 경우, 먼저 삭제하는 것이 좋습니다.

:::

### Recording debug log

To collect **debug** log and send it to us, you need to perform following steps:

1. Go to *Settings* → *General* → *Advanced*.
1. Tap *Logging level* and set it to *Debug*.
1. Reproduce the problem and try to remember the exact time it occurred.
1. Wait a while, then return to *Settings* and choose the *Support* tab. Tap *Report a bug* and complete the required fields. Don't forget to check the *Send app logs and system info* checkbox. Finally tap *Send*.

If you're interested in following the resolution of your issue and engaging in a dialogue with the developers, we recommend that you take the following steps after completing the first three:

1. Wait a while, then return to the *Advanced* screen and export logs via *Export logs and system info*. Then report a bug on GitHub by following these [instructions](/guides/report-bugs.md).
1. After creating an issue on GitHub, send the log file to <devteam@adguard.com>. Include the time of the bug and attach a link to your issue or its number (it appears as #number next to the title). Alternatively, you can upload the log file to Google Drive and send it to <devteam@adguard.com>. Add the file link to your GitHub issue
