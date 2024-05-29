# **Criando uma Aplicação de Cadastro de Alunos com Stimulus e REST API em Ruby on Rails**

## **Introdução**
Este artigo é um guia passo a passo para construir uma aplicação de cadastro de alunos utilizando Ruby on Rails, integrando uma REST API para operações CRUD e StimulusJS para enriquecer a interatividade do usuário. Ao final deste projeto, você terá uma aplicação completa e estará pronto para aplicar seus conhecimentos em projetos reais.

## **1. Configuração do Projeto**

### **1.1. Instalação do Ruby on Rails**
Certifique-se de ter o Ruby on Rails instalado em seu ambiente de desenvolvimento. Se necessário, instale-o seguindo as instruções oficiais.

### **1.2. Criação do Projeto Rails**
Crie um novo projeto Rails com o comando:
```bash
rails new CadastroAlunos
```

### **1.3. Configuração do Banco de Dados**
Configure o banco de dados MySQL ou PostgreSQL no arquivo `config/database.yml`.

## **2. Construção da REST API**

### **2.1. Modelo Aluno**
Crie um modelo `Aluno` com os atributos necessários:
```bash
rails generate model Aluno nome:string registro_academico:string email:string
```

### **2.2. Controlador Alunos**
Gere um controlador com ações CRUD para o modelo `Aluno`:
```bash
rails generate controller Alunos
```

### **2.3. Rotas REST**
Defina as rotas REST no arquivo `config/routes.rb`:
```ruby
resources :alunos
```

## **3. Implementação do StimulusJS**

### **3.1. Adicionando StimulusJS**
Adicione o StimulusJS ao seu projeto Rails¹². Você pode fazer isso adicionando a gem `stimulus-rails` ao seu `Gemfile` e executando o bundle install.

### **3.2. Controladores Stimulus**
Crie controladores Stimulus para adicionar interatividade às suas páginas. Por exemplo, para um controle de formulário de aluno:
```javascript
// app/javascript/controllers/aluno_form_controller.js
import { Controller } from "stimulus"

export default class extends Controller {
  connect() {
    console.log("Formulário de aluno conectado com Stimulus!")
  }
}
```

### **3.3. Uso do Stimulus na View**
Utilize os controladores Stimulus nas suas views para melhorar a experiência do usuário. Por exemplo:
```erb
<!-- app/views/alunos/_form.html.erb -->
<div data-controller="aluno-form">
  <%= form_with(model: aluno, local: true) do |form| %>
    <!-- Campos do formulário -->
  <% end %>
</div>
```

## **4. Consumindo a REST API**

### **4.1. Fetch API no Front-end**
Utilize a Fetch API para consumir sua REST API no front-end. Por exemplo, para buscar alunos:
```javascript
fetch('/alunos')
  .then(response => response.json())
  .then(data => console.log(data))
```

### **4.2. Integração com Stimulus**
Integre as chamadas da API com os controladores Stimulus para criar uma experiência de usuário dinâmica e responsiva.

## **5. Conclusão**

Com a integração da REST API e do StimulusJS, você criou uma aplicação de cadastro de alunos dinâmica e interativa em Ruby on Rails. Este projeto não só serve como uma excelente prática de desenvolvimento web, mas também como uma base sólida para futuras expansões e funcionalidades.

Espero que este guia tenha sido útil e que qualquer um, se sinta confiante para criar sua própria aplicação com Ruby on Rails, Stimulus e REST API.
