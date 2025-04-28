# Minicurso Hugo

Criando um blog com Hugo

---

Minicurso ministrado por mim no FLISoL 2025 - Natal/RN.

- Tema usado: [LoveIt](https://hugoloveit.com/theme-documentation-basics/)

- Material do minicurso: [Como criar seu blog com Hugo](https://carolinasoares.dev/tutorials/criando-blog-com-hugo/)

Obs.: criei uma conta externa no GitHub para exemplificar como subir o projeto com o GitHub Pages.

## Erro na versão do Hugo

O tema LoveIt suporta o Hugo na versão ≥ 0.128.0, outros temas também precisam de uma versão mais atual ou antiga para funcionar. Confira sempre a documentação dos temas escolhidos.

Verificar qual versão do Hugo está instalada:

    $ hugo version

### Atualizar versão do Hugo

Desintale o Hugo para instalar novamento depois:

    $ sudo apt remove hugo
    
Procure uma versão do Hugo para instalar no [GitHub](https://github.com/gohugoio/hugo/tags). 

Baixe o arquivo de instalação com (substitua o link pela versão escolhida):

    $ wget https://github.com/gohugoio/hugo/releases/download/v0.128.1/hugo_extended_0.128.1_Linux-64bit.tar.gz

Descompacte:

    $ tar -xvzf hugo_extended_0.125.7_Linux-64bit.tar.gz

Mova o executável para o diretório de binário

    $ sudo mv hugo /usr/local/bin/

Verifique a instalação:

    $ hugo version

Caso o arquivo de instalação seja .deb, após baixar o arquivo, instale com:

    $ sudo dpkg -i hugo_extended_0.128.1_Linux-64bit.deb

## Conflito de versão entre config.toml e hugo.toml no Hugo

Versões mais recentes do Hugo (v0.110.0+) passaram a usar hugo.toml como nome padrão do arquivo de configuração.

Para versões mais modernas do Hugo, alterar config.toml para hugo.toml:

    $ mv config.toml hugo.toml

Para versões mais antigas, alterar hugo.toml para config.toml:

    $ mv hugo.toml config.toml

Definir arquivo de configuração que será usado:

    hugo --config hugo.toml
    # ou
    hugo --config config.toml

Se ambos arquivos existirem, o Hugo usa essa ordem de prioridade:

    hugo.toml

    hugo.yaml

    hugo.json

    config.toml

    config.yaml

    config.json
