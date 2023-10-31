# front-end
joaoth@17

style.css

body {
    font-family: "Source Sans 3";
    color: #323232;
}

.content {
    width: 100%;
    max-width: 1280px;
    box-sizing: border-box;
    justify-content: center;
}

.center {
    justify-content: center;
    align-items: center;
}

.flex {
    display: flex;
}

.full {
    min-height: 100vh;
    background: #FFFFFF;
}

.bg-img {
    background-image: 
        linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.3)), 
        url(../images/PalomaRincon.jpg);
    background-size: cover;
}

.logo-wrapper {
    display: none;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    gap: 0.75rem;

    color: #f4f4f4;
    font-weight: 300;
    font-size: 1.25rem;
}

.logo-wrapper img {
    height: 2.5rem;
}

.form-wrapper {
    display: flex;
    flex-direction: column;

    background-color: #FFFFFF;

    box-sizing: border-box;
    padding-top: 1.5rem;
    padding-bottom: 2.5rem;
    padding-left: 1rem;
    padding-right: 1rem;

    width: 100%;
}

.mb-1 {
    margin-bottom: 0.5rem;
}

.form-logo {
    filter: brightness(0);
    height: 18px;
}

.form-title {
    font-weight: 600;
    font-size: 2.25rem;
    line-height: 1.2em;
    margin-bottom: 0.5rem;
}

.form-new-user {
    font-weight: 400;
    line-height: 1.5;

    margin-bottom: 2rem;
}

.form-new-user a,
.form-actions a,
.sign-in-help a {
    color: #1473e6;
    text-decoration: none;
}

.form-new-user a:hover,
.form-actions a:hover,
.sign-in-help a:hover {
    text-decoration: underline;
    cursor: pointer;
}

.form-group {
    display: flex;
    flex-direction: column;
}

.hidden {
    display: none;
}

.relative {
    position: relative;
}

.form-group:not(:last-of-type) {  
    margin-bottom: 1rem;
}

.form-group label {
    font-size: 0.75rem;
    color: #272727;
}

.form-group input {
    width: 100%;
    font-size: 1.25rem;
    border: none;
    border-bottom: 1px solid #eaeaea;
    transition: border-color 0.3s, box-shadow 0.3s;
    box-shadow: 0 1px 0 transparent;
    outline: none;
}

.form-group input.focus {
    border-color: #1473e6;
}

#toggle-password {
    position: absolute;
    top: 50%;
    right: 8px;
    transform: translateY(-50%);

    display: flex;
    padding: 0.5rem;
    width: fit-content;
    height: fit-content;
    justify-content: center;
    align-items: center;
}

#toggle-password.toggle-password::after {
    position: absolute;
    display: block;
    content: '👁';
}

#toggle-password.toggle-text::after {
    position: absolute;
    display: block;
    content: '🔒';
}


.form-group .input:error {
    border-color: #9c0000;
}

.form-group .form-validation:not(.show) {
    display: none;
}

.form-group .form-validation {
    color: #9c0000;
    font-weight: 700;
    font-size: 0.85rem;
    padding-top: 3px;
}

.form-email {
    margin-bottom: 21px;
}

.form-actions {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 1.5rem;
}

.form-actions a {
    font-size: 0.75rem;
}

.form-actions button {
    padding: 0.25rem 0.75rem;
    border: none;
    border-radius: 40px;
    color: #FFFFFF;
    background-color: #1473e6;
    font-weight: 700;
    height: 2rem;
}

.form-sepparator {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-weight: 300;
    color: #4b4b4b;
    margin-bottom: 1.5rem;
}

.form-sepparator::before,
.form-sepparator::after {
    display: block;
    content: '';
    flex-grow: 1;
    height: 1px;
    background-color: #eaeaea;
}

.social-login-wrapper {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    margin-bottom: 1.5rem;
}

.social-login-wrapper .social-login {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    font-weight: 700;
    padding: 1rem;
    color: #505050;
    border: 2px solid #eaeaea;
    border-radius: 60px;
    transition: color 0.3s, border-color 0.3s, background-color 0.3s;
}

.social-login-wrapper .social-login:hover{
    cursor: pointer;
    color: #323232;
    border-color: #d3d3d3;
}

.social-login-wrapper .social-login:active{
    background-color: #f4f4f4;
}

.social-login-wrapper .social-login img {
    display: block;
    width: 1.5rem;
    height: 1.5rem;
}

.sign-in-help {
    padding: 1rem 0;
    font-size: 0.75rem;
}

@media screen and (min-width: 510px) {

    .form-wrapper {
        width: 510px;
        padding: 2.5rem 3.5rem;
    }

    .full {
        padding: 1rem 0;
        box-sizing: border-box;
    }

    .flex.full {
        justify-content: center;
    }
    
}

@media screen and (min-width: 1280px) {
    
    .content {
        justify-content: flex-start;
    }

    .logo-wrapper {
        display: flex;
        flex-grow: 1;
    }

    .form-wrapper .form-logo,
    .form-wrapper .mb-1 {
        display: none;
    }

}






index.js



const emailRegex = /^(([^<>()[\]\.,;:\s@\"]+(\.[^<>()[\]\.,;:\s@\"]+)*)|(\".+\"))@(([^<>()[\]\.,;:\s@\"]+\.)+[^<>()[\]\.,;:\s@\"]{2,})$/i;

const emailInput = document.getElementById("user-email");
const emailGroup = emailInput.closest('form-group');

const passwordInput = document.getElementById("user-password");
const passwordGroup = passwordInput.closest('.form-group');
const togglepassword = document.getElementById('toggle-password');

const nextButton = document.getElementById("form-next");
const submitButton = document.getElementById("form-submit");

emailInput.addEventListener('change', (e) => {
    const isValid = emailRegex.test(e.target.value);

    const emailValidation = emailGroup.querySelector('.form-validation');
    
    emailInput.classList.remove('error');
    emailValidation.classList.remove('show');
    emailValidation.innerHTML = '';

    if(!isValid) {
        emailInput.classList.add('error');

        emailValidation.classList.add('show');
        emailValidation.innerHTML = 'Insira um e-mail válido';
    }
});    

const loginForm = document.getElementById("login-form");

loginForm.addEventListener('submit', (e) => {
    e.preventDefault();
    
    const email = e.target.email.value;

passwordGroup.classList.remove('hidden');

    console.log(email);
});

nextButton.addEventListener('click', () => {
    passwordGroup.classList.remove('hidden');

    nextButton.classList.add('hidden');
    submitButton.classList.remove('hidden');
});

togglepassword.addEventListener ('click', () => {
    const nextType = togglepassword.classList.contains('toggle-text')
    ?
    'toggle-password' :
    'toggle-text';

    togglepassword.classList.toggle('toggle-text');
    togglepassword.classList.toggle('toggle-password');

    if (nextType == 'toggle-password') {
        passwordInput.setAttribute('type', 'password')
    }else{
        passwordInput.setAttribute('type', 'text')
    }
})
function addClass(el, addedclass) {
    const classes = (el.getAttribute('class') ?? '').split(' ');

    const classExists = classes.includes(addedclass);

    if(classExists) {
        return;
    }

    classes.push(addedclass);

    classes = classes.join(' ');

    el.setAtribute('class', classes);

}






index.HTML





<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login - Adobe</title>
    <!-- Arquivo de reset, limpa as estilizações do navegador -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link
        href="https://fonts.googleapis.com/css2?family=Source+Sans+3:ital,wght@0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap"
        rel="stylesheet">
    <link rel="stylesheet" href="css/reset.css">
    <!-- Arquivo contendo as nossas estilizações -->
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <!-- Conteúdo Geral da Página -->
    <!-- Display Flex para que os conteúdos fiquem distribuídos de forma fluida -->
    <div class="flex center full bg-img">
        <div class="flex content">
            <!-- Elemento responsável por "conter" o logo -->
            <div class="logo-wrapper">
                <img src="./images/adobe_logo.svg" alt="Logo Adobe">
                Faça logon ou crie uma conta
            </div>
            <!-- Element responsável por "conter" o formulário -->
            <div class="form-wrapper">
                <!-- Display flex, para que o elemento ocupe o espaço disponível -->
                <div class="flex">
                    <!-- MB = Margin Bottom (ou margem inferior) -->
                    <div class="mb-1">
                        <!-- .form-logo será usada para alterar a cor do SVG -->
                        <img src="images/adobe_logo.svg" class="form-logo" alt="Logo Adobe">
                    </div>
                </div>
                <h1 class="form-title">Fazer logon</h1>
                <form id="login-form">
                    <div class="form-email">
                        <p class="form-new-user">
                            Novo usuário?
                            <a href="#">
                                Crie uma conta
                            </a>
                        </p>
                        <div class="form-group">
                            <label for="user-email">Endereço de email</label>
                            <input id="user-email" type="text" name="email">
                            <span class="form-validation"></span>
                        </div>
                        <div class="form-group hidden">
                            <label for="user-password">Senha</label>
                            <div class="relative">
                                <input id="user-password" type="password" name="password">
                                <button id="toggle-password" class="toggle-text" type="button">
                                    👁
                                </button>
                            </div>
                            <span class="form-validation"></span>
                        </div>
                    </div>
                    <div class="form-actions">
                        <a href="#">Fazer logon com chave de acesso</a>
                        <button id="form-next" class="btn btn-primary" type="button">Continuar</button>
                        <button id="form-submit" class="btn btn-primary hidden" type="submit">Enviar</button>
                    </div>
                    <div class="form-sepparator">
                        Ou
                    </div>
                    <div class="social-login-wrapper">
                        <div class="social-login">
                            <img src="./images/Google__G__Logo.svg.webp" alt="Logo Google">
                            Continuar com o Google
                        </div>
                        <div class="social-login">
                            <img src="./images/f_logo_RGB-Blue_58.png" alt="Logo Facebook">
                            Continuar com o Facebook
                        </div>
                        <div class="social-login">
                            <img src="./images/apple.svg" alt="Logo Apple">
                            Continuar com a Apple
                        </div>
                        <div class="sign-in-help">
                            <a href="#">
                                Obtenha ajuda para fazer logon
                            </a>
                        </div>
                    </div>
                </form>
            </div>
        </div>
    </div>
    <script src="./scripts/index.js"></script>
</body>
</html>
