<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minha Página</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            margin: 0;
            padding: 0;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
        }

        .container {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 50px;
            box-shadow: 0 8px 32px rgba(31, 38, 135, 0.37);
            border: 1px solid rgba(255, 255, 255, 0.18);
            max-width: 600px;
            animation: fadeInUp 1s ease-out;
        }

        .logo {
            width: 150px;
            height: 150px;
            background: linear-gradient(135deg, #808080, #606060);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 30px;
            position: relative;
            font-size: 48px;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            box-shadow: 0 10px 30px rgba(0,0,0,0.3);
            animation: pulse 2s infinite;
        }

        .logo-text {
            display: flex;
            align-items: center;
            gap: 2px;
        }

        .p-letter {
            color: #ff4444;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .c-letter {
            color: #44ff44;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        .coroa {
            position: absolute;
            top: -80px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 90px;
            color: #ffd700;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% {
                transform: translateX(-50%) translateY(0px);
            }
            50% {
                transform: translateX(-50%) translateY(-5px);
            }
        }

        .texto-principal {
            font-size: 32px;
            font-weight: bold;
            margin: 30px 0;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            animation: slideInLeft 1s ease-out 0.5s both;
        }

        .texto-secundario {
            font-size: 18px;
            line-height: 1.6;
            opacity: 0.9;
            animation: slideInRight 1s ease-out 1s both;
        }

        .botao-ideias {
            background: linear-gradient(135deg, #ff6b6b, #ee5a6f);
            border: none;
            padding: 15px 30px;
            border-radius: 50px;
            color: white;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            margin-top: 30px;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(255, 107, 107, 0.4);
            animation: slideInUp 1s ease-out 1.5s both;
        }

        .botao-ideias:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(255, 107, 107, 0.6);
            background: linear-gradient(135deg, #ff5252, #e91e63);
        }

        .botao-ideias:active {
            transform: translateY(-1px);
        }

        /* Estilos para a página de ideias */
        .pagina-ideias {
            display: none;
            max-width: 1200px;
            padding: 30px;
        }

        .pagina-ideias.ativa {
            display: block;
        }

        .conteudo-ideias {
            display: grid;
            grid-template-columns: 1fr 400px;
            gap: 40px;
            align-items: start;
        }

        .formulario-ideias {
            text-align: left;
        }

        .tabela-precos {
            background: rgba(255, 255, 255, 0.15);
            border-radius: 20px;
            padding: 25px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 8px 32px rgba(31, 38, 135, 0.2);
            animation: slideInRight 1s ease-out 0.3s both;
        }

        .titulo-precos {
            font-size: 24px;
            font-weight: bold;
            margin-bottom: 20px;
            text-align: center;
            color: #ffd700;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .item-preco {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 20px;
            margin-bottom: 12px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            border-left: 4px solid;
            transition: all 0.3s ease;
            backdrop-filter: blur(5px);
        }

        .item-preco:hover {
            transform: translateX(5px);
            background: rgba(255, 255, 255, 0.2);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .item-preco.pequeno {
            border-left-color: #4ade80;
            animation: slideInLeft 1s ease-out 0.5s both;
        }

        .item-preco.medio {
            border-left-color: #fbbf24;
            animation: slideInLeft 1s ease-out 0.7s both;
        }

        .item-preco.grande {
            border-left-color: #f87171;
            animation: slideInLeft 1s ease-out 0.9s both;
        }

        .item-preco.acessorio {
            border-left-color: #a855f7;
            animation: slideInLeft 1s ease-out 1.1s both;
        }

        .nome-produto {
            font-weight: bold;
            font-size: 16px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .preco {
            font-size: 18px;
            font-weight: bold;
            color: #4ade80;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.3);
        }

        .descricao-produto {
            font-size: 12px;
            opacity: 0.8;
            margin-top: 2px;
        }

        .info-adicional {
            margin-top: 20px;
            padding: 15px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            border-left: 3px solid #60a5fa;
            animation: slideInUp 1s ease-out 1.3s both;
        }

        .info-adicional h4 {
            margin: 0 0 8px 0;
            color: #60a5fa;
            font-size: 14px;
        }

        .info-adicional p {
            margin: 0;
            font-size: 13px;
            opacity: 0.9;
            line-height: 1.4;
        }

        /* Estilos para a página de agradecimento */
        .pagina-agradecimento {
            display: none;
            max-width: 600px;
            padding: 50px;
            text-align: center;
        }

        .pagina-agradecimento.ativa {
            display: block;
            animation: fadeInScale 0.8s ease-out;
        }

        .icone-sucesso {
            font-size: 80px;
            margin-bottom: 20px;
            animation: bounceIn 1s ease-out 0.3s both;
        }

        .titulo-agradecimento {
            font-size: 32px;
            font-weight: bold;
            margin-bottom: 20px;
            color: #4ade80;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            animation: slideInDown 0.8s ease-out 0.5s both;
        }

        .mensagem-agradecimento {
            font-size: 18px;
            line-height: 1.6;
            opacity: 0.95;
            margin-bottom: 30px;
            animation: slideInUp 0.8s ease-out 0.7s both;
        }

        .resumo-ideia {
            background: rgba(255, 255, 255, 0.15);
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
            border-left: 4px solid #4ade80;
            animation: slideInLeft 0.8s ease-out 0.9s both;
        }

        .resumo-ideia h4 {
            margin: 0 0 10px 0;
            color: #4ade80;
            font-size: 16px;
        }

        .resumo-ideia p {
            margin: 0;
            font-style: italic;
            opacity: 0.9;
        }

        .botao-nova-ideia {
            background: linear-gradient(135deg, #ff6b6b, #ee5a6f);
            border: none;
            padding: 15px 30px;
            border-radius: 50px;
            color: white;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(255, 107, 107, 0.4);
            margin-right: 15px;
            animation: slideInUp 0.8s ease-out 1.1s both;
        }

        .botao-nova-ideia:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(255, 107, 107, 0.6);
        }

        .botao-inicio {
            background: linear-gradient(135deg, #4facfe, #00f2fe);
            border: none;
            padding: 15px 30px;
            border-radius: 50px;
            color: white;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(79, 172, 254, 0.4);
            animation: slideInUp 0.8s ease-out 1.3s both;
        }

        .botao-inicio:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(79, 172, 254, 0.6);
        }

        .titulo-ideias {
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 20px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .texto-ideias {
            font-size: 16px;
            line-height: 1.6;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        .campo-nome, .caixa-ideias {
            width: 100%;
            padding: 15px 20px;
            border: none;
            border-radius: 15px;
            background: rgba(255, 255, 255, 0.9);
            color: #333;
            font-size: 16px;
            font-family: 'Arial', sans-serif;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            margin-bottom: 20px;
            box-sizing: border-box;
        }

        .caixa-ideias {
            min-height: 150px;
            resize: vertical;
        }

        .campo-nome::placeholder,
        .caixa-ideias::placeholder {
            color: #666;
        }

        .campo-nome:focus,
        .caixa-ideias:focus {
            outline: none;
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
        }

        .botao-voltar {
            background: linear-gradient(135deg, #4facfe, #00f2fe);
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            color: white;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(79, 172, 254, 0.4);
            margin-right: 15px;
        }

        .botao-voltar:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(79, 172, 254, 0.6);
        }

        .botao-enviar {
            background: linear-gradient(135deg, #56ab2f, #a8e6cf);
            border: none;
            padding: 12px 25px;
            border-radius: 50px;
            color: white;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(86, 171, 47, 0.4);
        }

        .botao-enviar:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(86, 171, 47, 0.6);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.05);
            }
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from {
                opacity: 0;
                transform: translateX(50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInScale {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        @keyframes bounceIn {
            0% {
                opacity: 0;
                transform: scale(0.3);
            }
            50% {
                opacity: 1;
                transform: scale(1.1);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }

        @keyframes slideInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media (max-width: 768px) {
            .container {
                margin: 20px;
                padding: 30px;
            }
            
            .logo {
                width: 120px;
                height: 120px;
                font-size: 36px;
            }

            .coroa {
                font-size: 24px;
                top: -15px;
            }
            
            .texto-principal {
                font-size: 24px;
            }
            
            .texto-secundario {
                font-size: 16px;
            }

            .botao-ideias {
                font-size: 16px;
                padding: 12px 25px;
            }

            .pagina-ideias {
                padding: 20px;
            }

            .conteudo-ideias {
                grid-template-columns: 1fr;
                gap: 30px;
            }

            .tabela-precos {
                order: -1;
            }

            .titulo-ideias {
                font-size: 24px;
            }

            .titulo-precos {
                font-size: 20px;
            }

            .item-preco {
                padding: 12px 15px;
            }

            .nome-produto {
                font-size: 14px;
            }

            .preco {
                font-size: 16px;
            }
        }
    </style>
</head>
<body>
    <!-- Página Principal -->
    <div class="container" id="paginaPrincipal">
        <div class="logo">
            <div class="coroa">👑</div>
            <div class="logo-text">
                <span class="p-letter">P</span><span class="c-letter">C</span>
            </div>
        </div>
        
        <div class="texto-principal">
            Bem-vindo ao Pop Caseiro
        </div>
        
        <div class="texto-secundario">
            Somos uma empresa inovadora focada em oferecer produtos criativos e de alta qualidade para nossos clientes. Nossa missão é transformar ideias em realidade através da criatividade e dedicação.
        </div>

        <button class="botao-ideias" onclick="abrirPaginaIdeias()">
            💡 Compartilhe sua Ideia
        </button>
    </div>

    <!-- Página de Ideias -->
    <div class="container pagina-ideias" id="paginaIdeias">
        <div class="conteudo-ideias">
            <div class="formulario-ideias">
                <div class="titulo-ideias">
                    🌟 Compartilhe suas Ideias Conosco!
                </div>
                
                <div class="texto-ideias">
                    Acreditamos que as melhores inovações nascem da colaboração e criatividade. Queremos ouvir suas ideias, sugestões e visões para produtos únicos. Seja uma receita especial, um conceito criativo ou uma melhoria para nossos serviços - toda ideia é valiosa para nós!
                    <br><br>
                    Conte-nos o que você tem em mente e vamos transformar juntos suas ideias em realidade.
                </div>

                <input 
                    type="text" 
                    class="campo-nome" 
                    placeholder="Seu nome (opcional)" 
                    id="campoNome"
                />

                <textarea 
                    class="caixa-ideias" 
                    placeholder="Digite sua ideia aqui... Seja criativo! Queremos saber sobre seus sonhos, conceitos, receitas, melhorias ou qualquer coisa que você acredita que poderia ser incrível!"
                    id="caixaTexto"
                ></textarea>

                <div>
                    <button class="botao-voltar" onclick="voltarPaginaPrincipal()">
                        ← Voltar
                    </button>
                    <button class="botao-enviar" id="botaoEnviar" onclick="enviarIdeia()">
                        Enviar Ideia ✨
                    </button>
                </div>
            </div>

            <div class="tabela-precos">
                <div class="titulo-precos">💰 Tabela de Preços</div>
                
                <div class="item-preco pequeno">
                    <div>
                        <div class="nome-produto">🧸 Boneco Pequeno</div>
                        <div class="descricao-produto">Até 15cm de altura</div>
                    </div>
                    <div class="preco">R$ 4,50</div>
                </div>

                <div class="item-preco medio">
                    <div>
                        <div class="nome-produto">🎪 Boneco Médio</div>
                        <div class="descricao-produto">16cm a 25cm de altura</div>
                    </div>
                    <div class="preco">R$ 6,50</div>
                </div>

                <div class="item-preco grande">
                    <div>
                        <div class="nome-produto">🎨 Boneco Grande</div>
                        <div class="descricao-produto">26cm ou mais de altura</div>
                    </div>
                    <div class="preco">R$ 9,50</div>
                </div>

                <div class="item-preco acessorio">
                    <div>
                        <div class="nome-produto">✨ Acessórios</div>
                        <div class="descricao-produto">Por unidade adicional</div>
                    </div>
                    <div class="preco">R$ 0,50</div>
                </div>

                <div class="info-adicional">
                    <h4>ℹ️ Informações Importantes</h4>
                    <p>• Preços podem variar conforme complexidade<br>
                    • Acessórios incluem chapéus, óculos, objetos, etc.<br>
                    • Personalizações especiais sob consulta<br>
                    • Coloque como você quer o boneco na barra de dar ideias<br>
                    • Prazo de entrega: 7 a 15 dias úteis</p>
                </div>
            </div>
        </div>
    </div>

    <!-- Página de Instruções de Envio -->
    <div class="container pagina-agradecimento" id="paginaInstrucoes">
        <div class="icone-sucesso">📧</div>
        
        <div class="titulo-agradecimento">
            Como Enviar sua Ideia
        </div>
        
        <div class="mensagem-agradecimento">
            Para enviar sua ideia, copie o texto abaixo e envie um email para nossa equipe:
        </div>

        <div class="resumo-ideia">
            <h4>📋 Copie este texto e envie por email:</h4>
            <textarea readonly id="emailInstrucoes" style="width: 100%; height: 200px; padding: 15px; border-radius: 10px; border: 2px solid #4ade80; background: rgba(255,255,255,0.9); color: #333; font-family: monospace; font-size: 14px; resize: none;"></textarea>
        </div>

        <div style="margin: 20px 0;">
            <button onclick="copiarTexto()" style="background: linear-gradient(135deg, #4ade80, #22c55e); border: none; padding: 12px 25px; border-radius: 50px; color: white; font-size: 16px; font-weight: bold; cursor: pointer; margin-right: 15px; box-shadow: 0 5px 15px rgba(74, 222, 128, 0.4);">
                📋 Copiar Texto
            </button>
            <button onclick="abrirEmail()" style="background: linear-gradient(135deg, #3b82f6, #1d4ed8); border: none; padding: 12px 25px; border-radius: 50px; color: white; font-size: 16px; font-weight: bold; cursor: pointer; box-shadow: 0 5px 15px rgba(59, 130, 246, 0.4);">
                ✉️ Abrir Gmail
            </button>
        </div>

        <div>
            <button class="botao-nova-ideia" onclick="novaIdeiaFromInstrucoes()">
                💡 Nova Ideia
            </button>
            <button class="botao-inicio" onclick="voltarInicioFromInstrucoes()">
                🏠 Voltar ao Início
            </button>
        </div>
    </div>

    <!-- Página de Agradecimento -->
    <div class="container pagina-agradecimento" id="paginaAgradecimento">
        <div class="icone-sucesso">🎉</div>
        
        <div class="titulo-agradecimento">
            Ideia Enviada com Sucesso!
        </div>
        
        <div class="mensagem-agradecimento">
            Muito obrigado por compartilhar sua criatividade conosco! Sua ideia foi enviada para nossa equipe e é muito valiosa para nós.
            <br><br>
            Nossa equipe irá analisar sua sugestão com carinho e, em breve, entraremos em contato para discutir as possibilidades de transformá-la em realidade.
        </div>

        <div class="resumo-ideia" id="resumoIdeia">
            <h4>📝 Sua ideia:</h4>
            <p id="textoIdeiaResumo"></p>
        </div>

        <div>
            <button class="botao-nova-ideia" onclick="novaIdeia()">
                💡 Enviar Nova Ideia
            </button>
            <button class="botao-inicio" onclick="voltarInicio()">
                🏠 Voltar ao Início
            </button>
        </div>
    </div>

    <script>
        function abrirPaginaIdeias() {
            document.getElementById('paginaPrincipal').style.display = 'none';
            document.getElementById('paginaIdeias').classList.add('ativa');
        }

        function voltarPaginaPrincipal() {
            document.getElementById('paginaIdeias').classList.remove('ativa');
            document.getElementById('paginaPrincipal').style.display = 'block';
        }

        function enviarIdeia() {
            const textoIdeia = document.getElementById('caixaTexto').value.trim();
            const nomeUsuario = document.getElementById('campoNome').value.trim();
            
            if (textoIdeia === '') {
                alert('Por favor, digite sua ideia antes de enviar! 😊');
                return;
            }

            // Salva a ideia localmente (simulando envio)
            const dataHora = new Date().toLocaleString('pt-BR');
            const remetente = nomeUsuario || 'Usuário Anônimo';
            
            // Cria o conteúdo da ideia para mostrar na página de instruções
            const ideiaCompleta = {
                nome: remetente,
                ideia: textoIdeia,
                data: dataHora
            };
            
            // Salva temporariamente
            window.ideiaAtual = ideiaCompleta;
            
            // Vai para página de instruções de envio
            document.getElementById('paginaIdeias').classList.remove('ativa');
            document.getElementById('paginaInstrucoes').classList.add('ativa');
            
            // Preenche as informações na página de instruções
            document.getElementById('emailInstrucoes').textContent = 
                `Para: popcaseiropc@gmail.com
Assunto: Nova Ideia - Pop Caseiro

Nova ideia recebida:

📅 Data/Hora: ${dataHora}
👤 Nome: ${remetente}

💡 IDEIA:
${textoIdeia}

---
Enviado através do site Pop Caseiro`;
            
            // Limpa os campos para próxima ideia
            document.getElementById('caixaTexto').value = '';
            document.getElementById('campoNome').value = '';
        }

        function novaIdeia() {
            document.getElementById('paginaAgradecimento').classList.remove('ativa');
            document.getElementById('paginaIdeias').classList.add('ativa');
        }

        function voltarInicio() {
            document.getElementById('paginaAgradecimento').classList.remove('ativa');
            document.getElementById('paginaPrincipal').style.display = 'block';
        }

        function novaIdeiaFromInstrucoes() {
            document.getElementById('paginaInstrucoes').classList.remove('ativa');
            document.getElementById('paginaIdeias').classList.add('ativa');
        }

        function voltarInicioFromInstrucoes() {
            document.getElementById('paginaInstrucoes').classList.remove('ativa');
            document.getElementById('paginaPrincipal').style.display = 'block';
        }

        function copiarTexto() {
            const textarea = document.getElementById('emailInstrucoes');
            textarea.select();
            textarea.setSelectionRange(0, 99999); // Para dispositivos móveis
            
            try {
                document.execCommand('copy');
                // Feedback visual
                const botao = event.target;
                const textoOriginal = botao.textContent;
                botao.textContent = '✅ Copiado!';
                botao.style.background = 'linear-gradient(135deg, #22c55e, #16a34a)';
                
                setTimeout(() => {
                    botao.textContent = textoOriginal;
                    botao.style.background = 'linear-gradient(135deg, #4ade80, #22c55e)';
                }, 2000);
            } catch (err) {
                alert('Não foi possível copiar automaticamente. Por favor, selecione e copie o texto manualmente.');
            }
        }

        function abrirEmail() {
            window.open('https://mail.google.com/mail/?view=cm&to=popcaseiropc@gmail.com', '_blank');
        }

        function confirmarEnvio() {
            if (window.ideiaAtual) {
                document.getElementById('textoIdeiaResumo').textContent = window.ideiaAtual.ideia;
                document.getElementById('paginaInstrucoes').classList.remove('ativa');
                document.getElementById('paginaAgradecimento').classList.add('ativa');
            }
        }

        // Adiciona funcionalidade de Enter + Ctrl para enviar
        document.addEventListener('DOMContentLoaded', function() {
            const caixaTexto = document.getElementById('caixaTexto');
            if (caixaTexto) {
                caixaTexto.addEventListener('keydown', function(e) {
                    if (e.ctrlKey && e.key === 'Enter') {
                        enviarIdeia();
                    }
                });
            }
        });
    </script>
</body>
</html>
