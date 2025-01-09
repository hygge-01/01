<!DOCTYPE html>
    <html lang="zh-Hant">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>每日氧氣用量記錄</title>
        <script src="https://cdn.tailwindcss.com"></script>
        <style>
            body {
                font-family: Arial, sans-serif;
            }
        </style>
    </head>
    <body class="bg-gray-100 p-6">
        <h1 class="text-2xl font-bold mb-4">每日氧氣用量記錄</h1>
        <div class="mb-4">
            <input type="text" id="userName" placeholder="用戶姓名" class="border p-2 mr-2">
            <input type="number" id="oxygenAmount" placeholder="氧氣用量" class="border p-2 mr-2">
            <select id="month" class="border p-2 mr-2">
                <option value="">月份</option>
                <option value="1">1月</option>
                <option value="2">2月</option>
                <option value="3">3月</option>
                <option value="4">4月</option>
                <option value="5">5月</option>
                <option value="6">6月</option>
                <option value="7">7月</option>
                <option value="8">8月</option>
                <option value="9">9月</option>
                <option value="10">10月</option>
                <option value="11">11月</option>
                <option value="12">12月</option>
            </select>
            <input type="number" id="day" placeholder="日期" class="border p-2 mr-2" min="1" max="31">
            <button onclick="addRecord()" class="bg-blue-500 text-white p-2">新增紀錄</button>
        </div>
        <table class="min-w-full bg-white border border-gray-300 mb-4">
            <thead>
                <tr>
                    <th class="border px-4 py-2">用戶姓名</th>
                    <th class="border px-4 py-2">氧氣用量</th>
                    <th class="border px-4 py-2">日期</th>
                    <th class="border px-4 py-2">操作</th>
                </tr>
            </thead>
            <tbody id="recordTable">
                <!-- 紀錄將在這裡顯示 -->
            </tbody>
        </table>

        <h2 class="text-xl font-bold mb-2">每月總氧氣用量</h2>
        <ul id="monthlyTotals" class="list-disc pl-5 mb-4">
            <!-- 每月總量將在這裡顯示 -->
        </ul>

        <h2 class="text-xl font-bold mb-2">每人總氧氣用量</h2>
        <ul id="individualTotals" class="list-disc pl-5 mb-4">
            <!-- 每人總量將在這裡顯示 -->
        </ul>

        <button onclick="exportRecords()" class="bg-green-500 text-white p-2">匯出紀錄</button>

        <script>
            const monthlyUsage = {};
            const individualUsage = {};
            const records = [];

            function addRecord() {
                const userName = document.getElementById('userName').value;
                const oxygenAmount = parseFloat(document.getElementById('oxygenAmount').value);
                const month = document.getElementById('month').value;
                const day = document.getElementById('day').value;

                if (userName === '' || isNaN(oxygenAmount) || month === '' || day === '') {
                    alert('請填寫所有欄位');
                    return;
                }

                const table = document.getElementById('recordTable');
                const row = document.createElement('tr');

                row.innerHTML = `
                    <td class="border px-4 py-2">${userName}</td>
                    <td class="border px-4 py-2">${oxygenAmount}</td>
                    <td class="border px-4 py-2">${month}月${day}日</td>
                    <td class="border px-4 py-2">
                        <button onclick="deleteRecord(this, '${userName}', ${month}, ${oxygenAmount})" class="bg-red-500 text-white p-1">刪除</button>
                    </td>
                `;

                table.appendChild(row);
                records.push({ userName, oxygenAmount, month, day });
                updateMonthlyUsage(month, oxygenAmount);
                updateIndividualUsage(userName, oxygenAmount);
                updateMonthlyTotals();
                updateIndividualTotals();

                document.getElementById('userName').value = '';
                document.getElementById('oxygenAmount').value = '';
                document.getElementById('month').value = '';
                document.getElementById('day').value = '';
            }

            function deleteRecord(button, userName, month, oxygenAmount) {
                const row = button.parentElement.parentElement;
                row.parentElement.removeChild(row);
                records.splice(records.findIndex(record => record.userName === userName && record.month === month && record.oxygenAmount === oxygenAmount), 1);
                updateMonthlyUsage(month, -oxygenAmount);
                updateIndividualUsage(userName, -oxygenAmount);
                updateMonthlyTotals();
                updateIndividualTotals();
            }

            function updateMonthlyUsage(month, amount) {
                if (!monthlyUsage[month]) {
                    monthlyUsage[month] = 0;
                }
                monthlyUsage[month] += amount;
            }

            function updateIndividualUsage(userName, amount) {
                if (!individualUsage[userName]) {
                    individualUsage[userName] = 0;
                }
                individualUsage[userName] += amount;
            }

            function updateMonthlyTotals() {
                const monthlyTotals = document.getElementById('monthlyTotals');
                monthlyTotals.innerHTML = '';

                for (const month in monthlyUsage) {
                    const total = monthlyUsage[month];
                    const listItem = document.createElement('li');
                    listItem.textContent = `${month}月: ${total} 單位氧氣`;
                    monthlyTotals.appendChild(listItem);
                }
            }

            function updateIndividualTotals() {
                const individualTotals = document.getElementById('individualTotals');
                individualTotals.innerHTML = '';

                for (const userName in individualUsage) {
                    const total = individualUsage[userName];
                    const listItem = document.createElement('li');
                    listItem.textContent = `${userName}: ${total} 單位氧氣`;
                    individualTotals.appendChild(listItem);
                }
            }

            function exportRecords() {
                let csvContent = "data:text/csv;charset=utf-8,\uFEFF"; // 添加BOM以支持UTF-8編碼
                csvContent += "用戶姓名,氧氣用量,月份,日期\n"; // CSV 標題

                records.forEach(record => {
                    const row = `${record.userName},${record.oxygenAmount},${record.month},${record.day}`;
                    csvContent += row + "\n";
                });

                const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
                const link = document.createElement("a");
                const url = URL.createObjectURL(blob);
                link.setAttribute("href", url);
                link.setAttribute("download", "oxygen_usage_records.csv");
                document.body.appendChild(link); // Required for FF

                link.click();
                document.body.removeChild(link); // Clean up
                URL.revokeObjectURL(url); // 釋放URL對象
            }
        </script>
    </body>
    </html>
