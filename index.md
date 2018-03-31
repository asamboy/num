<html>
	<head>
	<title>Números</title>
  	<meta charset="utf-8" />
		<script src="https://code.jquery.com/jquery-1.10.2.js"></script>
		<link href='http://fonts.googleapis.com/css?family=Roboto:100,300,700,400' rel='stylesheet' type='text/css'>
  	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		
		<style type="text/css">
			* {
				margin:0;
				padding:0;
				font-family: "Roboto", sans-serif;
				text-align: center;
				font-size: 1.6em;
			}

			body {
				background: #ecf0f1;
			}

			h1 {
				margin-top: 1em;
				color:#2c3e50;
				font-size: 1em;
			}

			#container {
				position: relative;
				margin: 5% auto;
				width: 3.8em;
				height: 5.7em;
			}

			.first {
				display: block;
				color:;
			}

			.second {
				float: left;
			}

			.fourth {
				float: right;
			}

			.fifth {
				position: absolute;
				left:0;
				bottom: 0;
			}

			.sixth {
				position: absolute;
				right:0;
				bottom: 0;
			}

			p {
				margin-top: 1.8em;
				font-size: .3em;
				font-weight: 300;
				color:#7f8c8d;
				font-weight: 100;
			}

		</style>	
	</head>

	<body>
		<h1></h1>
		<div id="container">
			<span class="first">1</span>
			<span class="second">2</span>
			<span class="third">3</span>
			<span class="fourth">4</span>
			<span class="fifth">5</span>
			<span class="sixth">6</span>
		</div>
		<div><p>versión 2.0</p></div>

		<script>
			var array = [];
			var colorarray = ["#e74c3c","#3498db","#2ecc71","#f1c40f"];
			var today = new Date();
			var year = today.getFullYear().toString();
			var seed = today.getDate() * (Math.log((today.getMonth()+1)/Math.PI)/Math.LN10) * year;
			var c;
			
			$(document).ready(function(){ 

				$("h1").text("Números para el "+today.getDate()+"/"+(today.getMonth()+1)+"/"+today.getFullYear().toString().substr(2, 3));

				array[0] = parseInt((263498670*seed+"").substr(7,1));
				array[1] = parseInt((453700780*seed+"").substr(7,1));
				array[2] = parseInt((734616753*seed+"").substr(7,1));
				array[3] = parseInt((898788267*seed+"").substr(7,1));
				array[4] = parseInt((911921799*seed+"").substr(7,1));
				array[5] = parseInt((526678639*seed+"").substr(7,1));

				loop1:
				for (var i = 1; i < array.length; i++) {
					for (var k = (i-1); k >= -1; k--) {
						if (array[i] === array[k]) {
							array[i]--;
							if (array[i] < 0) {
								array[i] = 9;
							}
							i--; 
							continue loop1;
						}
					}		
				}

				$(".first").text(array[0]);
				$(".second").text(array[1]);
				$(".third").text(array[2]);
				$(".fourth").text(array[3]);
				$(".fifth").text(array[4]);
				$(".sixth").text(array[5]);

				if (today.getDate()%2===0) {

					if (array[0] > 4) {
						c = 0;
					} else {
						c = 2;
					}
					$(".first").css("color",colorarray[c]);

					if (array[1] > 4) {
						c = 1;
					} else {
						c = 3;
					}
					$(".second").css("color",colorarray[c]);

					if (array[2] > 4) {
						c = 3;
					} else {
						c = 0;
					}
					$(".third").css("color",colorarray[c]);

					if (array[3] > 4) {
						c = 2;
					} else {
						c = 1;
					}
					$(".fourth").css("color",colorarray[c]);

					if (array[4] > 4) {
						c = 1;
					} else {
						c = 0;
					}
					$(".fifth").css("color",colorarray[c]);

					if (array[5] > 4) {
						c = 2;
					} else {
						c = 3;
					}
					$(".sixth").css("color",colorarray[c]);

				} else {

					if (array[0] > 4) {
						c = 1;
					} else {
						c = 3;
					}
					$(".first").css("color",colorarray[c]);

					if (array[1] > 4) {
						c = 0;
					} else {
						c = 2;
					}
					$(".second").css("color",colorarray[c]);

					if (array[2] > 4) {
						c = 2;
					} else {
						c = 1;
					}
					$(".third").css("color",colorarray[c]);

					if (array[3] > 4) {
						c = 3;
					} else {
						c = 0;
					}
					$(".fourth").css("color",colorarray[c]);

					if (array[4] > 4) {
						c = 2;
					} else {
						c = 3;
					}
					$(".fifth").css("color",colorarray[c]);

					if (array[5] > 4) {
						c = 0;
					} else {
						c = 1;
					}
					$(".sixth").css("color",colorarray[c]);
				} 

			});

		  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
		  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
		  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
		  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

		  ga('create', 'UA-63065921-1', 'auto');
		  ga('send', 'pageview');

		</script>
	</body>
</html>
