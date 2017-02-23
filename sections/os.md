## OS Security

### OS Security Comparison

In general, Linux is more secure than OSX, and OSX is more secure than Windows, for a few reasons:

1. There are far more Windows users than users of OSX or Linux. Though there is conflicting information on this subject, Windows tends to have a market share between 89-94%, while OSX has a market share between 6-10% and Linux has a market share of around 2%. This means it makes sense for virus makers to target Windows machines for maximum gains, and there are many more viruses for Windows as a result.
2. Microsoft operating systems, especially Windows 10, tend to "phone home" more often than OSX. With that said, OSX does report many actions to Apple, and iCloud represents a security hole in OSX. Linux distributions, in general, have no central corporation to report information to.
3. Windows uses a highly insecure model for users to install software that involves downloading and running large, unsercured binary files. OSX isn't much better, but security-conscious users can use solutions such as Homebrew to install critical software. Linux uses secure pacakage managers for installing software.

### OS Software Security

In general, and especially with Windows, keep all your software and your operating system up to date. 

To provide an additional layer of physical security, consider using a solution for encrypting your whole hard drive. Microsoft [BitLocker](https://en.wikipedia.org/wiki/BitLocker) has some issues, but it can protect you from hackers and malicious intruders, though not state actors. Another solution is [Symantec Disk Encryption with PGP](https://www.symantec.com/products/information-protection/encryption/endpoint-encryption), which is usable on Windows machines. Apple has its own equivelant of BitLocker called FileVault that is more secure as long as you disable storing your keys on iCloud. Many Linux distributions, such as Ubuntu, have the option to encrypt the entire disk by default. With these solutions, make sure to turn on password or PIN security for when the computer boots, and power off rather than shut down your machine while in transit.

On OSX, consider not using iCloud integrations when possible, as this has been a security sore spot on the OS. While Microsoft offers some security options in Windows 10, there have been numerous examples of the OS ignoring user settings for privacy and security.
