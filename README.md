<!DOCTYPE html>
<html lang="si">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>NCC Laptops - Negombo</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
        }

        html, body {
            width: 100%;
            min-height: 100%;
        }

        body {
            color: #fff;
            line-height: 1.6;

            /* Blue background */
            background:
                radial-gradient(circle at top left, #1687ff 0%, transparent 35%),
                radial-gradient(circle at bottom right, #003b91 0%, transparent 40%),
                linear-gradient(135deg, #001f5c, #0056b3, #007bff);

            background-attachment: fixed;
            overflow-x: hidden;
        }

        /* Animated background circles */
        body::before,
        body::after {
            content: "";
            position: fixed;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: rgba(255,255,255,0.08);
            z-index: -1;
            animation: floating 8s infinite ease-in-out;
        }

        body::before {
            top: 5%;
            left: -100px;
        }

        body::after {
            bottom: 5%;
            right: -100px;
            animation-delay: 2s;
        }

        @keyframes floating {
            0%, 100% {
                transform: translateY(0) scale(1);
            }

            50% {
                transform: translateY(-40px) scale(1.1);
            }
        }

        /* Main container */
        .container {
            width: 100%;
            max-width: 1400px;
            min-height: 100vh;
            margin: auto;
            padding: 20px;
        }

        /* Header */
        header {
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;

            background: rgba(255,255,255,0.96);
            padding: 15px 30px;
            border-radius: 18px;

            box-shadow:
                0 10px 35px rgba(0,0,0,0.20);

            margin-bottom: 25px;

            animation: slideDown 0.8s ease;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .logo img {
            width: 200px;
            max-width: 100%;
            height: auto;
            display: block;
        }

        header h2 {
            color: #0056b3;
            font-size: 1.25rem;
            letter-spacing: 2px;
        }

        /* Main content */
        .main-content {
            width: 100%;
            display: grid;

            grid-template-columns:
                minmax(0, 1.25fr)
                minmax(350px, 0.75fr);

            gap: 30px;
            align-items: stretch;
        }

        /* Image */
        .image-container {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;

            animation: imageEnter 1s ease;
        }

        @keyframes imageEnter {
            from {
                opacity: 0;
                transform: scale(0.92);
            }

            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .image-container img {
            width: 100%;
            height: auto;
            max-height: 750px;

            object-fit: contain;

            border-radius: 20px;

            box-shadow:
                0 15px 40px rgba(0,0,0,0.35);

            transition:
                transform 0.5s ease,
                box-shadow 0.5s ease;
        }

        .image-container img:hover {
            transform: scale(1.02);
            box-shadow:
                0 20px 50px rgba(0,0,0,0.45);
        }

        /* Details */
        .details-container {
            width: 100%;

            background: rgba(255,255,255,0.97);
            color: #333;

            padding: 35px;
            border-radius: 20px;

            box-shadow:
                0 15px 40px rgba(0,0,0,0.25);

            display: flex;
            flex-direction: column;
            justify-content: center;

            animation: slideRight 1s ease;
        }

        @keyframes slideRight {
            from {
                opacity: 0;
                transform: translateX(40px);
            }

            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        h1 {
            color: #004494;
            font-size: clamp(1.8rem, 3vw, 2.5rem);
            margin-bottom: 10px;
        }

        .tagline {
            font-weight: 600;
            color: #555;
            margin-bottom: 22px;
        }

        /* Price */
        .price-tag {
            display: inline-block;

            background: linear-gradient(
                135deg,
                #ffcc00,
                #ffd83d
            );

            color: #000;

            font-size: clamp(1.2rem, 2vw, 1.5rem);
            font-weight: bold;

            padding: 12px 20px;
            border-radius: 10px;

            margin-bottom: 25px;

            box-shadow:
                0 5px 15px rgba(0,0,0,0.12);

            animation: pricePulse 2.5s infinite;
        }

        @keyframes pricePulse {
            0%, 100% {
                transform: scale(1);
            }

            50% {
                transform: scale(1.03);
            }
        }

        /* Features */
        ul.features {
            list-style: none;
            margin-bottom: 30px;
        }

        ul.features li {
            margin-bottom: 14px;
            padding-left: 32px;

            position: relative;

            font-size: clamp(1rem, 1.5vw, 1.1rem);
            font-weight: 500;

            opacity: 0;
            animation: featureAppear 0.6s ease forwards;
        }

        ul.features li:nth-child(1) {
            animation-delay: 0.3s;
        }

        ul.features li:nth-child(2) {
            animation-delay: 0.5s;
        }

        ul.features li:nth-child(3) {
            animation-delay: 0.7s;
        }

        @keyframes featureAppear {
            from {
                opacity: 0;
                transform: translateX(-15px);
            }

            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        ul.features li::before {
            content: "✓";

            position: absolute;
            left: 0;
            top: 0;

            width: 23px;
            height: 23px;

            display: flex;
            align-items: center;
            justify-content: center;

            background: #0056b3;
            color: white;

            border-radius: 50%;

            font-weight: bold;
        }

        /* Call button */
        .action-btn {
            width: 100%;

            border: none;
            outline: none;

            background: linear-gradient(
                135deg,
                #0056b3,
                #007bff
            );

            color: white;

            padding: 16px 25px;

            font-size: 1.1rem;
            font-weight: bold;

            border-radius: 10px;

            cursor: pointer;

            box-shadow:
                0 8px 20px rgba(0,86,179,0.35);

            transition:
                transform 0.25s ease,
                box-shadow 0.25s ease,
                background 0.25s ease;
        }

        .action-btn:hover {
            transform: translateY(-3px);

            box-shadow:
                0 12px 25px rgba(0,86,179,0.45);

            background: linear-gradient(
                135deg,
                #003d82,
                #0056b3
            );
        }

        .action-btn:active {
            transform: scale(0.97);
        }

        /* Contact information */
        #contactInfo {
            display: none;

            margin-top: 20px;
            padding: 20px;

            background: #e8f4fd;

            border-left: 5px solid #0056b3;

            border-radius: 8px;

            animation: contactAppear 0.5s ease;
        }

        @keyframes contactAppear {
            from {
                opacity: 0;
                transform: translateY(-15px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        #contactInfo p {
            margin-bottom: 8px;
            font-size: 1rem;
        }

        #contactInfo a {
            color: #0056b3;
            text-decoration: none;
            font-weight: bold;
        }

        /* =========================================
           TABLET
        ========================================= */

        @media (max-width: 900px) {

            .container {
                padding: 15px;
            }

            .main-content {
                grid-template-columns: 1fr;
            }

            .image-container img {
                max-height: none;
            }

            .details-container {
                padding: 30px;
            }
        }

        /* =========================================
           MOBILE
        ========================================= */

        @media (max-width: 600px) {

            body {
                background:
                    linear-gradient(
                        160deg,
                        #001b50,
                        #0056b3,
                        #008cff
                    );
            }

            .container {
                width: 100%;
                min-height: 100vh;
                padding: 10px;
            }

            header {
                width: 100%;

                flex-direction: column;
                justify-content: center;

                text-align: center;

                padding: 15px;

                border-radius: 15px;

                gap: 8px;
            }

            .logo img {
                width: 170px;
            }

            header h2 {
                font-size: 1rem;
            }

            .main-content {
                width: 100%;
                display: flex;
                flex-direction: column;

                gap: 15px;
            }

            .image-container {
                width: 100%;
            }

            .image-container img {
                width: 100%;
                max-width: 100%;
                height: auto;

                border-radius: 15px;
            }

            .details-container {
                width: 100%;
                padding: 22px;

                border-radius: 15px;
            }

            h1 {
                font-size: 1.7rem;
            }

            .tagline {
                font-size: 0.95rem;
            }

            .price-tag {
                width: 100%;
                text-align: center;

                font-size: 1.2rem;
            }

            ul.features li {
                font-size: 1rem;
            }

            .action-btn {
                font-size: 1rem;
                padding: 15px;
            }
        }

        /* Very small phones */
        @media (max-width: 380px) {

            .container {
                padding: 7px;
            }

            header {
                padding: 12px;
            }

            .details-container {
                padding: 18px;
            }

            h1 {
                font-size: 1.5rem;
            }

            .price-tag {
                font-size: 1.05rem;
            }
        }
    </style>
</head>

<body>

    <div class="container">

        <!-- HEADER -->
        <header>

            <div class="logo">
                <img
                    src="https://via.placeholder.com/200x80/ffffff/0056b3?text=NCC+Logo"
                    alt="NCC Company Logo"
                >
            </div>

            <div>
                <h2>The Smart Choice</h2>
            </div>

        </header>


        <!-- MAIN -->
        <main class="main-content">

            <!-- LAPTOP IMAGE -->
            <section class="image-container">

                <img
                    src="1001863365.jpg"
                    alt="NCC Used and Refurbished Laptops Promo"
                >

            </section>


            <!-- DETAILS -->
            <section class="details-container">

                <h1>High-Quality Laptops</h1>

                <p class="tagline">
                    Used | Refurbished -
                    Imported from Australia, USA, Canada
                </p>


                <div class="price-tag">
                    Prices Starting From 30,000/-
                </div>


                <ul class="features">

                    <li>
                        DELL | HP | LENOVO | ACER
                    </li>

                    <li>
                        6 Months Warranty
                    </li>

                    <li>
                        පහසු ගෙවීමේ ක්‍රමයට ලබා ගත හැක
                    </li>

                </ul>


                <!-- CALL BUTTON -->
                <button
                    class="action-btn"
                    onclick="makeCall()"
                >
                    📞 Contact Us / විස්තර දැනගන්න
                </button>


                <!-- CONTACT INFO -->
                <div id="contactInfo">

                    <p>
                        📞
                        <strong>Phone:</strong>
                        <a href="tel:0703591371">
                          070 35 91 371
                        </a>
                    </p>

                    <p>
                        📍
                        <strong>Office:</strong>
                        No: 198, St. Joseph's Street, Negombo
                    </p>

                </div>

            </section>

        </main>

    </div>


    <script>

        function makeCall() {

            /*
             * Mobile phone 
             * Call/Dial application 
             */
            window.location.href = "tel:+94703591371";

            /*
             * Contact information 
             */
            var infoBox =
                document.getElementById("contactInfo");

            infoBox.style.display = "block";

        }

    </script>

</body>
</html>
