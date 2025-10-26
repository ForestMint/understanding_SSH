# understanding_SSH

This repository is about tips in using SSH to train myself on the various DevOps tools on a personal virtual infrastructure.
It mostly consists in getting used to the various 💩 that might happen around managing SSH connections.
Welcome.

Error 1 :

Message :

@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the ED25519 key sent by the remote host is
SHA256:<my-sha>.
Please contact your system administrator.
Add correct host key in /home/<username>/.ssh/known_hosts to get rid of this message.
Offending ECDSA key in /home/<username>/.ssh/known_hosts:5
Host key for <target-server-ip> has changed and you have requested strict checking.
Host key verification failed.

Explanation :

This is probably because you have in your .ssh folder, on the machine you're trying to connect from, a fingerprint or something related to the target machine.
If this thing is obsolete, possibly because the machine related to the IP stored in .ssh folder has been destroyed and re-created, then it fails when you're trying to connect to the new machine, which is not the machine the fingerprint belongs to.

Fix :

If you do not have any other important information in the .ssh folder, just remove it.

```bash
cd ~
ls -a # displays hidden files and folders
rm -rf .ssh
ls -a # displays hidden files and folders to check that .ssh has been removed
```

Error 2 :

Message :

OpenSSH Private Key exposed on GitHub.
(This will be sent automaticaaly by email)

Explanation :

??

Fix :

??
