<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine's Proposal</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <style>
        body {
            background-color: pink;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            position: relative;
        }
        h1 {
            color: purple;
            margin-bottom: 20px;
            font-size: 2rem;
            position: relative;
            z-index: 2;
        }
        .button-container {
            display: flex;
            gap: 20px;
            z-index: 2;
            position: relative;
        }
        .but {
            background-color: rgb(79, 229, 79);
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
            border-radius: 10px;
            position: relative;
        }
        #button2 {
            background-color: rgb(235, 73, 73);
        }
        .gif-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .gif-container img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            opacity: 0.8;
        }
    </style>
</head>
<body>
    <div class="gif-container">
        <img src="https://media4.giphy.com/media/KztT2c4u8mYYUiMKdJ/giphy.gif?cid=6c09b9522z9olj7pdqv4xkm8ofqncomohvx10pbslsfg545m&ep=v1_gifs_search&rid=giphy.gif&ct=g" alt="Valentine's GIF">
    </div>
    <h1>Will You Be My Valentine??</h1>
    <div class="button-container">
        <button class="but" id="button1">Yes</button>
        <button class="but" id="button2">No</button>
    </div>

    <script>
        $(document).ready(function() {
            var messages = [
                "Please be My Valentine 😖",
                "Pretty please? 🥺",
                "I'm getting sad... 😢",
                "Why not? 😔",
                "Last chance! 💔"
            ];
            var clickCount = 0;

            $('#button2').on('click', function() {
                if (clickCount < messages.length) {
                    $('h1').text(messages[clickCount]);
                } else {
                    $('h1').text("No more chances... 😞");
                }

                var currentWidth = $('#button1').outerWidth();
                var newWidth = currentWidth * 1.3;

                $('#button1').css({
                    width: newWidth,
                    fontSize: '+=4px'
                });

                clickCount++;
            });

            $('#button1').on('click', function() {
                $('h1').text("Yay! Love you so much! 💞");
                $('.button-container').hide();
            });
        });
    </script>
</body>
</html>


