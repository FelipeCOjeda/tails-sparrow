# Tails com Sparrow

Projeto independente de uma imagem USB baseada no Tails com armazenamento persistente pré-configurado, sem afiliação com o Tails, a Sparrow Wallet ou a Mozilla. A imagem está em preparação. [Página do projeto](https://felipecojeda.github.io/tails-sparrow/).

## Download

Ainda não há uma imagem pública. A cópia de trabalho foi clonada com armazenamento persistente e uma senha conhecida. Quem tiver a cópia e a senha pode acessar os dados nela. Trocar a senha no próprio pendrive não protege cópias anteriores.

A versão pública inclui armazenamento persistente pré-configurado. Prepare essa partição em um ambiente dedicado à distribuição, com apenas os arquivos e ajustes necessários ao produto. Exclua dados pessoais, carteiras, seeds, chaves privadas e credenciais da preparação da imagem.

## Altere a senha do persistente no primeiro acesso

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

1. **Baixe.** Quando a versão pública estiver disponível, baixe o arquivo `tails-sparrow.img` e sua assinatura `tails-sparrow.img.asc`.
2. **Verifique com GPG.** Confira a impressão digital da chave pública do projeto por um canal confiável, importe essa chave e rode `gpg --verify tails-sparrow.img.asc tails-sparrow.img`. Prossiga somente se a assinatura for válida e pertencer à chave esperada. O arquivo SHA256SUMS da versão também permitirá conferir o hash com `Get-FileHash -Algorithm SHA256 -LiteralPath .\tails-sparrow.img`. [Manual do GnuPG](https://gnupg.org/gph/en/manual.html).
3. **Grave e inicie.** No Rufus, selecione o pendrive, escolha o arquivo .img e clique em **Iniciar**. Se aparecer a opção, escolha **modo DD**. No balenaEtcher, escolha **Flash from file**, selecione o .img e o pendrive e clique em **Flash!**. O pendrive precisa comportar a imagem inteira. Faça backup, pois a gravação apaga o conteúdo do dispositivo selecionado. Reinicie e escolha o pendrive no menu de boot.

O Tails recomenda o Rufus no Windows e deixou de recomendar o balenaEtcher por motivos de privacidade. [Guia do Tails para Windows](https://tails.net/install/windows/).

O SHA256SUMS da versão pública será gerado a partir da imagem final. O GitHub Releases aceita arquivos individuais menores que 2 GiB. Se o arquivo compactado ultrapassar o limite, o botão de download direto precisará apontar para um armazenamento de objetos com capacidade para o arquivo inteiro. [Limites do GitHub Releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases).
