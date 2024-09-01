<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Verification Human</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(135deg, #f5f5f5, #e0e0e0);
            overflow: hidden;
        }

        .container {
            background-color: #ffffff;
            border-radius: 25px;
            padding: 50px;
            box-shadow: 0px 25px 70px rgba(0, 0, 0, 0.3);
            position: relative;
            z-index: 10;
            max-width: 500px;
            width: 100%;
            text-align: center;
            transform: translateY(0);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .container:hover {
            transform: translateY(-15px);
            box-shadow: 0px 35px 80px rgba(0, 0, 0, 0.4);
        }

        .container h2 {
            margin-bottom: 40px;
            color: #333;
            font-weight: bold;
            font-size: 28px;
            text-shadow: 1px 1px 5px rgba(0, 0, 0, 0.1);
        }

        .question {
            margin-bottom: 30px;
            font-size: 20px;
            color: #333;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .answer-options {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .answer-option {
            background-color: #007bff;
            color: white;
            padding: 15px 30px;
            margin: 10px 0;
            border-radius: 12px;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.2s ease, box-shadow 0.2s ease;
            font-size: 18px;
            width: 80%;
            max-width: 400px;
            text-align: center;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
        }

        .answer-option:hover {
            background-color: #0056b3;
            transform: scale(1.05);
            box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.3);
        }

        .answer-option:active {
            transform: scale(0.95);
            box-shadow: 0px 2px 6px rgba(0, 0, 0, 0.2);
        }

        .animated-svg {
            position: absolute;
            width: 600px;
            height: 600px;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 1;
            opacity: 0.2;
        }

        .animated-svg svg {
            width: 100%;
            height: 100%;
            animation: rotate 25s linear infinite;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .svg-background {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 0;
        }

        .svg-background svg {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
        }
    </style>
</head>
<body>

    <div class="svg-background">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
            <circle cx="50" cy="50" r="40" stroke="#007bff" stroke-width="10" fill="none" stroke-opacity="0.1"/>
            <circle cx="50" cy="50" r="30" stroke="#0056b3" stroke-width="10" fill="none" stroke-opacity="0.1"/>
            <circle cx="50" cy="50" r="20" stroke="#003f7f" stroke-width="10" fill="none" stroke-opacity="0.1"/>
        </svg>
    </div>

    <div class="container">
        <h2>Verification Human</h2>
        <div class="question">Apakah Anda fans Bayern Munchen?</div>
        <div class="answer-options">
            <div class="answer-option" onclick="window.location.href='gabut.html'">Iya, saya fans berat</div>
            <div class="answer-option" onclick="window.location.href='bar.html'">Tidak, saya fans Barcelona</div>
        </div>
    </div>

</body>
</html>
