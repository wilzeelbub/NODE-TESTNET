# INTRUCTIONS

# Update Binary
```
sudo apt update 
sudo apt install snapd -y 
sudo snap install lz4 
sudo systemctl stop
```

# Stop the service and reset the data
```
sudo systemctl stop nolusd
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
rm -rf $HOME/.nolus/data
```

# Download Latest Snapshot
```
wget -O wget -O nolus-snapshot-20230303.tar.lz4 https://snapshot.nolus.wilzeelbub.xyz/nolus/nolus-snapshot-20230303.tar.lz4 --inet4-only
```

# Restart Service
```
sudo systemctl restart nolusd
```

# Check Log

```
sudo journalctl -u nolusd -f --no-hostname -o cat
```
