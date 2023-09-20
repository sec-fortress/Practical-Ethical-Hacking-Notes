## **Installation**

```powershell
# install plumhound on your Kali machine
$ cd /opt
$ sudo git clone https://github.com/PlumHound/PlumHound.git
$ cd PlumHound
$ sudo pip install -r requirements.txt
```


## **Usage**

**Note :** You need to have your bloodhound and neo4j console up and running, because it will pull information from both for analysis

```powershell
# show help message
$ sudo python3 PlumHound.py --help

# query the domain
$ sudo python3 PlumHound.py --easy -p neo4j1

# Run default tasks
$ sudo python3 PlumHound.py -x tasks/default.tasks -p neo4j1 
```

Now we can change our directory to `reports` then open the `index.html` with **Firefox** for a better view.

