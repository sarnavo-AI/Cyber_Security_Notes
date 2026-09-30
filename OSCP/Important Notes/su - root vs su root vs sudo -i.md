`su -` vs. `su` (Without the Hyphen)

|Feature|`su -` (Recommended)|`su`|
|---|---|---|
|**Shell Type**|Login shell|Non-login shell|
|**Environment**|Loads `root` profile and variables|Keeps your original user profile|
|**Current Directory**|Changes to `/root`|Stays in your original folder|
|**System Behavior**|Avoids command paths missing errors|Can break administrative tools due to wrong environment paths|





	Here is the direct comparison between `su root` (specifically `su -`) and `sudo -i` in Linux:

| Feature                  | `su -` (or `su root`)                                               | `sudo -i`                                                                           |
| ------------------------ | ------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| **Password Required**    | **Root user's** password                                            | **Your own** account password                                                       |
| **Account Requirement**  | The root account must be active and have a known password.          | Your user account must be in the `sudo` or `wheel` group.                           |
| **Security Auditing**    | **Low:** Logs subsequent actions generically under the "root" user. | **High:** Logs your specific username alongside the privilege elevation.            |
| **Password Sharing**     | **Required:** Every administrator must know the same root password. | **Not Required:** Admins only need to know their individual passwords.              |
| **Default Availability** | Often disabled/locked by default on modern distros (e.g., Ubuntu).  | Enabled and preferred by default on most modern distros.                            |
| **Primary Risk**         | Leaving the root account active with a shared, static password.     | Misconfiguring the `/etc/sudoers` file and giving too much power to standard users. |
