# Daily Macos Terminal Issues
This article documents my daily issues and fixes to common problems I face as a t
erminal user on the macos both locally and th
rough ssh.

## Connection Closed by ip port 22.
This issue for me was weired cause I
could login using a different user. However,
my usual user could not. However, after tryi
ng many different fixes from the internet. I
decided to check if my user was admin
After discovering I was no longer ad
min because other user had removed me from ad
min group. I thought thats crazy let me fix that. So I looked for a terminal solution to d
o that. I scoured the net for solutions and q
uickly got a lovely command

```zsh
sudo dseditgroup -o edit -a john -t
user admin
```
This command add john to the admin u
ser group.
After doing this, I realised I could
 now ssh to the target host without the weire
d `Connection closed ... ` problem, and thats
 it problem fixed.
Command to list admin users `dscache
util -q group -a name admin` lovely command,
thanks to this I discovered my dilema.
