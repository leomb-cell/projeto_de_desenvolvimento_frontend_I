## E-Parking - seu guia de estacionamentos

<p>
    O E-Parking é uma plataforma desenvolvida para facilitar a localização e reserva de vagas de estacionamento em grandes centros urbanos. A solução permite que motoristas encontrem estacionamentos próximos ao seu destino, consultem disponibilidade, preços, horários, acessibilidade e avaliações, além de realizarem reservas antecipadamente.
</p>

<p>
    Para proprietários e gestores, a plataforma oferece recursos para gerenciar a ocupação das vagas em tempo real, melhorar o fluxo de entrada e saída e otimizar a utilização dos espaços disponíveis.
</p>

<p>
    O projeto também planeja explorar tecnologias de visão computacional, utilizando ferramentas como OpenCV e modelos YOLO, com o objetivo de identificar veículos, controlar o fluxo e monitorar a disponibilidade de vagas por meio da infraestrutura de câmeras já existente nos estacionamentos.
</p>

# Time da Persona "Proprietários"
<table>
    <thead>
        <tr>
            <th>
                <h3>Alunos</h3>
            </th>
            <th>
                <h3>GitHub</h3>
            </th>
        </tr> 
    </thead>
    <tbody>
        <tr>
            <td>Leonardo M. Bitencourte</td>    
            <td><a>https://github.com/leomb-cell</a></td>
        </tr>
        <tr>
            <td>Eduardo Manhães</td>    
            <td><a>https://github.com/Lalodev08</a></td>
        </tr>
        <tr>
            <td>Nicolas Barreiros</td>    
            <td><a>https://github.com/</a></td>
        </tr>
            <tr>
            <td>Giovana Ribero</td>    
            <td><a>https://github.com/GiovanaRibero</a></td>
        </tr>
    </tbody>
</table>     

# Time da Persona "Motoristas"
<table>
    <thead>
        <tr>
            <th>
                <h3>Alunos</h3>
            </th>
            <th>
                <h3>GitHub</h3>
            </th>
        </tr> 
    </thead>
    <tbody>
        <tr>
            <td>Nicollas Bion</td>    
            <td><a>https://github.com/</a></td>
        </tr>
        <tr>
            <td>Vitor Shultz</td>    
            <td><a>https://github.com/</a></td>
        </tr>
        <tr>
            <td>Erik Prade</td>    
            <td><a>https://github.com/ErikPrade</a></td>
        </tr>
        <tr>
            <td>Pedro H. Gazzoni</td>    
            <td><a>https://github.com/</a></td>
        </tr>
    </tbody>
</table>

# Tecnologias 

<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>Bootstrap</li>
    <li>JavaScript (DOM, eventos, validações e localStorage)</li>
</ul>

# Paleta de cores

<table>
    <thead>
        <tr>
            <th>
                <h3>Categoria</h3>
            </th>
            <th>
                <h3>Nome</h3>
            </th>
            <th>
                <h3>Codigo Hex</h3>
            </th>
        </tr> 
    </thead>
    <tbody>
        <tr>
            <td>Cor Principal</td>    
            <td>Azul Profundo</td>
            <td>#123B5D</td>
        </tr>
        <tr>
            <td>Cor de destaque</td>    
            <td>Azul Vivo</td>
            <td>#1976A8</td>
        </tr>
        <tr>
            <td>Cor de Fundo</td>    
            <td>Branco</td>
            <td>#FFFFFF</td>
        </tr>
    </tbody>
</table>    

# Fonte

Inter - <a href="https://fonts.google.com/share?selection.family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900"> 
Google Fonts
</a>

# Como rodar o projeto

Não precisa instalar nada.

1. Baixe o repositório: botão **Code → Download ZIP** (ou `git clone https://github.com/leomb-cell/projeto_de_desenvolvimento_frontend_I.git`).
2. Abra no navegador o arquivo da área desejada:
   - Motoristas: `drivers_landing_page/index.html`
   - Proprietários: `owners_landing_page/index.html`
3. Opcional: no VS Code, use a extensão **Live Server** (botão direito no `index.html` → *Open with Live Server*).

Os dados (usuários e reservas) ficam salvos no **localStorage** do navegador. Para começar do zero, abra o F12 → *Application* → *Local Storage* e apague as chaves `eparking_*`.

# Área do Motorista — Sprint 2 (JavaScript)

Fluxo: **Início (busca)** → **Resultados** → **Estacionamento** → **Pagamento** → **Confirmação** → **Minhas reservas**, além de **Cadastro** e **Login**.

| Página | O que o JavaScript faz |
|---|---|
| Início | Valida destino, data (não aceita data passada) e horário; mostra o usuário logado no cabeçalho |
| Cadastro | Valida nome e sobrenome, CPF (dígitos verificadores, com máscara), e-mail, senha (mín. 6) e confirmação; salva o usuário no localStorage |
| Login | Confere e-mail e senha com os usuários salvos e inicia a sessão; volta para a página onde o motorista estava |
| Resultados | Gera os cards dos estacionamentos a partir de um array, com filtros (Coberto, 24 horas, Acessível) e ordenação |
| Estacionamento | Carrega os dados pelo id da URL, calcula o total pela duração e valida a reserva |
| Pagamento | Cartão (16 dígitos, validade MM/AA não vencida, CVV), PIX ou pagamento no local; exige login e salva a reserva |
| Confirmação | Mostra a reserva salva com o código gerado |
| Minhas reservas | **CRUD local**: lista, edita (data, horário e duração, recalculando o valor) e cancela reservas |

**CRUD de reservas (localStorage):** *Create* no pagamento, *Read* em Minhas reservas e na confirmação, *Update* no botão **Editar** e *Delete* no botão **Cancelar**.

### Organização dos arquivos (motoristas)

```
drivers_landing_page/
├── index.html
├── pages/<pagina>/        HTML, CSS e JS de cada página
├── static/css/            index.css e feedback.css (mensagens de validação)
├── static/js/             storage.js (localStorage), validation.js, parkings.js (dados), index.js
└── sprint_templates/      relatórios das sprints
```
