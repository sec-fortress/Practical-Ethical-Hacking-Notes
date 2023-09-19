## **Installation**

```powershell
# Install bloodhound and neo4j
$ sudo pip3 install bloodhound
$ sudo apt install neo4j
$ sudo apt install bloodhound
```

## **Setup**

```powershell
# setup neo4j console
$ sudo neo4j console

# In the output, Find out the remote interface navigate to it with your browser

2023-09-19 11:32:18.062+0000 INFO  Remote interface available at http://localhost:7474/
```

- [ ] Now you will be asked for a password and username, Login it with `neo4j:neo4j`
- [ ] You will then be asked to create a new password, I will be using `neo4j1`

## **Usage**

```powershell
# startup bloodhound with these terminal command
$ sudo bloodhound
```

You should be referred to the bloodhound GUI, type in you **neo4j** credentials, mine is `neo4j:neo4j1`

## **Data Collection**

Data collection are mostly done by ingestors , ingestors collect data for us remotely so we don't have to pull down data by ourself's

```powershell
# Crate a directory called bloodhound and switch to it
$ mkdir bloodhound
$ cd bloodhound

#excalidraw 
#
$ sudo bloodhound-python -d MARVEL.local -u fcastle -p Password1 -ns 192.168.0.149 -c all

```


