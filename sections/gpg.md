## GPG

GPG is an implementation of PGP (Pretty Good Privacy), a set of algorithms and utilities for encryption. We'll use GPG to make a public/private key pair and we'll encrypt a message using our new public key.

### Installing GPG

#### OSX

On OSX, the easiest way to install GPG is through Homebrew, a package manager. To install Homebrew, open your terminal by typing `terminal` in the finder ( the magnifying glass in the top right of your screen). At the `$` prompt, type

    xcode-select --install

once that's finished, copy the command below and paste it into your terminal:

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	
Once that finishes, install GPG with:

    brew install gpg

#### Windows

On Windows, download and install [cygwin](https://cygwin.com/install.html). GPG is available from within Cygwin.

### Creating a public/private key pair

Start the key generation process with

    gpg --gen-key
	
Choose `DSA and Elgamal` from the menu when prompted.

You will next be asked for the strength of the key, which is also the size of the key. I recommend `4096` for real use, but `1024` is ok while learning the tool. Larger keys require more random bits to generate, so many take considerably longer.

You will be asked for your personal information. Fill in your information at the prompts. Follow the prompt for `Okay` when you're satisfied with your entries.

At this stage, you may be asked to generate more random bits for the key generation process. You should be able to simply do some work on the computer to complete the process. Move the mouse around and bang on the keys.

When complete, run

    gpg --list-keys
	
to check that your new key has been imported into the GPG keyring.

### Exporting your public key

Your key isn't much use if you don't have it in a form that you can email or put on your website.

    gpg --export --armor <email-address> > id_dsa.gpg.pub
	
This will create a text file called id_dsa.gpg.pub in the current folder that contains your publishable GPG key. You can send this over email or put it on your website and others can use it to encrypt messages before sending them to you.

### Encrypting a message

If you have a text file with somone else's public key in it, you can import their information to your keyring with 

    gpg --import <public-key>
	
where `<public-key>` is the file with the key in it. Make sure the key was successfully imported with

    gpg --list-keys
	
To encrypt a file with the new key, use

    gpg -r <email-address-of recipient> -e <name-of-file>
	
This should create a new file with the same name as the old one, but with `.gpg` appended to it. To see what the encrypted message looks like, try

    cat <encrypted-file-you-just-created.gpg>
	
which should print unreadable data to the screen, since the message has been encrypted.

### Decrypting a message

To decrypt a message that has been encrypted with your public key, simply run

    gpg -d <file-to-decrypt> > readable-message.txt
	
This will create a file called readable-message.txt in the same folder that should have the decrypted message in it.



