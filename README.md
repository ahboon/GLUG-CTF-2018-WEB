## Inspection
```
Head over to the link below to find the flag.
https://expect-glugctf.netlify.com/
```
This is a typical HTML source code viewing flag. CTRL+U will give you the flag. ``<div><!--The flag is GLUG{3el(0me_1o_$h3_N3xT_7eve7}--></div>``


## Go Get It!
```
Head over to the link below to find the flag.
http://104.248.49.223:7070/

Source code:
<!DOCTYPE html>
<html>
<head>
    <title>Flag!Flag!Flag!</title>
    <link rel="stylesheet" href="css/main.css">
</head>
<body>
    <div class='contain-flag'>
      <div class='pole'></div>
      <div class='flag'></div>
      <div class='shadow'></div>
      <div class='flag flag-2'></div>
    </div>
    <div>
        <center>
        <h3>This is just a decoy of the FLAG!</h3>
        <small>If you ask nicely, maybe i will give it to you.</small>
        <small>View Source of this page <a href="https://pastebin.com/LvfdATxz" target="_blank">Here</a></small>
        </center>
    </div>
    <pre><?php
    $flag = #REDACTED
 
    if(array_key_exists("flag", $_GET)) {
        if($_GET["flag"] === "true"){
        echo $flag;
        }
    }
    ?>
    </pre>
</body>
</html>
```
This is a challenge which expects a GET request with the variable 'flag', and its value equals to 'true'. Therefore, the solve for this is http://104.248.49.223:7070/?flag=true. ``GLUG{4lw4y5_fuzz_f0r_h1dd3n_p4r4m373r5}	``


## Rotten
```
Head over to the link below to find the flag.
https://rotplayer-glugctf.netlify.com/

Source Code:

<!DOCTYPE Html />
<html>
 <head>
 <meta charset="utf-8">
 <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
 <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
 <style type="text/css">
 .ins {
  padding:auto;
  margin:5rem auto 0 auto;
  text-align:center;
 }
 .btn {
  padding:auto;
  margin:1rem;
 }
 </style>
 <title>Rot Player</title>
 </head>
 <body>
<div class="container text-center">
 <h2>Rot Player</h2><small>Entry Point</small>
 <div class="container ins">
	 <input type="text" name="flag" id="flag" placeholder="Enter the flag" /><br>
	 <button class="btn btn-primary" id="check" >Login with Flag!</button>
 </div>
</div>

 <script type="text/javascript">
 document.getElementById("check").onclick = function () {
 var flag = document.getElementById("flag").value;
 var rotFlag = flag.replace(/[a-zA-Z]/g, function(c){
 return String.fromCharCode((c <= "Z" ? 90 : 122) >= (c = c.charCodeAt(0) + 13) ? c : c - 26);});
 if ("TYHT{py13a7_51q3_y061a_j17u_e0713!}" == rotFlag) {
 alert("Correct flag!");
 } else {
 alert("Incorrect flag, rot again");
 }
 }
 </script>

 </body>
</html>
```

This is a challenge which has a the flag hardcoded in its javascript. However, it is ROT13-ed and therefore you are required to provide the CORRECT flag to 'match' the logic. Putting the matching condition from the source code into cyberchef (google it), will give you the flag. ``GLUG{cl13n7_51d3_l061n_w17h_r0713!}``

## The Videogame
```
One fine day,Rocket Raccoon found the video game that Groot was so obsessed with.Unfortunately,Groot had set a password on it. In the password hint,he had provided link to a website. Raccoon could not find anything in the website. Can you help him find it, so that he can play the videogame?

http://104.248.49.223:7071/
```
This is a challenge which required the user to change the cookie. Examining to cookie, it shows ``user:unknown``. Changing it to ``user:ROOT`` and reloading the page will give us the flag. ``GLUG{I_@m_7r55t}``


## Referals
```
Misha recently got placed at Google.So she started refering her friends for incoming job posts in the company.She hid a secret in this website for those who got the job after her referal.The secret contains the place where she and her friends will be having party for their new jobs.

Minan is Misha's boyfriend.Minan wants to reach Misha asap.Since Minan didnt get a job at google and is a noob,Can you help him figure out the location?

http://104.248.49.223:8081/
```
This challenge requires us to craft a HTTP header with referer = https://www.google.com in it. Simply do a CURL request with ``--referer https://www.google.com`` in the curl request to the site and flag will be give. ``GLUG{Refendrum_@_007}``


## MI7
```
Olny Agents are allowed.

MI7 Members Secret Vault

https://mi7secret-glugctf.netlify.com/

MI7 was a department in the British Directorate of Military Intelligence in both the First and Second World War. The group, which was part of British Military Intelligence, was established to control propaganda and censorship. It was part of the War Office.



Even Google is allowed to see our secrets. You are not an agent! How dare you, to be here !!
```

So at first, this challenge looked like a user-agent challenge. But reading the last line, tells us otherwise. Google bots are used to crawl the internet for site indexing, and ``robots.txt`` might be the place we should be looking at.

Visiting ``https://mi7secret-glugctf.netlify.com/robots.txt`` will show us a list of URLs.

```
User-agent: *
Disallow: /cyberworld/map/
Disallow: /tmp/
Disallow: /fsck.bf
Disallow: /a7_vault.html
Disallow: /exploits/fuzzbunch/Eternal_pink
Disallow: /exploits/network/QuantumInjection.pdf
```
Following the URL ``https://mi7secret-glugctf.netlify.com/a7_vault.html`` will give us a BASE64 encoded string: ``R0xVR3tiMDc1X2M0bl8xNm4wcjNfN2gzX3J1bDM1fQ==``, subsequently, decoding it will give us a flag. ``GLUG{b075_c4n_16n0r3_7h3_rul35}``


## Musically
```
We can have a list of songs.And a search input where a user can search for a song along with details.
Link to the Challenge
http://142.93.207.206:7004/

Link to the source code
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css">
    <link rel="stylesheet" href="master.css">
    <title>ctf</title>
  </head>
  <body>
    <div class="wrap">
      <form method="post" class="search">
        <input type="text" class="searchTerm" placeholder="Enter a filter.." name=needle>
              <button type="submit" class="searchButton" name=submi>
                <i class="fa fa-search"></i>
             </button>
           </form>

      <div class="output">
        <h6>Here are top reccommendations:</h6>
        <pre><?php
        $key = ".";

        if(array_key_exists("needle", $_REQUEST)) {
            $key = $_REQUEST["needle"];
        }

        if($key != "") {
        passthru("grep -i $key songs.txt");
        }
        ?>
        </pre>
      </div>
</div>
  </body>
</html>
```
This is a typical command injection challenge. There are not filters, and therefore command injection can be done directly. Supplying ``;ls;`` will allow us to list files. Since ``flag.txt`` is in the same directory, doing a ``;cat flag.txt;`` will allow us to read the flag. Therefore, the flag is: ``GLUG{you_never_gonna_find_song}``


## New Blogger
```
Misha is a travel blogger.She made a website for her blog.Minan was very impressed with it but on detailed inspection found that there existed a vulnerability.
Can you find the flag exploiting the same?

Hint: Flag is in /etc/flag

Link
http://104.248.49.223:7074/
```
This challenge is a Local File Inclusion (LFI) challenge. The LFi was identified when playing around with the links in the site. Clicking on ``About Us`` will load ``About Us`` page. But looking at the URL, ``http://104.248.49.223:7074/?page=about-us.php`` was seen, and changing it to ``http://104.248.49.223:7074/?page=../../../../../../../../etc/flag`` gives us the flag. ``GLUG{7h3_54m3_0ld_f1l3_1nclu510n}``


## NinjaGirl
```
NInJa_gIrl thinks MD5 is amazing.She uses one salt to hash all her data. All you need to do is enter two different names and prove her that she’s wrong?
Link to the Challenge
http://104.248.49.223:7075/

Here is the source code: link
https://ghostbin.com/paste/seah6
Flag is in format: Glug{}

<?php
  include 'secret.php';
  if($_GET["str1"] and $_GET["str2"]) {
    if ($_GET["str1"] !== $_GET["str2"] and
        hash("md5", $salt . $_GET["str1"]) === hash("md5", $salt . $_GET["str2"])) {
      echo $flag;
    } else {
      echo "Sorry, you're wrong.";
    }
    exit();
  }
?>

<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CTF</title>
    <link href="https://fonts.googleapis.com/css?family=Audiowide" rel="stylesheet">
    <style media="screen">
      body{
        font-family: 'Audiowide', cursive;
        background-color: #ff4;
        padding: auto;
        text-align: center;
      }
      input{
        margin:1rem;
      }
    </style>
  </head>
  <body>
    <h1>
      Ninja Girl welcomes you.<br>
    </h1>
    <h3>Please enter your and your opponent's name.</h3>
    <form method="GET">
      Fighter 1: <input type="text" name="str1">
      <br>
      Fighter 2: <input type="text" name="str2">
      <br>
      <input type="submit" value="submit">
    </form>
    <img src="ninja.png" alt="" height="300px" width="300px">
  </body>
</html>
```
This is basically a challenge where you are required to overcome the code logic. To match the logics, we would need to supply the GET parameters with arrays. Because when PHP converts and array into string, it would be ``Array`` instead of the values in it. Therefore, a literal conversion with the salt would still give the same hashes. The following code snippet can be run and you would see ``testArray`` as the eventual text, even though both have different values.

```
<?php
/* Write your PHP code here */
$A = [1];
$B = [2];
echo "test" . $A;
# PHP Notice: Array to string conversion in index.php 5
# testArray <-- from $A
echo "test" . $B;
# PHP Notice: Array to string conversion in index.php 7
# testArray <-- from $B

?>
```
Therefore, the solve for this would be ``?str1[]=1&str2[]=2``, giving us the flag ``Glug{7i5e_1s_####123_7577}``.

## The Infinity War
```
Thanos has acquired half of the gems and soon coming on the earth for the Time stone.All the marvel heroes have therfore united to fight with him.
But as they needed one person to lead them,they organised an election to choose one leader.
But since Loki received least number of votes. He got jealous and mixed up the votes,and hid the result.
Can you find it?
This link will lead you to the vote counts.
http://167.99.149.173/
Flag is in the format Glug{}
```

This is a typical SQL injection question. Requiring the user to do a UNION SELECT injection. The payload required is ``' UNION SELECT IhidItHere,2,3,4 FROM Leaders;##``, giving us the flag ``Glug{3@st_!r0nm@n_1s_3est}``



## Pingmaster
```
Phonix made a new tool called “Pingmaster”. He hosted it in his server, as he is a poor person and couldn’t afford multiple servers he also kept his secret in it. But he thinks it really secure.
Prove him wrong.
Link to the challenge
http://104.248.49.223:7090/
Tip: Flag is in /etc/flag
```
This is yet another command injection challenge, but there are filters. Giving symbols like ``&``,``SPACE``, or ``|`` would trigger the filter. However, since the commands are executed and the standard output is then printed, we can trying the ``%0A`` method. ``%0A`` would add a new line, like a press of the ENTER key. Since ``SPACE`` is not allowed, we will have to use ``$IFS$9`` to insert spaces. But for this to work, instead of sending it through the form, we will have to send the GET request directly to prevent our symbols from be encoded. Therefore, the payload for the command would be ``http://104.248.49.223:7090/?host=%0Acat$IFS$9/etc/flag``, and the flag is ``GLUG{c40mm4nd_1nj3c710n_w17h0u7_5c4p35_15_l337}``.


THATS ALL FOLKS! I LOVE WEB!
