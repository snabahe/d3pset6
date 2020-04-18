
<html lang="en">
	<head>
		<meta charset="utf-8">
		<title>D3 PSET</title>
		<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/4.7.4/d3.js"></script>
		<link href="https://fonts.googleapis.com/css?family=Open+Sans:300" rel="stylesheet">
		<style type="text/css">

				.titlestyling {
						position: absolute;
						left: 10px;
						font: "Arial";
						font-size: 20px;
				}
				.textstyling {
						font: "Arial";
						font-size :14px;
				}

		</style>
		</head>
		<body>


		<div id="main">

		</div>
		<script type="text/javascript">
			var width = 1200;
			var height = 1000;

			agriculturedata = [["Brazil", 33.9],["Canada", 6.9],["Costa Rica", 34.5],["Denmark", 62],["Fiji", 23.3],["France", 52.4],["Greenland", .6],["Italy", 43.2],["Mali",33.8],["Netherlands",53.3]];

			var svg = d3.select("div#main")
						.append("svg")
						.attr("width", width)
						.attr("height", height);

			svg.selectAll("rect")
               .data(agriculturedata)
               .enter()
               .append("rect")
               .attr("y", function(d, i) {
                       return i*30*2 + 80;
                  })
               .attr("x", 160)
               .attr("width", function(d) {
                       return d[1]*2*2;
                  })
          	   .attr("height", 20*2)
							 .attr("fill-opacity", .7)
               .attr("fill", "green")

			 svg.append("line")
							 	.attr("x1", 160)
							 	.attr("y1", 70)
							 	.attr("x2", 160)
							 	.attr("y2", 670)
							 	.attr("stroke-width", 2)
							 	.attr("stroke", "black");

 //create title
			svg.append("text")
							 	.attr("x", 300)
							 	.attr("y", 50)
							 	.attr("text-anchor", "right-align")
							 	.attr("class", "titlestyling")
							 	.text("Agricultural Land By Countries")

//create data labels
for (var p=0; p<agriculturedata.length; p++)
		{
			svg.append("text")
								.text(agriculturedata[p][0])
								.attr("class", "text-styling")
								.attr("text-achor", 'start')
								.attr("y", p*60+100)
								.attr("x",70)
		}




		</script>
		</div>
	</body>
</html>
