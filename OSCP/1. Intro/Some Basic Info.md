
# SSH Connection
When accessing Module Exercise VMs that require an SSH connection, we suggest using the SSH command with a couple of extra options as follows:

```
ssh -o "UserKnownHostsFile=/dev/null" -o "StrictHostKeyChecking=no" learner@192.168.50.52
```

In the real world, using either (or both) of these options would open us up to man-in-the-middle attacks


# Simple Terminal Command
For simplicity, we will switch to a less complex version of the terminal with ```crtl + p```


## Updating locate Command DB
```
	sudo updatedb
	locate universal.ovpn
```


# CyberSecurity Term Origin
The term _cybersecurity_ came to mainstream use from a military origin.


# Risk
The most fundamental of these four terms is [_risk_](https://en.wikipedia.org/wiki/Risk) because it applies to many domains outside of cybersecurity and information technology. A simple way to define risk is to consider two axes: the _probability_ that a negative event will occur, and the _impact_ on something we value if such an event happens.

# Threat
 In cybersecurity, a [threat](https://csrc.nist.gov/glossary/term/cyber_threat) is something that poses a risk to an asset we care about protecting. Not all threats are human; if our network depends on the local electricity grid, a severe lightning storm could be a threat to ongoing system operations.

For a threat to become an actual risk, the target being threatened must be _vulnerable_ in some manner.

# Vulnerability
 A [_vulnerability_](https://csrc.nist.gov/glossary/term/vulnerability) is a flaw that allows a threat to cause harm. Not all flaws are vulnerabilities.

# CIA
- **Confidentiality**: Can actors who should not have access to the system or information access the system or information?
- **Integrity**: Can the data or the system be modified in some way that is not intended?
- **Availability**: Are the data or the system accessible when and how they are intended to be?

