# DPage Releases

Repositório público oficial de distribuição do **DPage by DTools**.

Este repositório contém somente instaladores e arquivos públicos de verificação de versão. O código-fonte do aplicativo, backend, credenciais e demais componentes internos permanecem em repositórios privados.

## Download

O instalador oficial mais recente é publicado em **GitHub Releases** com o nome estável:

`DPage-Setup.exe`

O portal DPage aponta para a release mais recente, sem expor o código-fonte privado.

## Publicação segura

A publicação do instalador é manual e deliberada. O workflow **Publish DPage Installer** recebe o ID de um build aprovado do repositório privado PLOTAPP e publica somente o artifact já testado. URLs temporárias de artifact não ficam armazenadas neste repositório.

O caminho preferencial usa um secret de leitura `PLOTAPP_READ_TOKEN` no GitHub Actions. Enquanto esse secret não estiver configurado, o workflow aceita uma URL temporária apenas como entrada da execução, sem gravá-la no código.

## Verificação

Cada release inclui `DPage-Setup.exe.sha256.txt`. O workflow valida o SHA-256 antes de publicar.

## Regra de pré-lançamento

Não publicar um novo instalador apenas porque compilou. Antes da release pública:

1. o build Windows precisa terminar verde;
2. todos os testes automatizados precisam passar;
3. o smoke test do executável empacotado precisa passar;
4. o backend correspondente precisa estar com o quality gate verde;
5. o teste manual do DPage deve ser concluído.

© DTools
