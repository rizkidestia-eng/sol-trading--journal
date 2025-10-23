# sol-trading--journal
trading journal solusdt
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trading Journal SOLUSDT</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 20px;
            min-height: 100vh;
        }
        
        .container {
            max-width: 1400px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
        }
        
        h1 {
            text-align: center;
            color: #667eea;
            margin-bottom: 10px;
            font-size: 2.5em;
        }
        
        .subtitle {
            text-align: center;
            color: #666;
            margin-bottom: 30px;
            font-size: 1.1em;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .stat-card {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
        }
        
        .stat-card.green {
            background: linear-gradient(135deg, #11998e 0%, #38ef7d 100%);
        }
        
        .stat-card.red {
            background: linear-gradient(135deg, #eb3349 0%, #f45c43 100%);
        }
        
        .stat-card.yellow {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        }
        
        .stat-label {
            font-size: 0.9em;
            opacity: 0.9;
            margin-bottom: 5px;
        }
        
        .stat-value {
            font-size: 2em;
            font-weight: bold;
        }
        
        .input-section {
            background: #f8f9fa;
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
        }
        
        .input-section h2 {
            color: #667eea;
            margin-bottom: 20px;
            font-size: 1.5em;
        }
        
        .form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 15px;
        }
        
        .form-group {
            display: flex;
            flex-direction: column;
        }
        
        label {
            font-weight: 600;
            margin-bottom: 5px;
            color: #333;
            font-size: 0.9em;
        }
        
        input, select, textarea {
            padding: 10px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1em;
            transition: border 0.3s;
        }
        
        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: #667eea;
        }
        
        textarea {
            resize: vertical;
            min-height: 60px;
        }
        
        .btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 12px 30px;
            border: none;
            border-radius: 8px;
            font-size: 1.1em;
            font-weight: 600;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            margin-right: 10px;
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(102, 126, 234, 0.4);
        }
        
        .btn-secondary {
            background: linear-gradient(135deg, #757F9A 0%, #D7DDE8 100%);
        }
        
        .btn-danger {
            background: linear-gradient(135deg, #eb3349 0%, #f45c43 100%);
        }
        
        .trades-table {
            overflow-x: auto;
            margin-bottom: 30px;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
        
        th {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: 600;
        }
        
        td {
            padding: 12px 15px;
            border-bottom: 1px solid #e0e0e0;
        }
        
        tr:hover {
            background: #f8f9fa;
        }
        
        .profit {
            color: #38ef7d;
            font-weight: 600;
        }
        
        .loss {
            color: #f45c43;
            font-weight: 600;
        }
        
        .badge {
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 0.85em;
            font-weight: 600;
        }
        
        .badge-win {
            background: #d4edda;
            color: #155724;
        }
        
        .badge-loss {
            background: #f8d7da;
            color: #721c24;
        }
        
        .delete-btn {
            background: #f45c43;
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.9em;
        }
        
        .delete-btn:hover {
            background: #eb3349;
        }
        
        .no-data {
            text-align: center;
            padding: 40px;
            color: #999;
            font-size: 1.1em;
        }
        
        .chart-container {
            background: #f8f9fa;
            padding: 25px;
            border-radius: 15px;
            margin-bottom: 30px;
        }
        
        .chart-container h2 {
            color: #667eea;
            margin-bottom: 20px;
        }
        
        @media print {
            body {
                background: white;
            }
            .btn, .input-section {
                display: none;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>📊 Trading Journal SOLUSDT</h1>
        <p class="subtitle">Track, Analyze, Improve - Target: 2x Trade @ TP 3% per Hari</p>
        
        <!-- Statistics Dashboard -->
        <div class="stats-grid">
            <div class="stat-card">
                <div class="stat-label">Total Trades</div>
                <div class="stat-value" id="totalTrades">0</div>
            </div>
            <div class="stat-card green">
                <div class="stat-label">Win Rate</div>
                <div class="stat-value" id="winRate">0%</div>
            </div>
            <div class="stat-card yellow">
                <div class="stat-label">Total P&L</div>
                <div class="stat-value" id="totalPnL">$0</div>
            </div>
            <div class="stat-card">
                <div class="stat-label">Avg RR Achieved</div>
                <div class="stat-value" id="avgRR">0</div>
            </div>
            <div class="stat-card green">
                <div class="stat-label">Best Trade</div>
                <div class="stat-value" id="bestTrade">$0</div>
            </div>
            <div class="stat-card red">
                <div class="stat-label">Worst Trade</div>
                <div class="stat-value" id="worstTrade">$0</div>
            </div>
        </div>
        
        <!-- Input Form -->
        <div class="input-section">
            <h2>➕ Input Trade Baru</h2>
            <div class="form-grid">
                <div class="form-group">
                    <label>Tanggal & Waktu</label>
                    <input type="datetime-local" id="tradeDate">
                </div>
                <div class="form-group">
                    <label>Sesi</label>
                    <select id="session">
                        <option value="London">London (16:00-18:00)</option>
                        <option value="New York">New York (20:00-22:00)</option>
                        <option value="Other">Lainnya</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Direction</label>
                    <select id="direction">
                        <option value="Long">Long (Buy)</option>
                        <option value="Short">Short (Sell)</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Entry Price ($)</label>
                    <input type="number" id="entryPrice" step="0.01" placeholder="150.50">
                </div>
                <div class="form-group">
                    <label>Exit Price ($)</label>
                    <input type="number" id="exitPrice" step="0.01" placeholder="154.00">
                </div>
                <div class="form-group">
                    <label>Position Size (SOL)</label>
                    <input type="number" id="positionSize" step="0.01" placeholder="10.00">
                </div>
            </div>
            <div class="form-grid">
                <div class="form-group">
                    <label>Stop Loss ($)</label>
                    <input type="number" id="stopLoss" step="0.01" placeholder="148.25">
                </div>
                <div class="form-group">
                    <label>Target TP ($)</label>
                    <input type="number" id="takeProfit" step="0.01" placeholder="155.00">
                </div>
                <div class="form-group">
                    <label>Result</label>
                    <select id="result">
                        <option value="Win">Win ✅</option>
                        <option value="Loss">Loss ❌</option>
                        <option value="Breakeven">Breakeven</option>
                    </select>
                </div>
            </div>
            <div class="form-group" style="margin-top: 15px;">
                <label>Notes (Setup, Alasan Entry, Mistakes, dll)</label>
                <textarea id="notes" placeholder="Contoh: EMA 9 cross 21, BOS bullish di M15, entry saat pullback ke OB H1. Bias H4 bullish. BTC trending up."></textarea>
            </div>
            <div style="margin-top: 20px;">
                <button class="btn" onclick="addTrade()">💾 Simpan Trade</button>
                <button class="btn btn-secondary" onclick="exportData()">📥 Export CSV</button>
                <button class="btn btn-danger" onclick="clearAllData()">🗑️ Clear All Data</button>
            </div>
        </div>
        
        <!-- Trades Table -->
        <div class="trades-table">
            <h2 style="color: #667eea; margin-bottom: 20px;">📝 History Trades</h2>
            <table id="tradesTable">
                <thead>
                    <tr>
                        <th>Date/Time</th>
                        <th>Sesi</th>
                        <th>Direction</th>
                        <th>Entry</th>
                        <th>Exit</th>
                        <th>Size</th>
                        <th>P&L ($)</th>
                        <th>P&L (%)</th>
                        <th>RR</th>
                        <th>Result</th>
                        <th>Notes</th>
                        <th>Action</th>
                    </tr>
                </thead>
                <tbody id="tradesBody">
                    <tr>
                        <td colspan="12" class="no-data">Belum ada trade. Mulai input trade pertama! 🚀</td>
                    </tr>
                </tbody>
            </table>
        </div>
        
        <!-- Weekly Summary -->
        <div class="chart-container">
            <h2>📈 Weekly Performance</h2>
            <div id="weeklySummary">
                <p style="color: #666;">Data weekly summary akan muncul setelah ada minimal 1 trade.</p>
            </div>
        </div>
    </div>
    
    <script>
        let trades = [];
        
        // Load data dari memory saat halaman dibuka
        function loadData() {
            const saved = localStorage.getItem('solTrades');
            if (saved) {
                trades = JSON.parse(saved);
                updateDisplay();
            }
        }
        
        // Save data ke memory
        function saveData() {
            localStorage.setItem('solTrades', JSON.stringify(trades));
        }
        
        // Set default datetime ke sekarang
        document.getElementById('tradeDate').valueAsNumber = Date.now() - (new Date().getTimezoneOffset() * 60000);
        
        function addTrade() {
            const tradeDate = document.getElementById('tradeDate').value;
            const session = document.getElementById('session').value;
            const direction = document.getElementById('direction').value;
            const entryPrice = parseFloat(document.getElementById('entryPrice').value);
            const exitPrice = parseFloat(document.getElementById('exitPrice').value);
            const positionSize = parseFloat(document.getElementById('positionSize').value);
            const stopLoss = parseFloat(document.getElementById('stopLoss').value);
            const takeProfit = parseFloat(document.getElementById('takeProfit').value);
            const result = document.getElementById('result').value;
            const notes = document.getElementById('notes').value;
            
            if (!tradeDate || !entryPrice || !exitPrice || !positionSize) {
                alert('⚠️ Mohon isi minimal: Tanggal, Entry Price, Exit Price, dan Position Size!');
                return;
            }
            
            // Calculate P&L
            let pnlDollar, pnlPercent, rrAchieved;
            
            if (direction === 'Long') {
                pnlDollar = (exitPrice - entryPrice) * positionSize;
                pnlPercent = ((exitPrice - entryPrice) / entryPrice) * 100;
            } else {
                pnlDollar = (entryPrice - exitPrice) * positionSize;
                pnlPercent = ((entryPrice - exitPrice) / entryPrice) * 100;
            }
            
            // Calculate RR achieved
            const risk = Math.abs(entryPrice - stopLoss) * positionSize;
            rrAchieved = risk > 0 ? Math.abs(pnlDollar / risk) : 0;
            
            const trade = {
                id: Date.now(),
                date: tradeDate,
                session,
                direction,
                entryPrice,
                exitPrice,
                positionSize,
                stopLoss,
                takeProfit,
                pnlDollar,
                pnlPercent,
                rrAchieved,
                result,
                notes
            };
            
            trades.unshift(trade);
            saveData();
            updateDisplay();
            
            // Clear form
            document.getElementById('notes').value = '';
            document.getElementById('entryPrice').value = '';
            document.getElementById('exitPrice').value = '';
            document.getElementById('positionSize').value = '';
            document.getElementById('stopLoss').value = '';
            document.getElementById('takeProfit').value = '';
            
            alert('✅ Trade berhasil disimpan!');
        }
        
        function deleteTrade(id) {
            if (confirm('Yakin mau hapus trade ini?')) {
                trades = trades.filter(t => t.id !== id);
                saveData();
                updateDisplay();
            }
        }
        
        function updateDisplay() {
            updateStats();
            updateTable();
            updateWeeklySummary();
        }
        
        function updateStats() {
            const totalTrades = trades.length;
            const winTrades = trades.filter(t => t.result === 'Win').length;
            const winRate = totalTrades > 0 ? ((winTrades / totalTrades) * 100).toFixed(1) : 0;
            const totalPnL = trades.reduce((sum, t) => sum + t.pnlDollar, 0);
            const avgRR = totalTrades > 0 ? (trades.reduce((sum, t) => sum + t.rrAchieved, 0) / totalTrades).toFixed(2) : 0;
            const bestTrade = trades.length > 0 ? Math.max(...trades.map(t => t.pnlDollar)) : 0;
            const worstTrade = trades.length > 0 ? Math.min(...trades.map(t => t.pnlDollar)) : 0;
            
            document.getElementById('totalTrades').textContent = totalTrades;
            document.getElementById('winRate').textContent = winRate + '%';
            document.getElementById('totalPnL').textContent = '$' + totalPnL.toFixed(2);
            document.getElementById('avgRR').textContent = avgRR;
            document.getElementById('bestTrade').textContent = '$' + bestTrade.toFixed(2);
            document.getElementById('worstTrade').textContent = '$' + worstTrade.toFixed(2);
            
            // Color coding untuk total P&L
            const pnlCard = document.getElementById('totalPnL').parentElement;
            if (totalPnL > 0) {
                pnlCard.className = 'stat-card green';
            } else if (totalPnL < 0) {
                pnlCard.className = 'stat-card red';
            } else {
                pnlCard.className = 'stat-card yellow';
            }
        }
        
        function updateTable() {
            const tbody = document.getElementById('tradesBody');
            
            if (trades.length === 0) {
                tbody.innerHTML = '<tr><td colspan="12" class="no-data">Belum ada trade. Mulai input trade pertama! 🚀</td></tr>';
                return;
            }
            
            tbody.innerHTML = trades.map(t => {
                const date = new Date(t.date);
                const dateStr = date.toLocaleDateString('id-ID', { day: '2-digit', month: 'short' });
                const timeStr = date.toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit' });
                const pnlClass = t.pnlDollar >= 0 ? 'profit' : 'loss';
                const resultBadge = t.result === 'Win' ? 'badge-win' : 'badge-loss';
                
                return `
                    <tr>
                        <td>${dateStr}<br><small>${timeStr}</small></td>
                        <td>${t.session}</td>
                        <td><strong>${t.direction}</strong></td>
                        <td>$${t.entryPrice.toFixed(2)}</td>
                        <td>$${t.exitPrice.toFixed(2)}</td>
                        <td>${t.positionSize} SOL</td>
                        <td class="${pnlClass}">$${t.pnlDollar.toFixed(2)}</td>
                        <td class="${pnlClass}">${t.pnlPercent >= 0 ? '+' : ''}${t.pnlPercent.toFixed(2)}%</td>
                        <td>1:${t.rrAchieved.toFixed(2)}</td>
                        <td><span class="badge ${resultBadge}">${t.result}</span></td>
                        <td style="max-width: 200px; font-size: 0.85em;">${t.notes || '-'}</td>
                        <td><button class="delete-btn" onclick="deleteTrade(${t.id})">Delete</button></td>
                    </tr>
                `;
            }).join('');
        }
        
        function updateWeeklySummary() {
            if (trades.length === 0) return;
            
            // Group trades by week
            const weeklyData = {};
            
            trades.forEach(t => {
                const date = new Date(t.date);
                const weekStart = new Date(date);
                weekStart.setDate(date.getDate() - date.getDay());
                const weekKey = weekStart.toLocaleDateString('id-ID', { day: '2-digit', month: 'short', year: 'numeric' });
                
                if (!weeklyData[weekKey]) {
                    weeklyData[weekKey] = {
                        trades: 0,
                        wins: 0,
                        losses: 0,
                        pnl: 0
                    };
                }
                
                weeklyData[weekKey].trades++;
                if (t.result === 'Win') weeklyData[weekKey].wins++;
                if (t.result === 'Loss') weeklyData[weekKey].losses++;
                weeklyData[weekKey].pnl += t.pnlDollar;
            });
            
            let summaryHTML = '<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px;">';
            
            Object.entries(weeklyData).forEach(([week, data]) => {
                const winRate = ((data.wins / data.trades) * 100).toFixed(0);
                const pnlClass = data.pnl >= 0 ? 'profit' : 'loss';
                
                summaryHTML += `
                    <div style="background: white; padding: 20px; border-radius: 10px; box-shadow: 0 2px 10px rgba(0,0,0,0.1);">
                        <h3 style="color: #667eea; margin-bottom: 10px; font-size: 1.1em;">Week: ${week}</h3>
                        <p><strong>Trades:</strong> ${data.trades} (${data.wins}W / ${data.losses}L)</p>
                        <p><strong>Win Rate:</strong> ${winRate}%</p>
                        <p><strong>P&L:</strong> <span class="${pnlClass}">$${data.pnl.toFixed(2)}</span></p>
                    </div>
                `;
            });
            
            summaryHTML += '</div>';
            document.getElementById('weeklySummary').innerHTML = summaryHTML;
        }
        
        function exportData() {
            if (trades.length === 0) {
                alert('⚠️ Tidak ada data untuk di-export!');
                return;
            }
            
            let csv = 'Date,Time,Session,Direction,Entry,Exit,Size,P&L_Dollar,P&L_Percent,RR,Result,Notes\n';
            
            trades.forEach(t => {
                const date = new Date(t.date);
                const dateStr = date.toLocaleDateString('id-ID');
                const timeStr = date.toLocaleTimeString('id-ID');
                csv += `${dateStr},${timeStr},${t.session},${t.direction},${t.entryPrice},${t.exitPrice},${t.positionSize},${t.pnlDollar.toFixed(2)},${t.pnlPercent.toFixed(2)},${t.rrAchieved.toFixed(2)},${t.result},"${t.notes}"\n`;
            });
            
            const blob = new Blob([csv], { type: 'text/csv' });
            const url = window.URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `SOL_Trading_Journal_${new Date().toISOString().split('T')[0]}.csv`;
            a.click();
            
            alert('✅ Data berhasil di-export ke CSV!');
        }
        
        function clearAllData() {
            if (confirm('⚠️ PERINGATAN: Ini akan menghapus SEMUA data trade!\n\nYakin mau lanjut? (Pastikan sudah export data dulu!)')) {
                if (confirm('Konfirmasi sekali lagi: HAPUS SEMUA DATA?')) {
                    trades = [];
                    saveData();
                    updateDisplay();
                    alert('✅ Semua data sudah dihapus!');
                }
            }
        }
        
        // Load data saat halaman pertama kali dibuka
        loadData();
    </script>
</body>
</html>
