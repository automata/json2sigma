# GML2JS

Baseado no trabalho original de <a href="https://github.com/coyotebush/github-network-analysis">@coyotebush</a> para visualização de repositórios de código do Github.

# Usando

Primeiramente é necessário este repositório:

    git clone https://github.com/automata/json2sigma.git

Em seguida, precisamos usar o Gephi para exportar um arquivo GML qualquer para JSON:

1. Baixe e instale o Gephi
2. Instale o plugin JSONExporter: Ferramentas > Plugins > Procure e instale
3. Abra um arquivo GML qualquer no Gephi
4. Exporte a rede como JSON: Arquivo > Exportar > Arquivo de grafo > foo.json

Edite o arquivo json2sigma/code.js, nas últimas linhas, para referenciar seu arquivofoo.json exportado:

    graph.parseJson('foo.json', function() {
      graph.iterEdges(function(e){
        e.size=Math.sqrt(e.weight);
      });
      graph.draw();
    });

Salve o arquivo e abra o index.html em seu navegador Web.
