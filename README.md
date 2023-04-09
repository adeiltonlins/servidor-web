# servidor-web
/* carregando o modulo http padrão para todas as instalações node.
É aqui que vamos utilizar uma função para criar o servidor posteriormente*/
const http = require("http");

/*
Definindos duas constantes para possibilitar o acesso da página através do navegador web*/
const host = 'localhost';
const port = 8000;

/*
Adicionando uma função que irá receber uma solicitação HTTP e retornar uma resposta também em HTTP.
Essa função recebe dois argumentos (req e res), o primeiro reune todos os dados da solicitação e o 
segundo é usado para devolver. O servidor irá retornar a mensagem: Parabens, conexão realizada!
*/
const requestListener = function (req, res) {//o nome da constante deve corresponder a ação executada
    res.writeHead(200); //o código 200 define o status ok via http
    res.end("Parabens, conexão realizada!");
};

const server = http.createServer(requestListener); /* criando o servidor server que recebe como parametro
o objeto requestLisitener
 */
server.listen(port, host, () => {//associando o servidor a um endereço e porta
    console.log(`O servidor está rodando em http://${host}:${port}`); //saída para o console
