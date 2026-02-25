# NSM-MULTI-develop 
<!-- NSM AI FULL SCREEN CHAT -->

<!-- Floating Button (Small) -->
<div id="aiAssistantBtn" onclick="toggleAIChat()" 
     style="position: fixed; bottom: 20px; right: 20px; z-index: 9999; cursor: pointer;">
    <div style="background: linear-gradient(135deg, #9370db 0%, #8a2be2 100%); 
                width: 60px; height: 60px; border-radius: 50%; 
                display: flex; align-items: center; justify-content: center;
                box-shadow: 0 5px 20px rgba(147,112,219,0.5);
                border: 3px solid #ffd700; animation: pulseAI 2s infinite;">
        <span style="font-size: 1.8em;">🤖</span>
    </div>
    <div style="position: absolute; top: -8px; right: -8px; background: #ff0000; color: #fff; 
                padding: 4px 8px; border-radius: 15px; font-size: 0.7em; font-weight: bold;">
        NSM AI
    </div>
</div>

<style>
@keyframes pulseAI {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.1); }
}
</style>

<!-- FULL SCREEN CHAT OVERLAY -->
<div id="aiChatOverlay" style="display: none; position: fixed; 
     top: 0; left: 0; width: 100%; height: 100%; 
     background: rgba(0,0,0,0.9); z-index: 9998;
     justify-content: center; align-items: center;">

    <!-- Chat Container - 90% Screen Size -->
    <div style="width: 95%; height: 95%; max-width: 800px; 
                background: linear-gradient(135deg, #0f0c29 0%, #302b63 100%); 
                border-radius: 20px; border: 3px solid #9370db; 
                box-shadow: 0 0 50px rgba(147,112,219,0.5);
                display: flex; flex-direction: column; overflow: hidden;">

        <!-- Header -->
        <div style="background: linear-gradient(135deg, #9370db 0%, #8a2be2 100%); 
                    padding: 20px; display: flex; justify-content: space-between; align-items: center;
                    border-bottom: 3px solid #ffd700;">
            <div style="display: flex; align-items: center; gap: 15px;">
                <div style="background: #fff; width: 50px; height: 50px; border-radius: 50%; 
                            display: flex; align-items: center; justify-content: center; font-size: 1.8em;">
                    🤖
                </div>
                <div>
                    <h3 style="color: #fff; margin: 0; font-size: 1.5em; letter-spacing: 2px;">NSM AI</h3>
                    <p style="color: #ffd700; margin: 5px 0 0 0; font-size: 0.9em;">Your Investment Guide | CEO: Muhammed Niyas</p>
                </div>
            </div>
            <button onclick="toggleAIChat()" 
                    style="background: rgba(255,0,0,0.8); color: #fff; border: none; 
                           width: 40px; height: 40px; border-radius: 50%; font-size: 1.5em; 
                           cursor: pointer; display: flex; align-items: center; justify-content: center;">
                ✕
            </button>
        </div>

        <!-- Quick Questions Bar -->
        <div style="background: rgba(147,112,219,0.2); padding: 15px; 
                    display: flex; gap: 10px; overflow-x: auto; flex-wrap: wrap;">
            <button onclick="askAI('What is SIP?')" 
                    style="background: rgba(255,215,0,0.2); border: 2px solid #ffd700; 
                           color: #ffd700; padding: 10px 20px; border-radius: 25px; 
                           font-size: 0.9em; cursor: pointer; white-space: nowrap;">
                💰 What is SIP?
            </button>
            <button onclick="askAI('How to start investing?')" 
                    style="background: rgba(0,255,0,0.2); border: 2px solid #00ff00; 
                           color: #00ff00; padding: 10px 20px; border-radius: 25px; 
                           font-size: 0.9em; cursor: pointer; white-space: nowrap;">
                🚀 How to start?
            </button>
            <button onclick="askAI('Best investment for beginners?')" 
                    style="background: rgba(0,191,255,0.2); border: 2px solid #00bfff; 
                           color: #00bfff; padding: 10px 20px; border-radius: 25px; 
                           font-size: 0.9em; cursor: pointer; white-space: nowrap;">
                ⭐ Best for beginners?
            </button>
            <button onclick="askAI('Stock market basics')" 
                    style="background: rgba(255,107,107,0.2); border: 2px solid #ff6b6b; 
                           color: #ff6b6b; padding: 10px 20px; border-radius: 25px; 
                           font-size: 0.9em; cursor: pointer; white-space: nowrap;">
                📈 Stock Market
            </button>
            <button onclick="askAI('Contact NSM CEO')" 
                    style="background: rgba(37,211,102,0.2); border: 2px solid #25d366; 
                           color: #25d366; padding: 10px 20px; border-radius: 25px; 
                           font-size: 0.9em; cursor: pointer; white-space: nowrap;">
                💬 Contact CEO Niyas
            </button>
        </div>

        <!-- Chat Area - LARGE -->
        <div id="chatArea" style="flex: 1; overflow-y: auto; padding: 25px; 
                                  background: rgba(0,0,0,0.4); font-size: 1.1em;">
            
            <!-- Welcome Message -->
            <div style="margin-bottom: 25px;">
                <div style="display: flex; align-items: flex-start; gap: 12px;">
                    <div style="background: #9370db; width: 45px; height: 45px; border-radius: 50%; 
                                display: flex; align-items: center; justify-content: center; 
                                font-size: 1.5em; flex-shrink: 0;">
                        🤖
                    </div>
                    <div style="background: rgba(147,112,219,0.2); padding: 20px; border-radius: 20px; 
                                border-left: 4px solid #9370db; max-width: 85%; color: #fff; 
                                line-height: 1.8; font-size: 1.05em;">
                        <p style="margin: 0 0 15px 0;"><strong>👋 Welcome to NSM Multi Invest!</strong></p>
                        <p style="margin: 0 0 10px 0;">I'm your AI investment assistant, here to help you navigate the world of:</p>
                        <ul style="margin: 10px 0; padding-left: 20px;">
                            <li>📊 <strong>Stock Market Trading</strong></li>
                            <li>💰 <strong>Mutual Funds & SIP</strong></li>
                            <li>🏆 <strong>Wealth Creation Strategies</strong></li>
                            <li>🎯 <strong>Financial Goal Planning</strong></li>
                        </ul>
                        <p style="margin: 15px 0 0 0; color: #ffd700;">
                            <em>Every answer includes personalized guidance from CEO Muhammed Niyas!</em>
                        </p>
                    </div>
                </div>
            </div>

        </div>

        <!-- Input Area - LARGE -->
        <div style="padding: 25px; background: rgba(0,0,0,0.6); border-top: 2px solid #9370db;">
            <div style="display: flex; gap: 15px; max-width: 900px; margin: 0 auto;">
                <input type="text" id="userInput" placeholder="Type your investment question here..." 
                       style="flex: 1; padding: 18px 25px; border-radius: 35px; 
                              border: 3px solid #9370db; background: rgba(255,255,255,0.1); 
                              color: #fff; font-size: 1.1em; outline: none;"
                       onkeypress="if(event.key==='Enter')sendMessage()">
                <button onclick="sendMessage()" 
                        style="background: linear-gradient(135deg, #9370db 0%, #8a2be2 100%); 
                               border: none; padding: 18px 35px; border-radius: 35px; 
                               color: #fff; font-size: 1.2em; cursor: pointer; 
                               box-shadow: 0 5px 20px rgba(147,112,219,0.5);">
                    Send ➤
                </button>
            </div>
            <p style="color: #666; font-size: 0.85em; text-align: center; margin-top: 15px;">
                🤖 NSM AI Assistant | CEO: Muhammed Niyas | +966 50 154 1639 | Not financial advice
            </p>
        </div>

    </div>
</div>

<script>
// Toggle Full Screen Chat
function toggleAIChat() {
    const overlay = document.getElementById('aiChatOverlay');
    const btn = document.getElementById('aiAssistantBtn');
    
    if (overlay.style.display === 'none') {
        overlay.style.display = 'flex';
        btn.style.display = 'none';
        document.body.style.overflow = 'hidden'; // Prevent background scroll
    } else {
        overlay.style.display = 'none';
        btn.style.display = 'block';
        document.body.style.overflow = 'auto';
    }
}

// Send Message
function sendMessage() {
    const input = document.getElementById('userInput');
    const message = input.value.trim();
    
    if (message) {
        addUserMessage(message);
        input.value = '';
        
        setTimeout(() => {
            const response = getAIResponse(message);
            addAIMessage(response);
        }, 600);
    }
}

// Quick Ask
function askAI(question) {
    addUserMessage(question);
    setTimeout(() => {
        const response = getAIResponse(question);
        addAIMessage(response);
    }, 500);
}

// Add User Message - LARGE
function addUserMessage(text) {
    const chatArea = document.getElementById('chatArea');
    const div = document.createElement('div');
    div.style.cssText = 'margin-bottom: 20px; text-align: right;';
    div.innerHTML = `
        <div style="background: linear-gradient(135deg, #ffd700 0%, #ffed4e 100%); 
                    color: #1a1a2e; padding: 18px 25px; border-radius: 25px 25px 4px 25px; 
                    display: inline-block; max-width: 80%; font-size: 1.1em; font-weight: 500;
                    box-shadow: 0 5px 15px rgba(255,215,0,0.3);">
            ${text}
        </div>
    `;
    chatArea.appendChild(div);
    chatArea.scrollTop = chatArea.scrollHeight;
}

// Add AI Message - LARGE
function addAIMessage(text) {
    const chatArea = document.getElementById('chatArea');
    const div = document.createElement('div');
    div.style.cssText = 'margin-bottom: 20px;';
    div.innerHTML = `
        <div style="display: flex; align-items: flex-start; gap: 15px;">
            <div style="background: #9370db; width: 45px; height: 45px; border-radius: 50%; 
                        display: flex; align-items: center; justify-content: center; 
                        font-size: 1.5em; flex-shrink: 0; box-shadow: 0 5px 15px rgba(147,112,219,0.4);">
                🤖
            </div>
            <div style="background: rgba(147,112,219,0.15); padding: 22px; border-radius: 4px 25px 25px 25px; 
                        border-left: 4px solid #9370db; max-width: 82%; color: #fff; 
                        line-height: 1.9; font-size: 1.05em; box-shadow: 0 5px 20px rgba(0,0,0,0.3);">
                ${text}
            </div>
        </div>
    `;
    chatArea.appendChild(div);
    chatArea.scrollTop = chatArea.scrollHeight;
}

// AI Response Database - ALL WITH NSM HELPING
function getAIResponse(input) {
    const lowerInput = input.toLowerCase();
    
    if (lowerInput.includes('sip')) {
        return `<strong>📈 SIP (Systematic Investment Plan)</strong><br><br>
        SIP-ൽ每月固定 തുക mutual fund-ൽ invest ചെയ്യുന്നു.<br><br>
        <strong>പ്രയോജനങ്ങൾ:</strong><br>
        • Rupee Cost Averaging<br>
        • Compound Interest ശക്തി<br>
        • Financial Discipline<br><br>
        💡 <strong style="color: #00ff00;">How NSM Helps You:</strong><br>
        CEO Muhammed Niyas നിങ്ങളുടെ goals അനുസരിച്ച് best SIP select ചെയ്യാൻ help ചെയ്യും. 
        Risk profile analyze ചെയ്ത് perfect mutual funds suggest ചെയ്യുന്നു.<br><br>
        <a href="https://wa.me/966501541639" style="color: #ffd700; font-size: 1.1em;">👉 Contact NSM to Start SIP!</a>`;
    }
    
    if (lowerInput.includes('start') || lowerInput.includes('begin')) {
        return `<strong>🚀 Investment Journey ആരംഭിക്കാൻ</strong><br><br>
        <strong>Steps:</strong><br>
        1. Financial Goals നിർണ്ണയിക്കുക<br>
        2. Risk Tolerance മനസ്സിലാക്കുക<br>
        3. Investment Type തിരഞ്ഞെടുക്കുക<br>
        4. Small Amount മുതൽ തുടങ്ങുക<br>
        5. Consistent ആയി continue ചെയ്യുക<br><br>
        💡 <strong style="color: #00ff00;">NSM's Personal Guidance:</strong><br>
        CEO Muhammed Niyas beginners-ന് step-by-step support നൽകുന്നു. 
        Demat account മുതൽ first investment വരെ NSM Multi Invest ഒപ്പമുണ്ട്.<br><br>
        <a href="https://wa.me/966501541639" style="color: #ffd700; font-size: 1.1em;">👉 WhatsApp NSM Now!</a>`;
    }
    
    if (lowerInput.includes('best') || lowerInput.includes('good')) {
        return `<strong>🎯 Beginners-ക്ക് Best Investments</strong><br><br>
        • <strong>Mutual Funds (SIP)</strong> - കുറഞ്ഞ റിസ്ക്, നല്ല returns<br>
        • <strong>Index Funds</strong> - Market follow ചെയ്യും, കുറഞ്ഞ ചെലവ്<br>
        • <strong>Stock Market</strong> - പഠിച്ചാൽ ഉയർന്ന returns<br>
        • <strong>Gold/Silver</strong> - Safe haven asset<br><br>
        💡 <strong style="color: #00ff00;">NSM Customized Solutions:</strong><br>
        CEO Muhammed Niyas നിങ്ങളുടെ financial situation analyze ചെയ്ത് 
        perfect investment mix create ചെയ്യുന്നു. Maximum returns നേടാൻ NSM help ചെയ്യും!<br><br>
        <a href="https://wa.me/966501541639" style="color: #ffd700; font-size: 1.1em;">👉 Get Free Consultation!</a>`;
    }
    
    if (lowerInput.includes('stock') || lowerInput.includes('share')) {
        return `<strong>📊 Stock Market Investing</strong><br><br>
        <strong>അടിസ്ഥാനങ്ങൾ:</strong><br>
        • Company shares വാങ്ങുക<br>
        • Dividend & price rise-ൽ നിന്ന് ലാഭം<br>
        • Long-term wealth creation<br><br>
        ⚠️ <strong>റിസ്ക്:</strong> Market volatility ഉണ്ട്<br><br>
        💡 <strong style="color: #00ff00;">NSM Trading Expertise:</strong><br>
        CEO Muhammed Niyas-ന് 5+ വർഷത്തെ trading അനുഭവമുണ്ട്. NSM നൽകുന്നു:<br>
        • Daily trading tips<br>
        • Technical analysis<br>
        • Risk management strategies<br>
        • Portfolio guidance<br><br>
        <a href="https://wa.me/966501541639" style="color: #ffd700; font-size: 1.1em;">👉 Join NSM Trading Community!</a>`;
    }
    
    if (lowerInput.includes('contact') || lowerInput.includes('niyas') || lowerInput.includes('ceo')) {
        return `<strong>👋 Contact NSM CEO - Muhammed Niyas</strong><br><br>
        📱 <strong>WhatsApp:</strong> +966 50 154 1639<br>
        📧 <strong>Email:</strong> m73232599@gmail.com<br>
        📸 <strong>Instagram:</strong> @ni.yas946<br>
        🌐 <strong>Website:</strong> niyas-nsm<br>
        📍 <strong>Location:</strong> Kozhikode, Kerala<br><br>
        💼 <strong>Services:</strong><br>
        • Investment Consulting<br>
        • Stock Market Guidance<br>
        • Mutual Fund Planning<br>
        • Financial Education<br>
        • Trading Tips<br><br>
        <em style="color: #ffd700;">"Let NSM Multi Invest power up your financial future!"</em>`;
    }
    
    // Default
    return `<strong>🤔 Thanks for your question!</strong><br><br>
    "<strong>${input}</strong>" - ഇത് ഒരു മികച്ച investment topic ആണ്.<br><br>
    ഇതിനെക്കുറിച്ച് കൂടുതൽ അറിയാൻ CEO Muhammed Niyas-നെ നേരിട്ട് contact ചെയ്യുക.<br><br>
    💡 <strong style="color: #00ff00;">NSM Expert Consultation:</strong><br>
    CEO Muhammed Niyas one-on-one mentoring നൽകുന്നു. 
    5+ വർഷത്തെ stock market & multi-sector investment അനുഭവം.<br><br>
    📱 <a href="https://wa.me/966501541639" style="color: #ffd700; font-size: 1.1em;">👉 WhatsApp CEO Niyas Now</a><br>
    📧 <a href="mailto:m73232599@gmail.com" style="color: #00bfff;">👉 Send Email</a><br><br>
    <em style="color: #9370db;">"NSM - Power Up Your Investments!"</em>`;
}
</script><!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NSM Multi Invest</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: #0a0a1a;
            font-family: Arial, sans-serif;
            overflow: hidden;
        }
        
        .container {
            width: 100vw;
            height: 100vh;
            display: flex;
            flex-direction: column;
        }
        
        /* Title */
        .header {
            text-align: center;
            padding: 20px;
            background: linear-gradient(90deg, #0f0f23, #1a1a3e, #0f0f23);
        }
        
        .header h1 {
            color: #fff;
            font-size: 2.5em;
            letter-spacing: 10px;
            text-shadow: 0 0 20px rgba(0,200,255,0.5);
        }
        
        /* Videos */
        .videos {
            flex: 1;
            display: flex;
        }
        
        .video-box {
            flex: 1;
            position: relative;
        }
        
        .video-box iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="header">
            <h1>NSM MULTI INVEST</h1>
        </div>
        
        <div class="videos">
            <div class="video-box">
                <iframe 
                    src="https://www.youtube.com/embed/y0zSL01oywQ?autoplay=1&mute=1&loop=1&playlist=y0zSL01oywQ" 
                    allow="autoplay; encrypted-media" 
                    allowfullscreen>
                </iframe>
            </div>
            
            <div class="video-box">
                <iframe 
                    src="https://www.youtube.com/embed/BzTwqkOc3dY?autoplay=1&mute=1&loop=1&playlist=BzTwqkOc3dY" 
                    allow="autoplay; encrypted-media" 
                    allowfullscreen>
                </iframe>
            </div>
        </div>
    </div>

</body>
</html>
