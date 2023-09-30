---
title: "Forma de otimizar a criação de ATAs de reunião"
date: 2022-12-30T22:21:09+01:00
draft: false
categories: [project]
tags: [tools,learning]
---

# **Elaboração de ATA de Reunião**

Uma das formas de formalizar os assuntos tratados de uma reunião de projeto é a elaboração de uma ATA de reunião.

Há diversas formas de confeccionar uma **Ata** de reunião, uma das formas mais utilizadas é a elaboração de um documento `.docx` básico, com as anotações de algum participante da reunião (normalmente o gerente do projeto, ou o responsável pelo projeto), que será posteriormente encaminhado via e-mail para todos os participantes.

> Mas como fica a organização destas **Atas**? Serão salvas em uma pasta no computador?

Uma forma que encontrei foi a utilização de uma solução híbrida. 

1. Salvar a **ATA** em uma pasta no [Microsoft OneDrive](https://www.microsoft.com/pt-br/microsoft-365/onedrive/online-cloud-storage) da equipe do projeto, criada no [Microsoft Teams](https://www.microsoft.com/pt-br/microsoft-teams/group-chat-software);
2. Utilizar o *software* [Obisidan](https://obsidian.md/), para a criação das **ATAs** em `markdown`, colocando a pasta do `Vault` no [Microsoft OneDrive](https://www.microsoft.com/pt-br/microsoft-365/onedrive/online-cloud-storage).

---

## **Informações básicas do projeto**
Primeiro o cabeçalho com as informações básicas do projeto. 

```md
---
**PROJETO:** Nome do Projeto

**TIPO DE DOCUMENTO:** (ATA ou ERRATA)

**OBJETIVO:** Objetivo da Reunião

**LOCAL:** Reunião Presencial ou Reunião Online

**HORÁRIO:** ***DEFINIR*** às ***DEFINIR***

---
```

---

## **Participantes da Reunião**
Inserir os participantes da reunião, especificando a `INSTITUIÇÃO` de cada Stakeholder participante da reunião, com e-mail para `CONTATO` e o `STATUS` (Presente ou Ausente).

```md
---
### **PARTICIPANTES**

|  INSTITUIÇÃO  |      NOME     | CONTATO  |  STATUS  |
| ------------- | ------------- | -------- | -------- |
| Instituição 1 | Stakeholder 1 | e-mail 1 | Presente |
| Instituição 2 | Stakeholder 2 | e-mail 2 | Presente |

---
```

---

## **Assuntos Tratados**
A pauta ou os tópicos tratados durante a execução da reunião.

```md
---
### **ASSUNTOS TRATADOS**

- Assunto 1;
- Assunto 2;
- etc.

---
```

---

## **Uma forma de organizar o documento final**
Dependendo da extensão do documento, talvez seja necessário uma forma de `quebrar a página`. O código `html` abaixo, nos auxilia na formatação do documento `.pdf` que será gerado.

```html
<div style="page-break-after: always;"></div>
```
---

## **Conteúdo discutido na reunião**
Devem ser transcritas as discussões realizadas durante o período vigente da reunião, de forma a solucionar a pauta proposta para a reunião.

```md
---
### **DISCUSSÕES**

- A reunião com a equipe presente foi iniciada às ***DEFINIR***;
- (Anotações da reunião);
- A reunião foi encerrada às ***DEFINIR***.

---
```
---

## **Próximos passos e ações**
Devem ser explicitados as ações definidas durante a reunião, com o `RESPONSÁVEL` pela execução da ação e a `DATA LIMITE` estipulada durante as discussões. Como exemplo, ao final da leitura deste *post* é sugerido o *download* do software [Obsidian](https://obsidian.md/).

```md
---
### **AÇÕES E PRÓXIMOS PASSOS**

|     **AÇÕES**     | **RESPONSÁVEL** | **DATA LIMITE** |
| ----------------- | --------------- | --------------- |
| Baixar o Obsidian | Eu              |     JAN/23      |

---
```

---

## **Assinatura dos *Stakeholders***
De acordo com o PMBOK 7ª edição:
> *Stakeholders* são indivíduos, grupos de indivíduos ou organizações que podem influenciar, ser influenciados, ou se perceber como influenciados por uma decisão, atividade ou resultado de um projeto, programa ou portfólio. - **Pmbok, 7th ed, p.250**

Abaixo, é proposto um local para a formalização dos aceites dos *Stakeholders* do projeto, e o marco para sinalizar o término da ATA redigida:

```html
### **ASSINATURAS**
<p style="text-align:center;">
<br><br>________________________________________________________<br>
<b>Stakeholder 1</b>
<br>Cargo/Função - Instituição 1</p>

<p style="text-align:center;">
<br><br>________________________________________________________ <br>
<b>Stakeholder 2</b>
<br>Cargo/Função - Instituição 2</p>

---
<p style="text-align:center;"><i>FIM DO DOCUMENTO</i></p>
```

---

## **Criação do arquivo .pdf**
Após a elaboração da ATA, conforme os tópicos apresentados, é necessário a criação do arquivo `.pdf` para o posterior compartilhamento do documento.

- **(i)** Com o [Obsidian](https://obsidian.md/) aberto, clique nos 3 pontos situados no canto superior direito: 
{{< figure src="/img/ata1.png" align="center" >}}

- **(ii)** Irá abrir um menu com diversas opções, selecione a opção `Export to PDF`:
{{< figure src="/img/ata2.png" align="center" >}}

- **(iii)** Finalmente, clique na opção `Export to PDF`:
{{< figure src="/img/ata3.png" align="center" >}}

- **(iv)** Será gerado o documento abaixo (exemplo):
{{< embed-pdf url="/misc/Untitled.pdf" >}}

---

## **Próximos passos**
Após gerar o documento `PDF`, podemos otimizar o nosso tempo duplicando o arquivo `markdown` no próprio [Obsidian](https://obsidian.md/) ou criando *templates* para este e outros tipos de documento, como p. ex. ERRATA, *meeting notes*, etc.
