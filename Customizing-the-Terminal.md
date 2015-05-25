###Getting rid of need to add sudo to certain commands
type this into your terminal to own the directory you want to be able to avoid having to type sudo in, replacing `your_username` with your actual username and `directory` with that directory name:

    sudo chown your_username directory 

For example, to apply this to your home directory (the top-level folder on your computer), you'd use `~` for `directory`.