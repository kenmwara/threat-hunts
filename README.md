# Threat Hunts

**Four investigations into realistic attacks, each traced from the first sign to the last move and written up as an incident report.**

Threat hunting means searching security logs for an attack that may already be under way, then piecing together what happened and what to do next. Each hunt below was investigated in Microsoft's security tools (Defender and Sentinel) with KQL, Microsoft's log search language. Three were live community hunts on [The Cyber Range](https://www.skool.com/cyber-range), scored on how many investigation questions ("flags") were answered correctly and on time.

<img src="images/overview.png" width="100%" alt="Key takeaways. Four attacks traced from the first sign to the last move. 46 / 46: Ransomware at a dental practice. Harborlight: one bad download, every computer locked in just over three hours. Every question answered. 17 / 17: An AI assistant tricked. Echo Leaks: hidden instructions made Copilot read 13 private files. A perfect score. 16 / 16: A hacked web server. Meridian: a website flaw led to full control, and a backdoor left running. Full marks. ≈1 h 40 m: Hidden browsing traced. Unauthorized Tor use on a test computer, rebuilt from Defender's logs.">

| Investigation | What happened | Result |
|---|---|---|
| **[Harborlight](https://github.com/kenmwara/threat-hunt-harborlight)** | Ransomware at a dental practice | 46 / 46 questions · 4,060 of 4,190 points |
| **[Echo Leaks](https://github.com/kenmwara/threat-hunt-echo-leaks)** | Microsoft 365 Copilot tricked by a Word file | 17 / 17 questions · a perfect 1,600 |
| **[Meridian](https://github.com/kenmwara/threat-hunt-meridian)** | A hacked Linux web server | 16 / 16 questions · full marks |
| **[Unauthorized Tor](https://github.com/kenmwara/threat-hunt-tor)** | Hidden browsing on a test computer | Session and relays traced |

## [Harborlight: ransomware at a dental practice](https://github.com/kenmwara/threat-hunt-harborlight)

One phishing download gave an attacker control of the whole network in just over three hours. All 46 investigation questions answered (4,060 of 4,190 points), on time.

<a href="https://github.com/kenmwara/threat-hunt-harborlight"><img src="images/harborlight.png" width="100%" alt="Key takeaways. One bad download gave an attacker the whole network in just over three hours. 3 h 25 m: From one click to full control. A staff member opened a phishing file at 01:57. By 05:22 the attacker had made a new admin account. 3 of 3: Every computer locked. Ransomware encrypted all three machines, after the shared files had been copied out. 0: Alerts anyone acted on. Security software caught one piece of the attack hours later, and nobody saw the alert. 11: Alert rules tested. Each rule was re-run on the evidence, with a fix for every blind spot found. 46 / 46: Every question answered. All 46 investigation flags found, on time."></a>

[Read the full report →](https://github.com/kenmwara/threat-hunt-harborlight)

## [Echo Leaks: an AI assistant tricked into reading private files](https://github.com/kenmwara/threat-hunt-echo-leaks)

Hidden instructions in a Word file made Microsoft 365 Copilot read 13 confidential files and try to send them out. All 17 questions answered, a perfect 1,600 of 1,600, on time.

<a href="https://github.com/kenmwara/threat-hunt-echo-leaks"><img src="images/echo-leaks.png" width="100%" alt="Key takeaways. One normal question to an AI assistant set off hidden instructions in a Word file. 13: Private files read. Copilot opened 13 confidential files the employee had never touched, across 4 company sites. 13: Hidden links to an outside server. Its answers carried links that could have sent the data out. 3 m 39 s: All in under four minutes. The second wave ran with no new question from anyone. 0: Accounts hacked. The AI was tricked, not the person. Resetting her password wouldn't have helped. 17 / 17: Every question answered. A perfect score, with seven alert rules tested against the evidence."></a>

[Read the full report →](https://github.com/kenmwara/threat-hunt-echo-leaks)

## [Meridian: a hacked Linux web server](https://github.com/kenmwara/threat-hunt-meridian)

A website flaw leaked a password, the attacker took full control, and a backdoor was still running at the end. All 16 questions answered, full marks, on time.

<a href="https://github.com/kenmwara/threat-hunt-meridian"><img src="images/meridian.png" width="100%" alt="Key takeaways. A website flaw led to full control, and a backdoor was still running at the end. 57 s: From leaked password to login. A website flaw exposed a settings file with a password. 57 seconds later the attacker logged in with it. 73: Attempts to phone home. A hidden backdoor tried 73 times to contact the attacker. The firewall blocked the traffic, not the program. 1: Backdoor never removed. The server's defences flagged it but left it running. The attack wasn't over. 0: Record of running programs. A clean-up routine had switched off the tool that records them, before the attack began. 16 / 16: Every question answered. Full marks, on time."></a>

[Read the full report →](https://github.com/kenmwara/threat-hunt-meridian)

## [Unauthorized Tor browsing on a work computer](https://github.com/kenmwara/threat-hunt-tor)

A hidden browser was used for about 1 hour 40 minutes on a test computer. The session was rebuilt from Microsoft Defender's logs and an evidence package.

<a href="https://github.com/kenmwara/threat-hunt-tor"><img src="images/tor.png" width="100%" alt="Key takeaways. Hidden web browsing on a test computer, traced from security logs. 3: Hops to hide the traffic. The Tor browser sent the traffic through three relays, over a normal web port. ≈1 h 40 m: How long it ran. From about 05:41 to 07:21 UTC. 0: Websites that can be named. Tor hides which sites were visited, and the computer kept no trace of them. 3: Kinds of evidence combined. File, program and network records, plus a full evidence package from the computer."></a>

[Read the full report →](https://github.com/kenmwara/threat-hunt-tor)

## How each report is written

Every report follows the same incident-report shape: a bottom line first, the key numbers, what happened in order, the evidence behind each finding, the alert rules that would catch it next time (each re-run against the data), and what to do now.

A fifth live hunt closes on 30 October 2026; its report will be added here after it closes.

*Simulated environments only. All data comes from training ranges and lab machines; no real organisation was involved.*
