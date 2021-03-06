---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Plug-in
{: #ibmcloud_commands_settings}

Use os comandos a seguir para gerenciar os plug-ins da CLI do {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="Comandos ibmcloud que podem ser usados para gerenciar os plug-ins da CLI do {{site.data.keyword.Bluemix_notm}}.">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud plugin repo-add](cli_plugin.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_plugin.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_plugin.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_plugin.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](cli_plugin.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_plugin.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_plugin.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_plugin.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](cli_plugin.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud plugin repos](cli_plugin.html#ibmcloud_plugin_repos)</td>
</tr>
 </tbody>
 </table>


 ## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Listar todos os repositórios de plug-in que estão registrados na CLI do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repos
```

<strong>Pré-requisitos</strong>: Nenhum

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Incluir um novo repositório de plug-in na CLI do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>REPO_NAME (necessário)</dt>
   <dd>O nome do repositório a ser incluído. É possível definir seu próprio nome para cada repositório.</dd>
   <dt>REPO_URL (necessário)</dt>
   <dd>A URL do repositório a ser incluído. A URL do repositório deve conter o protocolo (por exemplo, http://plugins.ng.bluemix.net em vez de plugins.ng.bluemix.net). http://plugins.ng.bluemix.net é o repositório de plug-in oficial da CLI do {{site.data.keyword.Bluemix_notm}}.</dd>
    </dl>


<strong>Exemplos</strong>:

Incluir o repositório de plug-in oficial da CLI do {{site.data.keyword.Bluemix_notm}} como `bluemix-repo`:

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Remover um repositório de plug-in da CLI do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
   <dl>
   <dt>REPO_NAME (necessário)</dt>
   <dd>O nome do repositório a ser removido.</dd>
   </dl>

<strong>Exemplos</strong>:

Remova o repositório `bluemix-repo` da CLI do {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud plugin repo-remove bluemix-repo
```

## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

Listar todos os plug-ins disponíveis em todos os repositórios incluídos ou em um repositório específico.

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>Liste somente os plug-ins no repositório especificado.</dd>
   </dl>

<strong>Exemplos</strong>:

Liste todos os plug-ins em todos os repositórios incluídos:

```
ibmcloud plugin repo-plugins
```

Listar todos os plug-ins no repositório `bluemix-repo`:

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Mostrar os detalhes de um plug-in no repositório.

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>O nome do repositório. Se nenhum repositório for especificado, o comando usará o plug-in padrão repository.å</dd>
   </dl>

<strong>Exemplos</strong>:

Listar detalhes do plug-in "IBM-Containers" no repositório "sample-repo":

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

Listar detalhes do plug-in "IBM-Containers" no repositório padrão

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

Listar todos os plug-ins instalados na CLI do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin list
```

<strong>Pré-requisitos</strong>: Nenhum

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

Mostrar detalhes de um plug-in instalado.

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>Pré-requisitos</strong>: Nenhum

## ibmcloud plugin install
{: #ibmcloud_plugin_install}

Instalar a versão específica de plug-in na CLI do {{site.data.keyword.Bluemix_notm}} por meio do caminho ou do repositório especificado.

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

Se nenhum repositório for especificado, o comando usará o repositório de plug-in padrão 'Bluemix'.
Se nenhuma versão for especificada, o comando selecionará a versão mais recente disponível para instalação.

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (obrigatório)</dt>
   <dd>Se -r <i>REPO_NAME</i> não for especificado, o plug-in será instalado por meio do caminho local ou da URL remota especificada.</dd>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>O nome do repositório no qual o binário do plug-in está localizado. Se nenhum repositório for especificado, o comando usará o repositório de plug-in padrão 'Bluemix'.</dd>
   <dt>-v <i>VERSION</i> (opcional)</dt>
   <dd>A versão do plug-in a ser instalado. Se não fornecida, a versão mais recente do plug-in será instalada. Essa opção é válida somente quando você instala o plug-in por meio do repositório.</dd>
   <dt>-f </dt>
   <dd>Forçar instalação do plug-in sem confirmação.</dd>
    </dl>


A CLI do {{site.data.keyword.Bluemix_notm}} tem o nome oficial do repositório de
`Bluemix`.

<strong>Exemplos</strong>:

Instalar um plug-in por meio do arquivo local:

```
ibmcloud plugin install /downloads/new_plugin
```

Instalar um plug-in por meio da URL remota:

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Instalar o plug-in 'container-service' da versão mais recente por meio do repositório 'Bluemix':

```
ibmcloud plugin install container-service -r Bluemix
```

ou apenas:

```
ibmcloud plugin install container-service
```

Instalar o plug-in 'container-service' com a versão '0.1.425' por meio do repositório de plug-in oficial:

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

Fazer upgrade do plug-in por meio de um repositório.

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

Se nenhum repositório for especificado, o comando usará o repositório de plug-in padrão 'Bluemix'.
Se nenhuma versão for especificada, o comando selecionará a versão mais recente disponível para instalação.

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>Nome do plug-in a ser atualizado. Se não especificado, o comando verificará os upgrades de todos os plug-ins instalados.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>O nome do repositório no qual o binário do plug-in está localizado. Se não especificado, o comando usará
o repositório de plug-in padrão 'Bluemix'.</dd>
 <dt>-v <i>VERSION</i> (opcional)</dt>
 <dd>A versão para a qual o plug-in será atualizado. Se não fornecida, atualize o plug-in para a versão mais recente disponível.</dd>
 <dt>--all</dt>
 <dd>Atualizar todos os plug-ins disponíveis</dd>
</dl>

<strong>Exemplos</strong>:

Procurar por todos os upgrades disponíveis no repositório de plug-in oficial 'Bluemix':

```
ibmcloud plugin update -r Bluemix
```

ou apenas:

```
ibmcloud plugin update
```

Plug-in de upgrade 'container-service' no repositório de plug-in oficial para o mais recente:

```
ibmcloud plugin update container-service
```

Atualizar o plug-in 'container-service' no repositório de plug-in oficial para a versão '0.1.440':

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Desinstalar o plug-in especificado da CLI do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>PLUGIN_NAME (necessário)</dt>
   <dd>O nome do plug-in a ser desinstalado.</dd>
    </dl>

<strong>Exemplos</strong>:

Desinstalar o plug-in 'container-service' que foi instalado anteriormente:

```
ibmcloud plugin uninstall container-service
```
