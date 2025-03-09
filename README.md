<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>طلب المعجنات</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            direction: rtl;
            text-align: right;
            background-color: #f7f7f7;
            padding: 20px;
        }
        .container {
            background-color: white;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h2 {
            color: #333;
        }
        label {
            font-size: 16px;
            margin-top: 10px;
        }
        input, select, textarea {
            width: 100%;
            padding: 8px;
            margin-top: 5px;
            margin-bottom: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>

    <div class="container">
        <h2>طلب معجنات</h2>
        <form id="orderForm">
            <label for="name">الاسم:</label>
            <input type="text" id="name" required>

            <label for="phone">رقم الهاتف:</label>
            <input type="tel" id="phone" required>

            <label for="quantity">كمية المعجنات (بالكيلو):</label>
            <input type="number" id="quantity" required>

            <label for="pastryType">نوع الكعك:</label>
            <select id="pastryType" required>
                <option value="كعك عيد بتمر">كعك عيد بتمر</option>
                <option value="كعك عيد براحه">كعك عيد براحه</option>
                <option value="كعك لف">كعك لف</option>
                <option value="مقروطه تمر">مقروطه تمر</option>
                <option value="مقروطه كاكاو">مقروطه كاكاو</option>
                <option value="معمول">معمول</option>
                <option value="كراكيش">كراكيش</option>
            </select>

            <label for="notes">ملاحظات (اختياري):</label>
            <textarea id="notes"></textarea>

            <button type="submit">إرسال الطلب</button>
        </form>
    </div>

    <script>
        document.getElementById('orderForm').addEventListener('submit', function(event) {
            event.preventDefault(); // منع إرسال النموذج بشكل افتراضي

            const name = document.getElementById('name').value;
            const phone = document.getElementById('phone').value;
            const quantity = document.getElementById('quantity').value;
            const pastryType = document.getElementById('pastryType').value;
            const notes = document.getElementById('notes').value;

            const orderSummary = `
                <h3>تفاصيل الطلب:</h3>
                <p><strong>الاسم:</strong> ${name}</p>
                <p><strong>رقم الهاتف:</strong> ${phone}</p>
                <p><strong>كمية المعجنات:</strong> ${quantity} كيلو</p>
                <p><strong>نوع الكعك:</strong> ${pastryType}</p>
                <p><strong>ملاحظات:</strong> ${notes || 'لا توجد ملاحظات'}</p>
            `;
            
            // يمكن عرض التفاصيل في صفحة جديدة أو إرسالها عبر البريد الإلكتروني
            alert(orderSummary); // لعرض التفاصيل للمستخدم
        });
    </script>

</body>
</html>
