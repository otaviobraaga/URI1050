# URI1050
URI 1050 Resolução em JavaScript


var modo_uri = false;

    try {
        document.URL;
    } catch (error) {
        modo_uri = true;
    }

    if (modo_uri) {
        var input = require('fs').readFileSync('/dev/stdin', 'utf8'); //string input do uri
        var valores = input.split('\n'); //quebra o input em um array de strings, onde cada string é um valor do teste atual do uri
    }

    function pularLinha() {
        if (!modo_uri)
            document.write("<br><br>");
    }

    function mostra(frase) {
        if (modo_uri)
            console.log(frase);
        else
            document.write(frase);

        pularLinha();
    }

    function entrada(mensagem = "", parse = null) {
        var valor = "";

        if (modo_uri)
            valor = valores.shift();
        else
            valor = prompt(mensagem);

        if (parse)
            valor = parse(valor);

        return valor;
    }

    var tabela_ddd = {
        61: "Brasilia",  //Um ojbeto armazena pares de chaves e valores.
        71: "Salvador",
        11: "Sao Paulo",
        21: "Rio de Janeiro",
        32: "Juiz de Fora",
        19: "Campinas",
        27: "Vitoria",
        31: "Belo Horizonte"
    };

    var ddd = entrada('Digite o DDD');
    var cidade = tabela_ddd[ddd];
    
    if (!cidade)
        cidade = "DDD nao cadastrado";

    mostra(cidade);
