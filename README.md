<!doctype html>

<html lang="en">

<head>

<meta charset="utf-8">

<title>jQuery Slideshow</title>
<link href="styles.css" rel="stylesheet" />
</head>

<body>
            <div id="slideshow"
                 <img class="slide" src="images/lakeview.jpg" />
                 <img class="slide" src="images/landscape.jpg" />
                 <img class="slide" src="images/mountain.jpg" />
                  <img class="slide" src="images/natural grass.jpg"/>
                 <img class="slide" src="images/outdoor.jpg" />
                 <img class="slide" src="images/sunshine.jpg"/>

            </div>
    <script src="jquery-3.6.0.min.js"></script>
    <script>
        $(document).ready(function () {
            var slideshow = (function () {
                var counter = 0,
                    i,
                    j,
                    slides = $("#slideshow .slide"),
                    slidesLen = slides.length - 1;
                for (i = 0, j = 9999; i < slides.length; i += 1, j -= 1) {
                    $(slides[i]).css("z-index", j);
                }
                return {
                    startSlideshow: function () {
                        window.setInterval(function () {
                            if (counter === 0) {
                                slides.eq(counter).fadeOut();
                                counter += 1;
                            } else if (counter === slidesLen) {
                                counter = 0;
                                slides.eq(counter).fadeIn(function () {
                                    slides.fadeIn();
                                });
                            } else {
                                slides.eq(counter).fadeOut();
                                counter += 1;
                            }
                        }, 2000);
                    }
                };
            }());
            slideshow.startSlideshow();
        }(jQuery));

            

    </script>



</body>

</html>

