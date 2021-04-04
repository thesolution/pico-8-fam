# pico-8-fam
This is a family repo where I'm documenting and publishing work my kids are doing to learn to program. Shout out to Hunter M for indroducing me to the [pico-8](https://www.lexaloffle.com/pico-8.php).

# project organization
We're using Dropbox free tier to share and sync a workspace.  Folder for each member, symlink to the app data directories on each computer.

> The default location for PICO-8's drive is:
>
>	Windows: C:/Users/Yourname/AppData/Roaming/pico-8/carts
>	OSX: /Users/Yourname/Library/Application Support/pico-8/carts
>	Linux: ~/.lexaloffle/pico-8/carts
From the [pico-8 manual](https://www.lexaloffle.com/pico8_manual.txt)

Initially linked each kids folder by name but now I think I'll just do a link to the repo in the carts directory.

    # macos
    cd ~/Library/Application\ Support/pico-8/carts/
    ln -s ~/Dropbox/dropbox/pico-8-fam pico-8-fam

    # windows
    cd ~\AppData\Roaming\pico-8\carts
    mklink /D pico-8-fam ~\Dropbox\pico-8-fam

Once we can all share code it's up to the adult supervisor to do a quick security check before exporting, commiting and pushing the updates.  On a raspberry pi 4 running nginx i have `/etc/nginx/sites-available/default` pointed to a clone of this repo located in `/var/www/html/pico-8-fam`.  I should probably come up with a more secure config, but there's nothing else on the server yet.

## exporting for the web
TODO: script this.

launch pico-8, navigate to each directory, in the pico-8 shell `load \<cart name\>.pb`, execute the cart with `run`, hit `F2` to capture a [thumbnail or "label"](https://www.reddit.com/r/pico8/comments/fdk79r/cant_export/), finally `export \<cart name\>.html` saves an html and js file for the program.

## review commit push
Once the carts are good, add and commit all changes and push to github.

## publish updates
On the raspberry pi I'm working out the kinks so for now I'm just ssh-ing in and doing a `git pull` to update the site with the latest code!

I would have killed for the ability to do this on my used 386SX 33mhz in the 1990s