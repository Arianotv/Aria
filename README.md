<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ماشین حساب ساده</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            direction: rtl;
            text-align: center;
        }
        .container {
            margin-top: 50px;
        }
        input, button {
            padding: 10px;
            margin: 5px;
            font-size: 16px;
        }
        button {
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>ماشین حساب ساده</h1>
    <div class="container">
        <input type="number" id="num1" placeholder="عدد اول">
        <input type="number" id="num2" placeholder="عدد دوم">
        <br>
        <button onclick="calculate('+')">جمع</button>
        <button onclick="calculate('-')">تفریق</button>
        <button onclick="calculate('*')">ضرب</button>
        <button onclick="calculate('/')">تقسیم</button>
        <h2>نتیجه: <span id="result">0</span></h2>
    </div>
    <footer>
        <p>ساخته شده توسط برنامه نویس برتر آرگ</p>
    </footer>

    <script>
        function calculate(operation) {
            let num1 = parseFloat(document.getElementById('num1').value);
            let num2 = parseFloat(document.getElementById('num2').value);
            let result;

            if (isNaN(num1) || isNaN(num2)) {
                alert('لطفاً هر دو عدد را وارد کنید.');
                return;
            }

            switch (operation) {
                case '+':
                    result = num1 + num2;
                    break;
                case '-':
                    result = num1 - num2;
                    break;
                case '*':
                    result = num1 * num2;
                    break;
                case '/':
                    if (num2 === 0) {
                        alert('تقسیم بر صفر ممکن نیست!');
                        return;
                    }
                    result = num1 / num2;
                    break;
                default:
                    result = 0;
                    break;
            }

            document.getElementById('result').textContent = result;
        }

        document.addEventListener('keydown', function(event) {
            if (event.key === "Enter") {
                calculate('+');
            }
        });
    </script>
</body>
</html>
