Start with a command-line Ubuntu install

Install openssh-server and python
Remove nano (because it's not vi)

Create an ansible account with sudo w/o password rights.

(meaning add the following line to the sudoers file:
ansible ALL=(ALL) NOPASSWD:ALL
)

perform an ssh-copy-id of your public key to the target ansible user's account

Add the new system's ip address to your /etc/ansible/hosts file

ansible-playbook -vvvv site.yml --limit <target system's ip>

Once the system is ready, we need to make sure the sound is working.

Open a terminal and run:

amixer sset Master unmute
amixer sset Master 100%
amixer sset Master 75%
aplay /usr/share/sounds/alsa/Front_Center.wav

Also, add normal users to the audio group so they can play sounds.
