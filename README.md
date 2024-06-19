# shh_gen


ssh-keygen -t ed25519 -f ~/.ssh/id_ed25519

eval "$(ssh-agent -s)" 


ssh-add ~/.ssh/id_ed25519

eval "$(ssh-agent -s)" 

cat ~/.ssh/id_ed25519.pub

//then go to github and paste the 
