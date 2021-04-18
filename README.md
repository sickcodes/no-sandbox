# [No Sandbox](https://github.com/sickcodes/no-sandbox)
## *"Applications That Run Chromium Without The Sandbox"*

![Chrome Sandbox](/nosandbox.png?raw=true "Chrome Sandbox Page")

## Page: [https://no-sandbox.io/](https://no-sandbox.io/)

## Project: [https://github.com/sickcodes/no-sandbox](https://github.com/sickcodes/no-sandbox)

## Twitter: [https://twitter.com/sickcodes](https://twitter.com/sickcodes)

The Chrome browser uses a sandbox.

The sandbox status page is found in all Chromium based and Chrome applications:

## [chrome://sandbox](chrome://sandbox)

See your Chrome sandbox status: [chrome://sandbox/](chrome://sandbox/)

![Chrome Sandbox](/Chrome-Sandbox.png?raw=true "Chrome Sandbox Page")

(Right click, copy paste URL: *Chrome won't even let you hyperlink to that page!*)

# Danger

A Chromium based javascript exploit can potentially affect every single downstream application that is built using the Chromium engine.

## List of almost daily exploits that affect Chromium based applications.

Chrome: [https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=chrome](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=chrome)

Chromium: [https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=chromium](https://cve.mitre.org/cgi-bin/cvekey.cgi?keyword=chromium)

When the sandbox is **disabled** using the flag option `--no-sandbox`, websites or rendered pages can potentially execute malicious Javascript based exploits on your computer.

This exposes the user to Remote Code Execution (RCE) exploits that can execute arbitrary code on your computer.

Inside of regular Chrome, where the sandbox is enabled, this is much harder to achieve, unless the attacker combines this with a "sandbox escape" vulnerability.

However, since a while ago, many applications have decided to put Applications inside of the Web Browser.

One such application that uses the `--no-sandbox` flag is [nodejs](https://nodejs.org/).

Node is a **back-end** Javascript runtime framework.

However, one such front-end framework built with nodejs is a popular appliation framework named [Electron](https://www.electronjs.org).

# Electron

## "desktop applications ... always trusted"?

As per their Documentation, they clearly outline the risks involved with running Electron Applications.

[https://www.electronjs.org/docs/api/sandbox-option](https://www.electronjs.org/docs/api/sandbox-option)

> *One of the key security features of Chromium is that all blink rendering/JavaScript code is executed within a sandbox. This sandbox uses OS-specific features to ensure that exploits in the renderer process cannot harm the system.*

> *Usually this is not a problem for desktop applications since the code is always trusted, but it makes Electron less secure than Chromium for displaying untrusted web content.*

The last sentence is quite a statement.

---------

# Applications that use the `--no-sandbox` flag when running Chromium and Chrome based Applications and may expose users to RCE vulnerabilities:

Are we missing any apps? Please submit a Pull Request on the [sickcodes/no-sandbox GitHub repo](https://github.com/sickcodes/no-sandbox)

Official Application List: [https://www.electronjs.org/apps](https://www.electronjs.org/apps)

| **App** | **Sandbox** | **Built With** | **Source** | **Desktop Platforms** | **Risks** | **Other Examples** | 
|---|---|---|---|---|---|---|
| [Slack](https://slack.com/) | Enabled | Electron |**Closed Source** | Windows, macOS, Linux | Untrusted desktop application without source code, but sandbox enabled. | [2020-09-28 XSS to HTML injection RCE](https://hackerone.com/reports/783877) |
| [Twitch](https://twitch.com/) | **DISABLED** | Electron |**Closed Source** | Windows, macOS | Untrusted desktop application without source code |
| [VSCode](https://code.visualstudio.com/) | **DISABLED** | Electron | [https://github.com/microsoft/vscode](https://github.com/microsoft/vscode) | Windows, macOS, Linux | Untrusted VSCode extensions can execute malicious code on your computer. | [ZDNet: Malicious extensions](https://www.zdnet.com/article/microsoft-releases-emergency-security-updates-for-windows-and-visual-studio/), [CVE-2020-17023 package.json RCE](https://msrc.microsoft.com/update-guide/en-us/vulnerability/CVE-2020-17023), [CVE-2020-17022 Image based RCE](https://msrc.microsoft.com/update-guide/en-us/vulnerability/CVE-2020-17022) |
| [Signal](https://https://signal.org/) | **DISABLED** | Electron | [https://github.com/signalapp/Signal-Desktop](https://github.com/signalapp/Signal-Desktop) | Windows, macOS, Linux | A JavaScript based exploit would lead to RCE |
| [FB Messenger](https://www.messenger.com/desktop) | **DISABLED** | Electron | **Closed Source** | Windows | Any JS based exploit would lead to RCE. |
| [Microsoft Teams](https://code.visualstudio.com/) | **DISABLED** | Electron | **Closed Source** | Windows, macOS | Untrusted desktop application without source code. |
| [Keybase](https://keybase.io/) | **DISABLED** | Electron | [https://github.com/keybase/client](https://github.com/keybase/client) | Windows, macOS, Linux | A JavaScript based exploit would lead to RCE |
| [Discord](https://discord.com/) | **DISABLED** | Electron | **Closed Source** | Windows, macOS, Linux | Untrusted desktop application without source code. A JavaScript based exploit would lead to RCE |

