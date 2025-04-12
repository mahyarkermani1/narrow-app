
# narrow-app
Application to understand narrow recon

# update
This repo is a fork from [**HERE**](https://github.com/Voorivex/narrow-app), and the main goal is to discover hidden resources like files, paths, parameters, etc and I worked on this app like a normal user to discover these type of resources ( without looking to the source code ).

I discover this list of resources and I share them here:

 1. Foundable ( visible resources ):

```
    http://127.0.0.1:5000/users
    http://127.0.0.1:5000/contact?action=contact
    http://127.0.0.1:5000/contact
    http://127.0.0.1:5000/intro?mode=play&user=1&url=https://google.com
```

2. in javascript sources:

```
    endpoint: http://127.0.0.1:5000/api/user/:username (user1, user2, user3)
```

3. Tool: Param Miner : ffuf : discover hidden headers

```
    Param Miner: x-requested-with: test ( status-code 500 )
    Fuff: ffuf -w /home/mahyar/Documents/headers_1218.txt -u http://192.168.43.90:5000/ -mc all -H "FUZZ: test" -fs 494 : x-requested-with        [Status: 500, Size: 265, Words: 33, Lines: 6, Duration: 94ms]
```

4. Tool : ffuf : hidden js file

```
    ffuf -u http://192.168.43.90:5000/static/FUZZ -w '/home/mahyar/Documents/js-medium_173652.txt'  -mc all -fs 207 : admins.js
```
