# Importação de Content Pack no Graylog

Este guia descreve o procedimento para importar um **Content Pack** no Graylog a partir de um arquivo `.json` previamente exportado.

---

## Pré-requisitos

* Acesso administrativo ao Graylog
* Arquivo do Content Pack (`.json`)
* Streams, Index Sets e Inputs já existentes (ou planejados) no ambiente de destino

---

## Passo a passo para importação

### 1. Acessar o menu de Content Packs

No Graylog, navegue até:

```
System → Content Packs
```

---

### 2. Fazer upload do Content Pack

1. Clique em **Upload**
2. Selecione o arquivo `.json` exportado
3. Aguarde o upload ser concluído

---

### 3. Instalar o Content Pack

Após o upload:

1. Localize o Content Pack na lista
2. Clique em **Install**
3. Será exibida a tela de configuração de parâmetros (se aplicável)

---

### 4. Configurar parâmetros (se necessário)

Dependendo de como o Content Pack foi criado, você pode precisar mapear:

* **Streams**
* **Index Sets**
* **Inputs**
* **IDs específicos do ambiente**

⚠️ Atenção:

* Certifique-se de que os recursos referenciados existem no ambiente de destino
* Caso não existam, crie-os antes de concluir a instalação

---

### 5. Confirmar a instalação

* Revise as configurações
* Clique em **Install**
* Aguarde a conclusão do processo

---

## Pós-importação

Após a instalação:

* Verifique se os **dashboards** foram criados corretamente
* Confirme se as **queries** estão retornando dados
* Ajuste permissões de acesso, se necessário
* Valide se os **streams** estão recebendo logs corretamente

---

## Problemas comuns

| Problema           | Possível causa        | Solução                  |
| ------------------ | --------------------- | ------------------------ |
| Dashboard vazio    | Streams diferentes    | Ajustar stream na search |
| Erro na importação | Dependências ausentes | Criar recursos antes     |
| Dados não aparecem | Index set incorreto   | Validar configuração     |

---

## Boas práticas

* Padronizar nomes de streams e index sets entre ambientes
* Versionar o arquivo `.json` no repositório (como já feito)
* Documentar dependências no próprio repositório
* Testar primeiro em ambiente de homologação

---

## Observação

Content Packs podem incluir múltiplos objetos interdependentes, como:

* Dashboards
* Searches
* Streams
* Event Definitions

Por isso, sempre valide o ambiente antes e depois da importação.

---

## Exemplo de uso

```bash
# Apenas referência - a importação é feita via interface web
# Não há comando CLI oficial para instalação direta
```

---

## 👨‍💻 Autor

Procedimento documentado para padronização de ambientes Graylog e reuso de dashboards.

---
