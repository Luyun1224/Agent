<!DOCTYPE html>
<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI 多代理架構</title>
    <!-- 引入 Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- 引入 Inter 字體 -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f3f4f6; /* 淺灰色背景 */
            color: #333; /* 深灰色文字 */
            line-height: 1.6;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1.5rem;
        }
        .card {
            background-color: #fff;
            border-radius: 1rem; /* 更圓潤的圓角 */
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.08); /* 柔和的陰影 */
            padding: 2rem;
            margin-bottom: 2rem;
            border: 1px solid #e2e8f0; /* 淺邊框 */
            transition: transform 0.2s ease-in-out;
        }
        .card:hover {
            transform: translateY(-5px); /* 懸停效果 */
        }
        .section-title {
            font-size: 2.5rem; /* 較大標題 */
            font-weight: 700; /* 粗體 */
            color: #1a202c; /* 深色標題 */
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
        }
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: #6366f1; /* 紫色下劃線 */
            margin: 1rem auto 0;
            border-radius: 9999px;
        }
        .agent-flow {
            position: relative;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 2rem;
            margin-top: 3rem;
            padding-bottom: 2rem; /* 留出底部空間 */
        }
        .agent-box {
            background-color: #ffffff;
            border-radius: 1rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            padding: 1.5rem;
            text-align: center;
            width: calc(33% - 2rem); /* 三列佈局 */
            min-width: 280px; /* 最小寬度 */
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            border: 2px solid #a78bfa; /* 紫色邊框 */
            transition: all 0.3s ease;
        }
        .agent-box:hover {
            transform: translateY(-8px) scale(1.02);
            box-shadow: 0 12px 25px rgba(0, 0, 0, 0.12);
            border-color: #8b5cf6;
        }
        .orchestrator-box {
            background-color: #6366f1; /* 深紫色 */
            color: white;
            padding: 2rem;
            width: 100%; /* 總策劃居中且寬度較大 */
            max-width: 400px;
            margin-bottom: 3rem;
            border-radius: 1.5rem;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
            position: relative;
            z-index: 10; /* 確保在頂部 */
            border: 3px solid #c7d2fe;
            animation: pulse 2s infinite;
        }
        .orchestrator-box h3 {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 0.75rem;
        }
        .agent-box h4 {
            font-size: 1.25rem;
            font-weight: 600;
            color: #4c51bf; /* 深藍紫色 */
            margin-bottom: 0.75rem;
        }
        .agent-box p {
            font-size: 0.95rem;
            color: #666;
            flex-grow: 1; /* 讓內容填充空間 */
        }

        /* 響應式調整 */
        @media (max-width: 1024px) {
            .agent-box {
                width: calc(50% - 2rem); /* 兩列佈局 */
            }
        }
        @media (max-width: 768px) {
            .agent-box {
                width: 100%; /* 單列佈局 */
            }
            .section-title {
                font-size: 2rem;
            }
            .card {
                padding: 1.5rem;
            }
        }

        /* 箭頭樣式 */
        .arrow {
            position: absolute;
            background-color: #6366f1; /* 紫色箭頭 */
            height: 3px;
            z-index: 5;
            transform-origin: left center;
        }
        .arrow::after {
            content: '';
            position: absolute;
            width: 0;
            height: 0;
            border-top: 8px solid transparent;
            border-bottom: 8px solid transparent;
            border-left: 8px solid #6366f1;
            right: -8px;
            top: 50%;
            transform: translateY(-50%);
        }

        /* 脈衝動畫 */
        @keyframes pulse {
            0% {
                box-shadow: 0 15px 30px rgba(99, 102, 241, 0.2);
            }
            50% {
                box-shadow: 0 15px 40px rgba(99, 102, 241, 0.4);
            }
            100% {
                box-shadow: 0 15px 30px rgba(99, 102, 241, 0.2);
            }
        }

        /* Prompt Examples Specific Styles */
        .prompt-card {
            background-color: #f8fafc;
            border-radius: 0.75rem;
            border: 1px solid #cbd5e1;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
        }
        .prompt-card h3 {
            font-size: 1.35rem;
            font-weight: 600;
            color: #2b6cb0; /* Deep blue for prompt titles */
            margin-bottom: 0.75rem;
        }
        .prompt-card pre {
            background-color: #e2e8f0;
            color: #2d3748;
            padding: 1rem;
            border-radius: 0.5rem;
            overflow-x: auto;
            font-family: 'SFMono-Regular', Consolas, 'Liberation Mono', Menlo, Courier, monospace;
            font-size: 0.9rem;
            white-space: pre-wrap; /* Wrap long lines */
            word-break: break-all; /* Break words to prevent overflow */
            margin-top: 0.75rem;
        }
        .prompt-card p {
            font-size: 0.95rem;
            color: #4a5568;
            margin-top: 0.5rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <header class="py-12 text-center">
            <h1 class="text-5xl font-extrabold text-blue-800 mb-4">🌟 善用 AI 多代理架構完成複雜專案</h1>
            <p class="text-xl text-gray-600">AI 已不再是單一助手，而是您的智慧團隊夥伴。</p>
        </header>

        <!-- 核心觀念 -->
        <section class="mb-12">
            <h2 class="section-title">🧠 核心觀念</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="card">
                    <h3 class="text-2xl font-bold text-indigo-700 mb-3">AI 已不再是單一助手，而是團隊夥伴</h3>
                    <ul class="list-disc pl-5 space-y-2 text-gray-700">
                        <li>每個「AI 代理人（Agent）」可被設定成不同角色：統籌、文獻分析、寫作、視覺設計、品質控管等。</li>
                        <li>透過多代理協作，可以將一本共識書、計畫案、教學模組在短時間內高效完成。</li>
                    </ul>
                </div>
                <div class="card">
                    <h3 class="text-2xl font-bold text-indigo-700 mb-3">以任務導向規劃 AI 架構</h3>
                    <ul class="list-disc pl-5 space-y-2 text-gray-700">
                        <li>明確輸入「我希望完成什麼」，例如：撰寫在地化生活形態醫學專家共識。</li>
                        <li>接著由 GPT/Claude/Gemini 等工具協助分配多位 Agent，各自負責文獻搜尋、摘要撰寫、圖片生成、語音總結等。</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- 工具與應用對應 -->
        <section class="mb-12">
            <h2 class="section-title">🛠 工具與應用對應</h2>
            <div class="card overflow-x-auto">
                <table class="min-w-full divide-y divide-gray-200">
                    <thead class="bg-indigo-50">
                        <tr>
                            <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider rounded-tl-lg">工具 / 模型</th>
                            <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">擅長功能</th>
                            <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider rounded-tr-lg">適用場景</th>
                        </tr>
                    </thead>
                    <tbody class="bg-white divide-y divide-gray-200">
                        <tr>
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="text-sm font-medium text-gray-900">ChatGPT-4.5 / GPT-4o</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">寫作、邏輯、程式產出、繁體中文最穩</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">白皮書撰寫、問卷分析、流程建議</div>
                            </td>
                        </tr>
                        <tr>
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="text-sm font-medium text-gray-900">Claude</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">超大文本處理（百頁 PDF）、文獻整併</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">長篇論文摘要、結構重建</div>
                            </td>
                        </tr>
                        <tr>
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="text-sm font-medium text-gray-900">Gemini</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">多模態整合（圖像推理 + 文件生成）</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">視覺化、PDF 解析、語音紀錄</div>
                            </td>
                        </tr>
                        <tr>
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="text-sm font-medium text-gray-900">Perplexity / Scispace</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">深度文獻搜尋、DOI 匯整</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">找實證、論文出處、比對來源</div>
                            </td>
                        </tr>
                        <tr>
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="text-sm font-medium text-gray-900">Gamma / Notion AI / Elicit</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">網頁視覺化、互動簡報、結構設計</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">工作坊教材、資料庫建置</div>
                            </td>
                        </tr>
                        <tr>
                            <td class="px-6 py-4 whitespace-nowrap">
                                <div class="text-sm font-medium text-gray-900">Mistral / Mixtral</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">推論速度快、適合腳本類應用</div>
                            </td>
                            <td class="px-6 py-4">
                                <div class="text-sm text-gray-700">聊天機器人、語音稿生成</div>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </section>

        <!-- 多代理人範例 -->
        <section class="mb-12">
            <h2 class="section-title">� 多代理人範例<br><small class="text-xl font-normal text-gray-500">（以「生活形態醫學共識撰寫」為例）</small></h2>
            <div class="flex flex-col items-center agent-flow">
                <!-- 總策劃 Agent -->
                <div class="orchestrator-box text-center">
                    <h3 class="text-3xl font-extrabold mb-2">🎯 總策劃 Agent</h3>
                    <p class="text-lg">統整章節架構、分配任務、控制證據等級一致性</p>
                </div>

                <!-- 箭頭向下 -->
                <div class="w-1 bg-indigo-500 h-20 rounded-full my-4 relative">
                    <div class="absolute bottom-0 left-1/2 -translate-x-1/2 w-0 h-0 border-l-[10px] border-r-[10px] border-t-[15px] border-l-transparent border-r-transparent border-t-indigo-500"></div>
                </div>

                <!-- 各 Agent -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 w-full max-w-6xl">
                    <div class="agent-box">
                        <h4 class="text-indigo-700">📚 文獻搜尋 Agent</h4>
                        <p>根據章節主題進行高等級文獻抓取（可用深入研究功能）</p>
                    </div>
                    <div class="agent-box">
                        <h4 class="text-indigo-700">✍️ 章節撰寫 Agent</h4>
                        <p>每章 2000-3000 字，引用文獻，自動摘要</p>
                    </div>
                    <div class="agent-box">
                        <h4 class="text-indigo-700">🖼 視覺設計 Agent</h4>
                        <p>為每章生成摘要圖、統計圖、資訊圖表</p>
                    </div>
                    <div class="agent-box">
                        <h4 class="text-indigo-700">🧪 品質控管 Agent</h4>
                        <p>整體內容邏輯一致性、風格一致性修正</p>
                    </div>
                    <div class="agent-box">
                        <h4 class="text-indigo-700">📊 評估產出 Agent</h4>
                        <p>將結果製作成網頁、PDF、語音、廣播等輸出形式</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- AI 任務指令範例 -->
        <section class="mb-12">
            <h2 class="section-title">💡 AI 任務指令範例 (Prompt Examples)</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="prompt-card">
                    <h3>1. 建立專家共識型章節文章</h3>
                    <pre>我要完成一本「生活形態醫學臺灣在地化」的專家共識白皮書，請你幫我設計 AI 多代理架構，分配不同 AI 角色的任務與流程。目標讀者為臺灣的專業醫事人員，每章需 2000–3000 字，有文獻、摘要、圖片。完成後需整合為一份有視覺化與摘要圖的 HTML 文件。</pre>
                    <p>此指令會啟動 <b>總策劃 Agent</b> 來協調整個專案，並涉及 <b>文獻搜尋 Agent</b>、<b>章節撰寫 Agent</b>、<b>視覺設計 Agent</b> 及 <b>評估產出 Agent</b> 的緊密協作。</p>
                </div>
                <div class="prompt-card">
                    <h3>2. 深度文獻研究</h3>
                    <pre>請幫我針對「生活形態醫學的在地化挑戰與機會」進行深度研究，提供具證據等級的文獻來源（至少 10 篇），每篇附上 DOI、出處、結論摘要，並說明與臺灣情境的關聯性。</pre>
                    <p>這個任務主要由 <b>文獻搜尋 Agent</b> 負責，可能結合 <b>Perplexity / Scispace</b> 等工具來進行深度文獻探勘。</p>
                </div>
                <div class="prompt-card">
                    <h3>3. 問卷設計（以護理人員 AI 認知為例）</h3>
                    <pre>請根據實證文獻，設計一份針對居家護理人員的「AI 認知與態度前後測問卷」。須包含三大構面：知識、態度、應用經驗，每題對應參考文獻，Likert 5 點量表，需標明出處。</pre>
                    <p>此指令需要 <b>文獻搜尋 Agent</b> 獲取實證資料，並由 <b>章節撰寫 Agent</b> 負責問卷的邏輯設計和內容撰寫。</p>
                </div>
                <div class="prompt-card">
                    <h3>4. 視覺化呈現研究結果</h3>
                    <pre>這是一份 PDF 報告內容，請幫我視覺化為摘要圖、摘要投影片，並以台灣醫學教育期刊的風格配色。請生成 HTML 頁面與圖片摘要兩種格式。</pre>
                    <p>這個任務是 <b>視覺設計 Agent</b> 的核心功能，可能搭配 <b>Gemini</b> 的多模態整合能力及 <b>Gamma / Notion AI</b> 等工具進行網頁與簡報設計。</p>
                </div>
                <div class="prompt-card">
                    <h3>5. 自動任務管理與提醒</h3>
                    <pre>請幫我設定一個 AI 任務助手，每天下午 4 點提醒我要審查最新的教案回收表單，並整理 Gmail 中含有「OSCE」、「評量」字樣的信件摘要，每週一輸出為摘要報告。</pre>
                    <p>此類任務可由一個專門的 <b>自動化 Agent</b> 負責，該 Agent 需具備時間排程、郵件處理和報告生成能力，類似 <b>Mistral / Mixtral</b> 的腳本應用。</p>
                </div>
                <div class="prompt-card">
                    <h3>6. 視覺化一份問卷結果</h3>
                    <pre>這是某場次問卷回收的 Excel，請幫我將它視覺化為一份互動式 HTML 儀表板，顯示前後測比較、分數提升趨勢、學員回饋分類，並提供 AI 判讀建議。</pre>
                    <p>這項任務結合了 <b>視覺設計 Agent</b> (用於互動式儀表板) 和潛在的 <b>章節撰寫 Agent</b> (用於 AI 判讀建議)，並需要強大的數據處理能力。</p>
                </div>
            </div>
        </section>

        <footer class="text-center py-8 text-gray-500">
            <p>&copy; 2025 AI 多代理架構. All rights reserved.</p>
        </footer>
    </div>
</body>
</html>
�
