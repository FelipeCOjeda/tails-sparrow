# Tails com Sparrow

Projeto independente de uma imagem USB baseada no Tails, sem afiliação com o Tails, a Sparrow Wallet ou a Mozilla. A imagem está em preparação. [Página do projeto](https://felipecojeda.github.io/tails-sparrow/).

## Download

Ainda não há uma imagem pública. A cópia de trabalho foi clonada com armazenamento persistente e uma senha conhecida. Quem tiver a cópia e a senha pode acessar os dados nela. Trocar a senha no próprio pendrive não protege cópias anteriores.

A versão pública deve ser reconstruída a partir de uma imagem oficial verificada, sem partição persistente clonada, dados pessoais, carteiras, seeds, chaves, perfis ou credenciais. Crie o armazenamento persistente no primeiro uso e defina uma frase secreta exclusiva antes de salvar dados. Se você usa a senha da cópia em outro lugar, substitua-a antes de voltar a usar o armazenamento.

## Versões e compatibilidade

- [Sparrow Wallet 2.5.6](https://sparrowwallet.com/download/) tem distribuição oficial para Linux. Verifique a assinatura do manifesto antes de incorporar o pacote.
- [Firefox 160](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/160) existe para Linux e recebeu correções no [Firefox 160.0.1](https://www.mozilla.org/en-US/security/advisories/mfsa2026-130/). A versão instalada, a execução e o comportamento de rede dessa imagem ainda precisam ser verificados. Use o [Tor Browser](https://tails.net/doc/anonymous_internet/Tor_Browser/) para navegação via Tor no Tails.
- Para instalar pacotes manualmente, abra **Configurações adicionais → Senha de administração** na tela de boas-vindas antes de iniciar o Tails. A senha vale para a sessão e é usada quando uma tarefa pede privilégios. Para atualizar o próprio Tails, siga o fluxo de atualização do sistema. Valide se os aplicativos personalizados sobrevivem ao upgrade. [Senha de administração](https://tails.net/doc/first_steps/welcome_screen/administration_password/) · [Software adicional](https://tails.net/doc/persistent_storage/additional_software/) · [Atualizações do Tails](https://tails.net/doc/upgrade/).

## Verificar, gravar e iniciar

1. Baixe a futura imagem e o arquivo SHA256SUMS da mesma versão. Se o download estiver em um arquivo compactado, extraia o arquivo .img.
2. No PowerShell, rode **Get-FileHash -Algorithm SHA256 -LiteralPath .\tails-sparrow.img** e compare todos os 64 caracteres com o hash do .img em SHA256SUMS. O hash verifica integridade e uma assinatura verificável ajuda a confirmar procedência.
3. Use um pendrive com capacidade real igual ou maior que o tamanho da imagem descompactada. Faça backup, selecione o .img no gravador e confirme o dispositivo de destino. A gravação apaga os dados do pendrive. [Guia do Tails para Windows](https://tails.net/install/windows/).
4. Reinicie o computador, selecione o pendrive no menu de inicialização e aguarde a tela de boas-vindas. Crie sua própria persistência se precisar guardar dados. [Configuração da persistência](https://tails.net/doc/persistent_storage/configure/).

O SHA256SUMS da versão pública será gerado a partir da imagem final. O GitHub Releases aceita arquivos individuais menores que 2 GiB. Se o arquivo compactado ultrapassar o limite, o botão de download direto precisará apontar para um armazenamento de objetos com capacidade para o arquivo inteiro. [Limites do GitHub Releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases).
