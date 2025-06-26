<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contato</title>      
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.6/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.6/dist/js/bootstrap.bundle.min.js"></script>

    <style>
        body {
            background: linear-gradient(120deg, #3a7bd5 0%, #00d2ff 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }
       .contact-container {
  background: #ffffff;
  max-width: 100vw;
  width: 100%;
  border-radius: 0;
  box-shadow: none;
  padding: 2rem;
  min-height: 100vh; 
  box-sizing: border-box; 
}
        .contact-title {
            font-weight: 700;
            color: #3a7bd5;
            margin-bottom: 1.5rem;
            text-align: center;
        }
        .btn-primary {
            background: #3a7bd5;
            border: none;
        }
        .btn-primary:hover {
            background: #00d2ff;
        }
        label {
            color: #3a7bd5;
        }
    </style>
</head>



<body>

 <div class="contact-container">

    <nav aria-label="breadcrumb" class="mb-4">
      <ol class="breadcrumb">
        <li class="breadcrumb-item"><a href="#" class="text-primary text-decoration-none"></a></li>
        <li class="breadcrumb-item active" aria-current="page">Contato</li>
      </ol>
    </nav>

    <h2 class="contact-title"><i class="fa-solid fa-envelope"></i> Fale Conosco</h2>

   
    <button type="button" class="btn btn-secondary w-100 mb-3" data-bs-toggle="modal" data-bs-target="#infoModal">
      <i class="fa-solid fa-circle-info"></i> Ajuda Rápida
    </button>

    
    <button type="button" class="btn btn-warning w-100 mb-3" data-bs-toggle="popover" title="Dica!" data-bs-content="Preencha todos os campos obrigatórios corretamente.">
      <i class="fa-solid fa-lightbulb"></i> Mostrar Dica
    </button>


    <div class="contact-container">
       
        <form id="form-contato" aria-label="Formulário">
            <div class="mb-3">
                <label for="nome" class="form-label">Nome Completo</label>
                <input type="text" class="form-control" id="nome" name="nome" required>
            </div>
            <div class="mb-3">
                <label for="email" class="form-label">E-mail</label>
                <input type="email" class="form-control" id="email" name="email" required>
            </div>
            <div class="mb-3">
                <label for="cep" class="form-label">Cep</label>
                <input type="text" placeholder="12345-678" class="form-control" id="cep" name="cep" required>
            </div>
            <div class="mb-3">
                <label for="rua" class="form-label">Rua</label>
                <input type="text" class="form-control" id="rua" name="rua" required>
            </div>
            <div class="mb-3">
                <label for="bairro" class="form-label">Bairro</label>
                <input type="text" class="form-control" id="bairro" name="bairro" required>
            </div>
            <div class="mb-3">
                <label for="cidade" class="form-label">Cidade</label>
                <input type="text" class="form-control" id="cidade" name="cidade" required>
            </div>
            <div class="mb-3">
                <label for="estado" class="form-label">Estado</label>
                <input type="text" class="form-control" id="estado" name="estado" required>
            </div>
            <div class="mb-3">
                <label for="numero" class="form-label">Número</label>
                <input type="text" placeholder="Número" class="form-control" id="numero" name="numero" required>
            </div>
            <button type="submit" class="btn btn-primary w-100"><i class="fa-solid fa-paper-plane"></i> Enviar Formulário</button>
        </form>
    </div>

    
    <div class="accordion mt-5" id="faqAccordion">
      <div class="accordion-item">
        <h2 class="accordion-header" id="headingOne">
          <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
            O que acontece após o envio?
          </button>
        </h2>
        <div id="collapseOne" class="accordion-collapse collapse show" aria-labelledby="headingOne" data-bs-parent="#faqAccordion">
          <div class="accordion-body">
            Seus dados serão analisados e entraremos em contato por e-mail.
          </div>
        </div>
      </div>
    </div>

    <p class="mt-4">
      <a class="btn btn-info" data-bs-toggle="collapse" href="#textCollapse" role="button" aria-expanded="false" aria-controls="textCollapse">
        Mostrar Informações
      </a>
    </p>
    <div class="collapse" id="textCollapse">
      <div class="card card-body">
        Aguarde nosso contato. 
      </div>
    </div>

  </div>

  
  <div class="modal fade" id="infoModal" tabindex="-1" aria-labelledby="infoModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="infoModalLabel">Ajuda</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Fechar"></button>
        </div>
        <div class="modal-body">
          Preencha o formulário com seus dados reais. O CEP é usado para autocompletar o endereço.
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Fechar</button>
        </div>
      </div>
    </div>
  </div>

<script>
$(document).ready(function() {
    $('#cep').on('blur', function() {
        const cep = $(this).val().replace(/\D/g, '');
        if (cep.length === 8) {
            $.getJSON(`https://viacep.com.br/ws/${cep}/json/`, function(data) {
                if (!('erro' in data)) {
                    $('#rua').val(data.logradouro);
                    $('#bairro').val(data.bairro);
                    $('#cidade').val(data.localidade);
                    $('#estado').val(data.uf);
                } else {
                    alert('CEP não encontrado.');
                }
            });
        }
    });
});

function submitform(){


    const nome = $('#nome').val();
    const email = $('#email').val();
    const cep = $('#cep').val();
    const rua = $('#rua').val();
    const bairro = $('#bairro').val();
    const cidade = $('#BRENNcidade').val();
    const estado = $('#estado').val();
    const numero = $('#numero').val();


    const formData = {
        "nome": nome,
        "email": email,
        "cep": cep,
        "rua": rua,
        "bairro": bairro,
        "cidade": cidade,
        "estado": estado,
        "numero": numero
    };

    console.log (formData);
}



</script>


    
</body>
</html>

