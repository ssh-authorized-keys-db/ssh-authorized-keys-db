# ssh-authorized-keys-db
manage your ssh authorized keys via a central database

openssh provides an sshd_config directive called AuthorizedKeysCommand, 
which specifies a program to be used to look up the user's public keys.

this idea for this project is to use aws dynamodb to store public keys
and to provide scripts to centrally manage those keys and then to look
them up via AuthorizedKeysCommand dynamically at the moment of login.

the benefits to this approach are that you can by default keep systems
secure and then, without any agent running on the box at all, you can
enable access when you need it and remove it when you don't.
