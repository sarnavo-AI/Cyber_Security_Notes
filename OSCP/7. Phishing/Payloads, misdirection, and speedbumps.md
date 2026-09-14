
## Inbound email filters

The most common technologies designed to impact phishing campaigns include [inbound email filters](https://www.proofpoint.com/uk/threat-reference/email-filtering), which scan all incoming email for markers of malicious behavior, and block them if they look suspicious.

Most email filtering technologies consider the relative _reputation_ of an incoming email's domain. This is calculated in various ways depending on the product, but most tend to use [reputation block lists](https://icannwiki.org/Reputation_Block_Lists), in combination with other factors like the relative age of the sender's email domain.

Most email filtering products scrutinize file attachments, so we must leverage evasion techniques when delivering our payloads. Certain file attachments are especially scrutinized, including **EXE** and **SCR** file types, which are often considered malicious. Depending on the product, other executables (or files that contain executable code) may be considered malicious, including Office documents, PDF files, archive files (like ZIP files), or script files as well as hyperlinks that point to external domains hosting these file types.

## Identifying risks of malicious Office macros
Several applications in the Microsoft Office family support [_Visual Basic for Applications_](https://learn.microsoft.com/en-us/office/vba/library-reference/concepts/getting-started-with-vba-in-office) (VBA), a built-in scripting language that enables Office documents to execute custom [_macros_](https://learn.microsoft.com/en-us/office/vba/library-reference/concepts/getting-started-with-vba-in-office). Macros are intended to make Office documents more dynamic with embedded automation, which can be useful when distributing complicated documents in a large organization.

Attackers have been using malicious Office macros to execute code for a long time. In 1999, the US-CERT warned about the [Melissa Macro Virus](https://insights.sei.cmu.edu/documents/506/1999_019_001_496184.pdf), which originated from a malicious Microsoft Word document. Since then, attackers have used Office macros _extensively_ in phishing campaigns.

Microsoft has attempted to address malicious macros. First, they disabled them by default, forcing users to explicitly enable them. Microsoft also introduced the [Mark of the Web](https://en.wikipedia.org/wiki/Mark_of_the_Web) (MotW), a file attribute set by Windows when a file is downloaded from an external source. This is enabled by Windows' default NTFS file system.

![[Pasted image 20260729205430.png]]
 MoTW

Microsoft introduced [_Protected View_](https://support.microsoft.com/en-gb/office/what-is-protected-view-d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653), which presents a warning when users open Office documents with the MotW attribute set. In this case, users must take action to bypass the warning and edit the document or use its dynamic content, including macros.

In a recent development, [Microsoft started blocking macros running in any documents with a MotW by default](https://learn.microsoft.com/en-us/microsoft-365-apps/security/internet-macros-blocked). This makes phishing with Office macros less effective, since any file downloaded from an email will have the MotW attribute set.

## Assess threats from malicious files
Macros aren't the only files that can execute client-side code. While Windows-based **EXE** files are executable (as the name suggests) it's statistically unlikely that these files will even reach a target's inbox. Even if an **EXE** file reached its intended destination, most users are aware of the danger of this type of file. Because of this, attackers have moved to other types of files, including [SCR files](https://www.malwarebytes.com/blog/news/2014/11/rogue-scr-file-links-circulating-in-steam-chat), [HTA files](https://trustedsec.com/blog/malicious-htas), and [JScript files](https://www.broadcom.com/support/security-center/protection-bulletin/yet-another-jscript-rat-spreads-via-phishing-campaign).

SCR --> Screen saver file
HTA --> natively runs HTML, Jscript, VBScript, CSS without a JS Engine like V8 or Node.JS, it uses something native in windows like Trident (MSHTML.dll)
JScript --> Windows version of JavaScript

For example, [CVE-2017-11882](https://nvd.nist.gov/vuln/detail/CVE-2017-11882) is a memory corruption vulnerability in the [Equation Editor](https://support.microsoft.com/en-gb/office/equation-editor-6eac7d71-3c74-437b-80d3-c7dea24fdf3f), which was bundled with Microsoft Office until 2018. Even as late as 2023, some endpoint protection vendors [reported seeing active exploitation of this vulnerability](https://www.kaspersky.co.uk/blog/cve-2017-11882-exploitation-on-the-rise/26372/) targeting organizations who had not updated Office.

Similarly, [CVE-2023-21716](https://nvd.nist.gov/vuln/detail/CVE-2023-21716) is a vulnerability in Microsoft Word which targets the [RTF file](https://en.wikipedia.org/wiki/Rich_Text_Format) parser. [PoCs for this vulnerability](https://github.com/JMousqueton/CVE-2023-21716) are also publicly available.

Other applications are also prone to file parsing vulnerabilities, including PDF viewers. Adobe Acrobat Reader is a common target for attackers and vulnerability researchers alike. Consider [CVE-2023-21608](https://nvd.nist.gov/vuln/detail/CVE-2023-21608), which is a [_use-after-free_](https://owasp.org/www-community/vulnerabilities/Using_freed_memory#:~:text=Use%20after%20free%20errors%20occur,conditions%20and%20other%20exceptional%20circumstances) vulnerability. Several [public PoCs for this vulnerability](https://github.com/hacksysteam/CVE-2023-21608) can execute arbitrary code.

In an especially advanced targeted phishing attack, we could even leverage a vulnerability in a piece of software which we know our target runs. In this case, we would research the kinds of software our target may be using and try to find vulnerabilities which may affect that software. Different industries tend to use different kinds of software from document readers such as [_Office_](https://www.microsoft.com/en-us/microsoft-365/microsoft-office) and [_Adobe Reader_](https://get.adobe.com/reader/) or email clients such as [_Outlook_](https://www.microsoft.com/en-us/microsoft-365/outlook/outlook-for-windows) to browsers such as [_Google Chrome_](https://www.google.com/chrome/?brand=FHFK&ds_kid=43700078760035379&gad_source=1&gclid=Cj0KCQiA7se8BhCAARIsAKnF3rzmTRPb6eMuxWuYmlZDLVV_BN7HVXj8Gjcse-T64Xzs8SNXZs7jGZEaAp9oEALw_wcB&gclsrc=aw.ds). We could even research job postings or websites such as [_Glassdoor_](https://www.glassdoor.com/index.htm), [_LinkedIn_](https://www.linkedin.com/), company websites, software review websites like [_G2 Crowd_](https://www.g2.com/) or [_Capterra_](https://www.capterra.com/), industry-specific forums or blogs, and technology news websites to gain information about technology used by the target organization.



