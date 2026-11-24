# Tails com Sparrow

Projeto independente de uma imagem USB baseada no Tails com armazenamento persistente pré-configurado, sem afiliação com o Tails, a Sparrow Wallet ou a Mozilla. A imagem está em preparação. [Página do projeto](https://felipecojeda.github.io/tails-sparrow/).

## Download

[Baixar os três volumes no GitHub Releases](https://github.com/FelipeCOjeda/tails-sparrow/releases/tag/v0.1.0). O pacote completo ocupa 5,74 GiB e a imagem extraída ocupa 14,46 GiB.

A imagem inclui armazenamento persistente pré-configurado com uma senha inicial pública. Troque a senha no primeiro acesso, antes de guardar dados.

## Altere a senha do persistente no primeiro acesso

**Senha inicial do armazenamento persistente** `SatoshiNakamoto21`

Se o seu pendrive já vem com armazenamento persistente configurado, troque a senha logo no primeiro acesso, antes de salvar dados.

1. Na tela de boas-vindas, desbloqueie o armazenamento persistente com a senha atual e inicie o Tails.
2. Abra **Aplicativos → Tails → Armazenamento persistente**.
3. Clique em **Alterar frase secreta** (Change Passphrase), na barra de título.
4. Digite a senha atual, informe uma nova frase secreta exclusiva e repita a nova senha no campo de confirmação. Clique em **Alterar**.
5. Reinicie o Tails e confirme que a nova senha desbloqueia o armazenamento persistente.

A troca altera a frase secreta exigida pelo pendrive. Cópias da imagem continuam acessíveis com a senha inicial. Uma partição LUKS clonada também compartilha a chave de criptografia do volume com as outras cópias. A troca da frase secreta mantém essa chave. [Documentação do Tails](https://translate.tails.net/projects/tails/wikisrcdocpersistent_storagepassphrase-po/en/).

## Versões e compatibilidade

- [Sparrow Wallet 2.5.6](https://sparrowwallet.com/download/) tem distribuição oficial para Linux. Verifique a assinatura do manifesto antes de incorporar o pacote.
- [Firefox 160](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/160) existe para Linux e recebeu correções no [Firefox 160.0.1](https://www.mozilla.org/en-US/security/advisories/mfsa2026-130/). A versão instalada, a execução e o comportamento de rede dessa imagem ainda precisam ser verificados. Use o [Tor Browser](https://tails.net/doc/anonymous_internet/Tor_Browser/) para navegação via Tor no Tails.
- Para instalar pacotes manualmente, abra **Configurações adicionais → Senha de administração** na tela de boas-vindas antes de iniciar o Tails. A senha vale para a sessão e é usada quando uma tarefa pede privilégios. Para atualizar o próprio Tails, siga o fluxo de atualização do sistema. Valide se os aplicativos personalizados sobrevivem ao upgrade. [Senha de administração](https://tails.net/doc/first_steps/welcome_screen/administration_password/) · [Software adicional](https://tails.net/doc/persistent_storage/additional_software/) · [Atualizações do Tails](https://tails.net/doc/upgrade/).

## Verificar, gravar e iniciar

1. **Baixe e extraia.** Salve os volumes .7z.001, .7z.002 e .7z.003 na mesma pasta. Abra apenas o .001 no 7-Zip e extraia o arquivo **tails sparrow.img**.
2. **Verifique o SHA-256.** Baixe o SHA256SUMS do mesmo Release, rode `Get-FileHash -Algorithm SHA256 -LiteralPath '.\tails sparrow.img'` no PowerShell e compare o resultado com a linha do .img. Esta versão ainda não tem assinatura GPG.
3. **Grave e inicie.** No Rufus, selecione o pendrive, escolha o arquivo .img e clique em **Iniciar**. Se aparecer a opção, escolha **modo DD**. No balenaEtcher, escolha **Flash from file**, selecione o .img e o pendrive e clique em **Flash!**. O pendrive precisa comportar a imagem inteira. Faça backup, pois a gravação apaga o conteúdo do dispositivo selecionado. Reinicie e escolha o pendrive no menu de boot.

O Tails recomenda o Rufus no Windows e deixou de recomendar o balenaEtcher por motivos de privacidade. [Guia do Tails para Windows](https://tails.net/install/windows/).
