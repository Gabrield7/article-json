<a href=""><img src="./Como Utilizar JSON para Troca de Dados entre Aplicações.png" alt="DIO - course"></a>

## O Que é JSON?
JSON (JavaScript Object Notation) é uma forma simples e organizada de guardar e trocar informações entre computadores e programas. Pense no JSON como uma lista de compras que é fácil de ler e entender. Ele é usado para enviar dados de um lugar para outro na internet, como entre seu computador e um site.

## Estrutura do JSON
JSON usa chaves e valores para guardar informações. As chaves são como etiquetas que dizem o que é a informação, e os valores são as próprias informações. Aqui está um exemplo de um objeto JSON que guarda informações sobre uma pessoa:

```
{
  "nome": "João",
  "idade": 10,
  "brinquedos": ["bola", "lego"]
}
```

Neste exemplo:

- "nome" é uma chave, e "João" é o valor.
- "idade" é uma chave, e 10 é o valor.
- "brinquedos" é uma chave, e ["bola", "lego"] é um array (lista) de valores.

## Enviando Dados JSON com JavaScript
Para mandar dados usando JSON, usamos uma função chamada fetch(). É como mandar uma carta com as informações que queremos enviar. Vamos ver como isso funciona:

```
fetch('https://api.exemplo.com/dados', {
  method: 'POST',  // Diz que estamos enviando dados
  headers: {
    'Content-Type': 'application/json'  // Diz que estamos enviando dados no formato JSON
  },
  body: JSON.stringify({ nome: "Maria", idade: 12 })  // Os dados que estamos enviando, convertidos para JSON
})
.then(response => response.json())  // Quando recebemos a resposta, convertemos para um objeto
.then(data => console.log(data));  // Mostramos os dados recebidos no console
```

Neste exemplo:

- Usamos fetch() para enviar dados para 'https://api.exemplo.com/dados'.
- Dizemos que estamos enviando dados com method: 'POST'.
Especificamos que os dados estão no formato JSON com Content-Type: 'application/json'.
- Usamos ```JSON.stringify()``` para converter o objeto ```{ nome: "Maria", idade: 12 }``` em uma string JSON.
- Quando recebemos a resposta, convertemos de volta para um objeto JavaScript com ```response.json()```.
- Finalmente, mostramos os dados recebidos no console.

## Recebendo Dados JSON com JavaScript
Para receber dados JSON, também usamos a função fetch(). É como receber uma carta de volta com as informações. Veja como isso funciona:
```
fetch('https://api.exemplo.com/dados')  // Faz uma requisição para o endereço
  .then(response => response.json())  // Quando recebemos a resposta, convertemos para um objeto
  .then(data => console.log(data));  // Mostramos os dados recebidos no console`
```
Neste exemplo:

- Fazemos uma requisição GET para 'https://api.exemplo.com/dados'.
- Quando recebemos a resposta, usamos response.json() para convertê-la de uma string JSON para um objeto JavaScript.
- Mostramos os dados recebidos no console.

## Convertendo entre JSON e Objetos JavaScript
Para converter um objeto JavaScript para JSON, usamos JSON.stringify(). Para converter JSON de volta para um objeto JavaScript, usamos JSON.parse(). Aqui está um exemplo:
```
const objeto = { nome: "Ana", idade: 10 };  // Um objeto JavaScript
const jsonString = JSON.stringify(objeto);  // Converte o objeto em uma string JSON
console.log(jsonString);  // Mostra a string JSON: '{"nome":"Ana","idade":10}'

const novoObjeto = JSON.parse(jsonString);  // Converte a string JSON de volta para um objeto
console.log(novoObjeto.nome);  // Mostra "Ana", que é o valor da chave "nome"
```
Neste exemplo:

- JSON.stringify(objeto) converte o objeto ```{ nome: "Ana", idade: 10 }``` em uma string JSON ```{"nome":"Ana","idade":10}```.
- ```JSON.parse(jsonString)``` converte a string JSON de volta para um objeto.
- Mostramos o valor da chave "nome" do novo objeto, que é "Ana".

## Segurança e Validação dos Dados JSON
É importante garantir que os dados JSON estejam corretos e seguros. Usar algo chamado JSON Schema ajuda a verificar se os dados estão no formato certo. Além disso, devemos proteger nossas informações quando enviamos e recebemos dados na internet.
```
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "type": "object",
  "properties": {
    "nome": { "type": "string" },  // A chave "nome" deve ser uma string
    "idade": { "type": "integer", "minimum": 0 }  // A chave "idade" deve ser um número inteiro não negativo
  },
  "required": ["nome", "idade"]  // "nome" e "idade" são obrigatórios
}
```
Neste exemplo de JSON Schema:

- Garantimos que o objeto tenha as propriedades "nome" e "idade".
- Verificamos que "nome" é uma string e "idade" é um número inteiro não negativo

## Conclusão

Em síntese, o JSON (JavaScript Object Notation) se destaca como uma ferramenta essencial para trocar dados de maneira estruturada e eficiente entre diferentes aplicações web. Com sua sintaxe simples de chaves e valores, o JSON permite representar informações complexas de forma compreensível tanto para humanos quanto para computadores.

Dominar o uso de JSON em JavaScript não só facilita o envio de dados entre servidores e clientes, mas também abre caminho para criar aplicações mais dinâmicas e conectadas. Essa habilidade não apenas melhora a eficiência do desenvolvimento, mas também é fundamental para explorar todo o potencial da programação web moderna.

Assim, aprender e dominar JSON é não apenas uma necessidade técnica, mas uma habilidade transformadora para qualquer desenvolvedor web.


#JSON #JavaScript #DataExchange
