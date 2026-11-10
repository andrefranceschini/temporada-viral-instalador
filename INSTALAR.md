# Instalar a Temporada Viral numa sessão do Claude Code na nuvem

Instruções para a IA. Quem comprou só precisa mandar, numa sessão do Claude Code na nuvem aberta no próprio
repositório:

> Instale a Temporada Viral seguindo https://raw.githubusercontent.com/andrefranceschini/temporada-viral-instalador/main/INSTALAR.md
> A senha é: (a senha da área de membros)

Versão do arquivo protegido: v2.3 (10/11/2026).

## Passos

1. Se a pessoa não mandou a senha, peça a senha da área de membros e espere. Não tente adivinhar.
2. Baixe e abra o arquivo protegido, fora do repositório:

   ```bash
   curl -fsSL -o /tmp/tv.enc https://raw.githubusercontent.com/andrefranceschini/temporada-viral-instalador/main/temporada-viral.zip.enc
   openssl enc -d -aes-256-cbc -pbkdf2 -iter 200000 -in /tmp/tv.enc -out /tmp/tv.zip -pass pass:"SENHA_QUE_A_PESSOA_MANDOU"
   ```

   Se o `openssl` falhar com "bad decrypt", a senha está errada. Avise e peça de novo.
3. Copie a pasta para a raiz do repositório:

   ```bash
   rm -rf /tmp/tv && mkdir -p /tmp/tv && unzip -q /tmp/tv.zip -d /tmp/tv
   cp -r /tmp/tv/temporada-viral/. ./
   rm -f /tmp/tv.enc /tmp/tv.zip
   ```

4. Nunca grave a senha em arquivo, commit, mensagem de commit ou variável de ambiente persistente.
5. Faça o commit e envie (`git add -A`, commit "instala a Temporada Viral", push). Se puder, envie direto para o
   branch principal (`git push origin HEAD:main`), para as próximas sessões já começarem com a ferramenta. Se o push
   no principal for recusado, envie o branch da sessão e explique à pessoa, em uma frase, como juntar pelo celular
   (abrir o pull request no GitHub e tocar em "Merge").
6. Leia o `CLAUDE.md` que acabou de chegar e siga o modo nuvem: a máquina não tem placa de vídeo e o render roda
   na CPU (`kit/INSTALAR.md`, seção 4). Ative a licença com o e-mail da compra (seção "Licença" do `CLAUDE.md`) e
   faça commit do `.licenca.json`, para as próximas sessões não pedirem de novo. Depois comece a entrevista do
   canal, como manda o `CLAUDE.md`. Na pergunta dos dois caminhos, a nuvem já é o caminho recomendado (Claude
   Code): siga por ele sem perguntar.
7. Os vídeos prontos vão para o repositório. Diga à pessoa onde baixar cada um pelo celular.
