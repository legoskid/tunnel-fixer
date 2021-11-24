#tunnel-fixer
This is a fork of the original tunnel-fixer.
##Q&A
>Why?
The last commit on the original was April 23, and doesn't work anymore.
>You are going to get banned!
As long as you don't abuse it, you won't.
>Why doesn't the thing doesn't let me join VMs?
You accessed collabvm.html directly. Set it up properly.
##How to use
1. Go onto CollabVM
2. Install a CORS extension because you won't fix it yourself (i use https://addons.mozilla.org/en-US/firefox/addon/moesif-origin-cors-changer1/)
3. Clone the repository
4. Host the repository on any port, you don't have to port forward (simply: put it on a webserver)
5. Go into Inspect Element, go into the Console and put in this script. Run it. That's it.
```js
if(location.host == "ontheotherside.cyou"){
location.href = "http://computernewb.com/collab-vm"
}
else{
for(var i =0; i<=5; i++){document.open();document.close();}

var xhttp = new XMLHttpRequest();
xhttp.open('GET', "http://localhost:port/collabvm.html")
xhttp.onreadystatechange = function () {
    if (xhttp.readyState == XMLHttpRequest.DONE) {
        document.open();
        document.write(xhttp.responseText);
        document.close();
    }
}
xhttp.send()}```