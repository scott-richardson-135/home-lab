# Very Basic UFW setup
More to come maybe

## Installing UFW
To install UFW, run:
```sudo apt install ufw```

Easy as pie

## Setting my rules and enabling firewall
I don't have much to allow yet, so i just ran this command with the few services I need right now:

```sudo ufw allow 2222 # SSH custom port```

```sudo ufw allow 80 # NGINX```

Then to enable the firewall:

```sudo ufw enable```

## Rules on my server
To view rules, run: 
```sudo ufw status```

Current rules are listed in [ufw-rules.txt](https://github.com/scott-richardson-135/home-lab/blob/main/security-baseline/ufw-rules.txt)

