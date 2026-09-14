
For a web application to show a specific page, a web server provides the file from the file system. These files can be in the web root directory or one of its subdirectories. In Linux systems, the **/var/www/html/** directory is often used as the web root. When a web application displays a page, **http://example.com/file.html** for example, it will try to access **/var/www/html/file.html**. The http link doesn't contain any part of the path except the filename because the web root also serves as a base directory for a web server. If a web application is vulnerable to directory traversal, a user may access files outside of the web root by using relative paths, thus accessing sensitive files like SSH private keys or configuration files.

While it is important to understand how to exploit Directory Traversal vulnerabilities, it is also crucial that we can identify them. We should always check for vulnerabilities by hovering over all buttons, checking all links, navigating to all accessible pages, and (if possible) examining the page's source code. Links can be an especially valuable source of information, providing parameters or other data about the application.

For example, if we find the following link, we can extract vital information from it.

```
https://example.com/cms/login.php?language=en.html
```

First, **login.php** tells us the web application uses PHP. We can use this information to develop assumptions about how the web application works, which is helpful for the exploitation phase.

Second, the URL contains a _language_ parameter with an HTML page as its value. In a situation like this, we should try to navigate to the file directly (**https://example.com/cms/en.html**). If we can successfully open it, we can confirm that **en.html** is a file on the server, meaning we can use this parameter to try other file names. We should always examine parameters closely when they use files as a value.







## Windows
Before wrapping up this section, let's briefly examine directory traversal attacks on Windows. On Linux, we usually use the **/etc/passwd** file to test directory traversal vulnerabilities. On Windows, we can use the file **C:\Windows\System32\drivers\etc\hosts** to test directory traversal vulnerabilities, which is readable by all local users.

Once we gather information about the running application or service, we can research paths leading to sensitive files. For example, if we learn that a target system is running the [_Internet Information Services_](https://en.wikipedia.org/wiki/Internet_Information_Services) (IIS) web server, we can research its log paths and web root structure. Reviewing the [Microsoft documentation](https://docs.microsoft.com/en-us/iis/manage/provisioning-and-managing-iis/managing-iis-log-file-storage), we learn that the logs are located at **C:\inetpub\logs\LogFiles\W3SVC1\**. Another file we should always check when the target is running an IIS web server is **C:\inetpub\wwwroot\web.config**, which may contain sensitive information like passwords or usernames.

In this section, we used the **../** sequence for directory traversal on Linux. As shown, Windows uses backslashes instead of forward slashes for file paths. Therefore, **..\** is an important alternative to **../** on Windows targets. While [RFC 1738](https://www.ietf.org/rfc/rfc1738.txt) specifies to always use slashes in a URL, we may encounter web applications on Windows which are only vulnerable to directory traversal using backslashes. Therefore, we should always try to leverage both forward slashes and backslashes when examining a potential directory traversal vulnerability in a web application running on Windows.


