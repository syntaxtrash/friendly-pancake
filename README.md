# friendly-pancake

to test stuff

### Generating a new SSH key and adding it to the ssh-agent using Git Bash:

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

```bash
ssh-keygen -t ed25519 -C "juandelacruz@example.com"
```

```bash
eval "$(ssh-agent -s)"
```

```bash
ssh-add ~/.ssh/id_ed25519
```

### Adding a new SSH key to your GitHub account:

https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account#adding-a-new-ssh-key-to-your-account

### Creating the SSH Configuration File for multiple github accounts:

```bash
nano ~/.ssh/config
```

```bash
Host github-personal
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519

Host github-work
    HostName github.com
    User git
    IdentityFile ~/.ssh/other_id_ed25519
```

After editing the configuration file, save the changes and exit the text editor. In nano, you can do this by pressing Ctrl + O to write out the file and Ctrl + X to exit.

### Generating a GPG key:

https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key

```bash
gpg --full-generate-key
```

```bash
gpg --list-secret-keys --keyid-format=long

# From the list of GPG keys, copy the long form of the GPG key ID you'd like to use. In this example, the GPG key ID is 3AA5C34371567BD2::
------------------------------------
sec   4096R/3AA5C34371567BD2 2016-03-10 [expires: 2017-03-10]
uid                          Hubot <hubot@example.com>
ssb   4096R/4BB6D45482678BE3 2016-03-10

```

```bash
gpg --armor --export 3AA5C34371567BD2
# Prints the GPG key ID, in ASCII armor format
```

### Adding a GPG key to your GitHub account:

https://docs.github.com/en/authentication/managing-commit-signature-verification/adding-a-gpg-key-to-your-github-account

### Git Global Configuration:

```bash
git config --global user.name "Juan Dela Cruz"
git config --global user.email juandelacruz@example.com
git config --global user.signingkey 3AA5C34371567BD2
```

### Logs

git commit with sign test april 04 2024
git commit with sign test may 05 2024
