<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pesquisa de Satisfação</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #4169E1;
        }
        .container {
            max-width: 600px;
            margin: auto;
            background: white;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }
        .logo {
            display: flex;
            justify-content: center;
            margin-bottom: 20px;
        }
        .logo img {
            max-width: 100%;
            height: auto;
            border-radius: 8px;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        .question {
            margin-bottom: 20px;
        }
        .question p {
            margin-bottom: 10px;
            font-weight: bold;
        }
        .options {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }
        .options label {
            display: flex;
            align-items: center;
            margin-bottom: 5px;
        }
        .options input {
            margin-right: 5px;
        }
        button {
            display: block;
            width: 100%;
            padding: 10px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #0056b3;
        }
        .suggestions, .email {
            margin-top: 20px;
        }
        .suggestions h2, .email h2 {
            margin-top: 0;
        }
        .suggestions textarea, .email input {
            width: 100%;
            padding: 10px;
            border-radius: 4px;
            border: 1px solid #ccc;
            margin-top: 10px;
            box-sizing: border-box;
        }
        .email input {
            margin-bottom: 20px;
        }
        .responses {
            margin-top: 20px;
            padding: 20px;
            background-color: #f9f9f9;
            border-radius: 8px;
            display: none; /* Hide responses initially */
        }
        .responses h2 {
            margin-top: 0;
        }
        .response {
            margin-bottom: 10px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            background-color: white;
        }
        #password-prompt {
            display: none;
            text-align: center;
            padding: 20px;
            background-color: white;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }
        #password-prompt input {
            padding: 10px;
            border-radius: 4px;
            border: 1px solid #ccc;
            margin-top: 10px;
            width: calc(100% - 22px);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="logo">
            <img src="https://i.postimg.cc/d7qbkdwX/logo-cer-II-2.png" alt="Logo CER">
        </div>
        <h1>Pesquisa de Satisfação</h1>
        <form id="survey-form">
            <div class="question">
                <p>1. Como você avalia a estrutura física da nossa unidade?</p>
                <div class="options">
                    <label><input type="radio" name="estrutura_fisica" value="1" required> 1</label>
                    <label><input type="radio" name="estrutura_fisica" value="2"> 2</label>
                    <label><input type="radio" name="estrutura_fisica" value="3"> 3</label>
                    <label><input type="radio" name="estrutura_fisica" value="4"> 4</label>
                    <label><input type="radio" name="estrutura_fisica" value="5"> 5</label>
                </div>
            </div>
            <div class="question">
                <p>2. Como você avalia a limpeza da nossa unidade?</p>
                <div class="options">
                    <label><input type="radio" name="limpeza" value="1" required> 1</label>
                    <label><input type="radio" name="limpeza" value="2"> 2</label>
                    <label><input type="radio" name="limpeza" value="3"> 3</label>
                    <label><input type="radio" name="limpeza" value="4"> 4</label>
                    <label><input type="radio" name="limpeza" value="5"> 5</label>
                </div>
            </div>
            <div class="question">
                <p>3. Como você avalia o atendimento da recepção?</p>
                <div class="options">
                    <label><input type="radio" name="atendimento_recepcao" value="1" required> 1</label>
                    <label><input type="radio" name="atendimento_recepcao" value="2"> 2</label>
                    <label><input type="radio" name="atendimento_recepcao" value="3"> 3</label>
                    <label><input type="radio" name="atendimento_recepcao" value="4"> 4</label>
                    <label><input type="radio" name="atendimento_recepcao" value="5"> 5</label>
                </div>
            </div>
            <div class="question">
                <p>4. Como você avalia a cordialidade dos profissionais da unidade?</p>
                <div class="options">
                    <label><input type="radio" name="cordialidade_profissionais" value="1" required> 1</label>
                    <label><input type="radio" name="cordialidade_profissionais" value="2"> 2</label>
                    <label><input type="radio" name="cordialidade_profissionais" value="3"> 3</label>
                    <label><input type="radio" name="cordialidade_profissionais" value="4"> 4</label>
                    <label><input type="radio" name="cordialidade_profissionais" value="5"> 5</label>
                </div>
            </div>
            <div class="question">
                <p>5. Como você avalia a competência dos profissionais da unidade?</p>
                <div class="options">
                    <label><input type="radio" name="competencia_profissionais" value="1" required> 1</label>
                    <label><input type="radio" name="competencia_profissionais" value="2"> 2</label>
                    <label><input type="radio" name="competencia_profissionais" value="3"> 3</label>
                    <label><input type="radio" name="competencia_profissionais" value="4"> 4</label>
                    <label><input type="radio" name="competencia_profissionais" value="5"> 5</label>
                </div>
            </div>
            <div class="email">
                <h2>Email para devolutiva</h2>
                <input type="email" name="email" placeholder="Digite seu email (opcional)">
            </div>
            <div class="suggestions">
                <h2>Sugestões</h2>
                <p>Se você tiver alguma sugestão para melhorar nossos serviços, por favor, escreva abaixo:</p>
                <textarea name="sugestoes" rows="4"></textarea>
            </div>
            <button type="submit">Enviar</button>
        </form>
        <div id="password-prompt">
            <h2>Digite a senha para ver as respostas:</h2>
            <input type="password" id="password-input" placeholder="Senha">
            <button onclick="checkPassword()">Entrar</button>
        </div>
        <div class="responses" id="responses-section">
            <h2>Respostas Registradas</h2>
            <div id="responses-list"></div>
        </div>
    </div>
    <script>
        const correctPassword = 'admcer321';

        document.getElementById('survey-form').addEventListener('submit', function(event) {
            event.preventDefault();
            const formData = new FormData(this);
            const response = {};
            formData.forEach((value, key) => {
                response[key] = value;
            });

            let responses = JSON.parse(localStorage.getItem('responses')) || [];
            responses.push(response);
            localStorage.setItem('responses', JSON.stringify(responses));
            alert('Resposta enviada com sucesso!');
            this.reset();
        });

        function checkPassword() {
            const password = document.getElementById('password-input').value;
            if (password === correctPassword) {
                document.getElementById('password-prompt').style.display = 'none';
                document.getElementById('responses-section').style.display = 'block';
                displayResponses();
            } else {
                alert('Senha incorreta!');
            }
        }

        function displayResponses() {
            const responses = JSON.parse(localStorage.getItem('responses')) || [];
            const responsesList = document.getElementById('responses-list');
            responsesList.innerHTML = '';
            responses.forEach((response, index) => {
                const responseDiv = document.createElement('div');
                responseDiv.classList.add('response');
                responseDiv.innerHTML = `
                    <p><strong>Resposta ${index + 1}:</strong></p>
                    <p><strong>Estrutura Física:</strong> ${response.estrutura_fisica}</p>
                    <p><strong>Limpeza:</strong> ${response.limpeza}</p>
                    <p><strong>Atendimento Recepção:</strong> ${response.atendimento_recepcao}</p>
                    <p><strong>Cordialidade Profissionais:</strong> ${response.cordialidade_profissionais}</p>
                    <p><strong>Competência Profissionais:</strong> ${response.competencia_profissionais}</p>
                    <p><strong>Email:</strong> ${response.email || 'Não fornecido'}</p>
                    <p><strong>Sugestões:</strong> ${response.sugestoes || 'Nenhuma'}</p>
                `;
                responsesList.appendChild(responseDiv);
            });
        }

        window.onload = function() {
            document.getElementById('password-prompt').style.display = 'block';
        };
    </script>
</body>
</html>
