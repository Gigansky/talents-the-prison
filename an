<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Калькулятор талантов - Тюряга</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            color: #e6e6e6;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
            background-color: rgba(30, 30, 46, 0.8);
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            border-bottom: 2px solid #394867;
            padding-bottom: 20px;
        }
        
        h1 {
            color: #4cc9f0;
            font-size: 2.2rem;
            margin-bottom: 10px;
            text-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
        }
        
        .subtitle {
            color: #a9b7c6;
            font-size: 1.1rem;
        }
        
        .calculator {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
            margin-bottom: 30px;
        }
        
        @media (max-width: 768px) {
            .calculator {
                grid-template-columns: 1fr;
            }
        }
        
        .input-section, .results-section {
            background-color: rgba(40, 40, 60, 0.7);
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .input-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            color: #a9b7c6;
            font-weight: 500;
        }
        
        input, select {
            width: 100%;
            padding: 12px 15px;
            border-radius: 8px;
            border: 1px solid #394867;
            background-color: #2a2a3e;
            color: #e6e6e6;
            font-size: 1rem;
            transition: all 0.3s;
        }
        
        input:focus, select:focus {
            outline: none;
            border-color: #4cc9f0;
            box-shadow: 0 0 0 2px rgba(76, 201, 240, 0.3);
        }
        
        button {
            background: linear-gradient(to right, #4361ee, #3a0ca3);
            color: white;
            border: none;
            padding: 14px 20px;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            width: 100%;
            margin-top: 10px;
        }
        
        button:hover {
            background: linear-gradient(to right, #3a56d4, #2d0a8a);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.4);
        }
        
        button:active {
            transform: translateY(0);
        }
        
        .result-item {
            background-color: rgba(50, 50, 70, 0.7);
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 15px;
            border-left: 4px solid #4361ee;
        }
        
        .result-title {
            font-size: 1.1rem;
            font-weight: 600;
            color: #4cc9f0;
            margin-bottom: 8px;
        }
        
        .result-value {
            font-size: 1.5rem;
            font-weight: 700;
            color: #f72585;
        }
        
        .progress-container {
            margin-top: 20px;
            background-color: rgba(40, 40, 60, 0.7);
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .progress-bar {
            height: 20px;
            background-color: #2a2a3e;
            border-radius: 10px;
            margin-top: 10px;
            overflow: hidden;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(to right, #4361ee, #3a0ca3);
            border-radius: 10px;
            transition: width 0.5s ease;
        }
        
        .talent-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            gap: 12px;
            margin-top: 25px;
        }
        
        .talent-item {
            background-color: rgba(50, 50, 70, 0.7);
            border-radius: 8px;
            padding: 12px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            border: 2px solid transparent;
        }
        
        .talent-item:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            border-color: #4361ee;
        }
        
        .talent-item.active {
            background-color: rgba(67, 97, 238, 0.3);
            border-color: #4361ee;
        }
        
        .talent-level {
            font-size: 1.2rem;
            font-weight: 700;
            color: #4cc9f0;
        }
        
        .talent-damage {
            font-size: 0.9rem;
            color: #a9b7c6;
            margin-top: 5px;
        }
        
        .talent-total {
            font-size: 0.8rem;
            color: #f72585;
            margin-top: 3px;
        }
        
        .info-section {
            margin-top: 30px;
            background-color: rgba(40, 40, 60, 0.7);
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .info-title {
            color: #4cc9f0;
            font-size: 1.3rem;
            margin-bottom: 15px;
            border-bottom: 1px solid #394867;
            padding-bottom: 10px;
        }
        
        .info-text {
            line-height: 1.6;
            color: #a9b7c6;
        }
        
        .highlight {
            color: #f72585;
            font-weight: 600;
        }
        
        .total-damage-section {
            margin-top: 25px;
            background-color: rgba(40, 40, 60, 0.7);
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .total-damage-title {
            color: #4cc9f0;
            font-size: 1.3rem;
            margin-bottom: 15px;
            border-bottom: 1px solid #394867;
            padding-bottom: 10px;
        }
        
        .total-damage-value {
            font-size: 1.8rem;
            font-weight: 700;
            color: #f72585;
            text-align: center;
            margin: 15px 0;
        }
        
        .total-damage-description {
            text-align: center;
            color: #a9b7c6;
            margin-bottom: 15px;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Калькулятор талантов</h1>
            <p class="subtitle">для игры "Тюряга" - рассчитывайте требуемый урон для прокачки талантов</p>
        </header>
        
        <div class="calculator">
            <div class="input-section">
                <div class="input-group">
                    <label for="talentIndex">Уровень таланта (0-998):</label>
                    <input type="number" id="talentIndex" min="0" max="998" value="50">
                </div>
                
                <div class="input-group">
                    <label for="currentDamage">Ваш текущий урон:</label>
                    <input type="number" id="currentDamage" min="0" value="5000">
                </div>
                
                <button id="calculateBtn">Рассчитать</button>
            </div>
            
            <div class="results-section">
                <div class="result-item">
                    <div class="result-title">Требуемый урон для таланта:</div>
                    <div class="result-value" id="requiredDamage">0</div>
                </div>
                
                <div class="result-item">
                    <div class="result-title">Осталось набрать урона:</div>
                    <div class="result-value" id="remainingDamage">0</div>
                </div>
                
                <div class="result-item">
                    <div class="result-title">Прогресс:</div>
                    <div class="result-value" id="progressPercent">0%</div>
                </div>
                
                <div class="progress-container">
                    <div>Прогресс прокачки:</div>
                    <div class="progress-bar">
                        <div class="progress-fill" id="progressFill" style="width: 0%"></div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="total-damage-section">
            <div class="total-damage-title">Общий урон для достижения таланта</div>
            <div class="total-damage-description">
                Общее количество урона, которое нужно нанести с начала игры до выбранного уровня таланта:
            </div>
            <div class="total-damage-value" id="totalDamageValue">0</div>
            <div class="progress-container">
                <div>Прогресс общего урона:</div>
                <div class="progress-bar">
                    <div class="progress-fill" id="totalProgressFill" style="width: 0%"></div>
                </div>
            </div>
        </div>
        
        <div class="talent-list" id="talentList">
            <!-- Таланты будут сгенерированы через JavaScript -->
        </div>
        
        <div class="info-section">
            <div class="info-title">Как работает калькулятор</div>
            <p class="info-text">
                Калькулятор рассчитывает требуемый урон для прокачки талантов по формуле из игры "Тюряга". 
                Формула учитывает разные фазы роста требований:
            </p>
            <ul class="info-text" style="margin-left: 20px; margin-top: 10px;">
                <li>Фаза 1 (1-99 уровень): множитель <span class="highlight">1.05</span></li>
                <li>Фаза 2 (100-199 уровень): множитель <span class="highlight">1.01</span></li>
                <li>Фаза 3 (200-357 уровень): множитель <span class="highlight">1.007</span></li>
                <li>Фаза 4 (358-464 уровень): множитель <span class="highlight">1.007</span></li>
                <li>Фаза 5 (465-776 уровень): множитель <span class="highlight">1.015</span></li>
                <li>Фаза 6 (777+ уровень): множитель <span class="highlight">1.014</span></li>
            </ul>
            <p class="info-text" style="margin-top: 15px;">
                Кликайте на таланты в списке выше для быстрого выбора уровня, или вводите значение вручную.
            </p>
        </div>
    </div>

    <script>
        // Формула расчета требуемого урона для таланта
        function getRequiredDamage(talentIndex) {
            const n = talentIndex + 1;
            if (n < 1 || n > 999) {
                throw new Error("Индекс должен быть между 0 и 998");
            }
            
            // В реальной игре здесь могут быть переопределения
            // if (DamageReqOverrides.TryGetValue(n, out var overridden))
            //     return overridden;
            
            const baseValue = 50;
            const phase1 = Math.pow(1.05, Math.max(Math.min(n, 99) - 1, 0));
            const phase2 = Math.pow(1.01, Math.max(Math.min(n - 99, 100), 0));
            const phase3 = Math.pow(1.007, Math.max(Math.min(n - 199, 158), 0));
            const phase4 = Math.pow(1.007, Math.max(Math.min(n - 357, 107), 0));
            const phase5 = Math.pow(1.015, Math.max(Math.min(n - 464, 312), 0));
            const phase6 = Math.pow(1.014, Math.max(n - 776, 0));
            const result = baseValue * phase1 * phase2 * phase3 * phase4 * phase5 * phase6;
            
            return Math.round(result);
        }
        
        // Функция расчета общего урона для достижения уровня таланта
        function getTotalDamageForTalent(talentIndex) {
            let total = 0;
            for (let i = 0; i <= talentIndex; i++) {
                total += getRequiredDamage(i);
            }
            return total;
        }
        
        // Элементы DOM
        const talentIndexInput = document.getElementById('talentIndex');
        const currentDamageInput = document.getElementById('currentDamage');
        const calculateBtn = document.getElementById('calculateBtn');
        const requiredDamageElement = document.getElementById('requiredDamage');
        const remainingDamageElement = document.getElementById('remainingDamage');
        const progressPercentElement = document.getElementById('progressPercent');
        const progressFillElement = document.getElementById('progressFill');
        const talentListElement = document.getElementById('talentList');
        const totalDamageValueElement = document.getElementById('totalDamageValue');
        const totalProgressFillElement = document.getElementById('totalProgressFill');
        
        // Функция форматирования чисел с разделителями
        function formatNumber(num) {
            return num.toString().replace(/\B(?=(\d{3})+(?!\d))/g, " ");
        }
        
        // Функция расчета и отображения результатов
        function calculate() {
            try {
                const talentIndex = parseInt(talentIndexInput.value);
                const currentDamage = parseInt(currentDamageInput.value);
                
                if (isNaN(talentIndex) || talentIndex < 0 || talentIndex > 998) {
                    alert('Пожалуйста, введите корректный уровень таланта (0-998)');
                    return;
                }
                
                if (isNaN(currentDamage) || currentDamage < 0) {
                    alert('Пожалуйста, введите корректное значение текущего урона');
                    return;
                }
                
                const requiredDamage = getRequiredDamage(talentIndex);
                const remainingDamage = Math.max(0, requiredDamage - currentDamage);
                const progressPercent = Math.min(100, Math.round((currentDamage / requiredDamage) * 100));
                
                // Расчет общего урона
                const totalDamage = getTotalDamageForTalent(talentIndex);
                const totalProgressPercent = Math.min(100, Math.round((currentDamage / totalDamage) * 100));
                
                requiredDamageElement.textContent = formatNumber(requiredDamage);
                remainingDamageElement.textContent = formatNumber(remainingDamage);
                progressPercentElement.textContent = `${progressPercent}%`;
                progressFillElement.style.width = `${progressPercent}%`;
                
                totalDamageValueElement.textContent = formatNumber(totalDamage);
                totalProgressFillElement.style.width = `${totalProgressPercent}%`;
                
                // Обновляем активный талант в списке
                updateActiveTalent(talentIndex);
                
            } catch (error) {
                alert('Произошла ошибка при расчете: ' + error.message);
            }
        }
        
        // Функция обновления активного таланта в списке
        function updateActiveTalent(activeIndex) {
            const talentItems = document.querySelectorAll('.talent-item');
            talentItems.forEach(item => {
                item.classList.remove('active');
                if (parseInt(item.dataset.index) === activeIndex) {
                    item.classList.add('active');
                }
            });
        }
        
        // Генерация списка талантов
        function generateTalentList() {
            talentListElement.innerHTML = '';
            
            // Генерируем таланты для ключевых уровней
            const keyLevels = [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 
                               150, 200, 250, 300, 350, 400, 450, 500, 
                               550, 600, 650, 700, 750, 800, 850, 900, 950, 998];
            
            keyLevels.forEach(level => {
                const requiredDamage = getRequiredDamage(level);
                const totalDamage = getTotalDamageForTalent(level);
                const talentItem = document.createElement('div');
                talentItem.className = 'talent-item';
                talentItem.dataset.index = level;
                
                talentItem.innerHTML = `
                    <div class="talent-level">${level}</div>
                    <div class="talent-damage">${formatNumber(requiredDamage)}</div>
                    <div class="talent-total">Σ ${formatNumber(totalDamage)}</div>
                `;
                
                talentItem.addEventListener('click', () => {
                    talentIndexInput.value = level;
                    calculate();
                });
                
                talentListElement.appendChild(talentItem);
            });
        }
        
        // Инициализация при загрузке страницы
        window.addEventListener('DOMContentLoaded', () => {
            generateTalentList();
            calculate(); // Первоначальный расчет
            
            // Обработчики событий
            calculateBtn.addEventListener('click', calculate);
            
            talentIndexInput.addEventListener('change', calculate);
            currentDamageInput.addEventListener('change', calculate);
            
            talentIndexInput.addEventListener('input', calculate);
            currentDamageInput.addEventListener('input', calculate);
        });
    </script>
</body>
</html>
