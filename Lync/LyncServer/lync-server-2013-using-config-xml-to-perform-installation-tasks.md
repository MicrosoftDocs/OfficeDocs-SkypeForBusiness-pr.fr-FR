---
title: 'Lync Server 2013 : utilisation du fichier config. xml pour effectuer des tâches d’installation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2933da3fc52cc6a5c23f74806ff3a4e81dcb2ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>Utilisation de config. xml pour effectuer des tâches d’installation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Bien que l’outil de personnalisation Office soit le principal outil pour l’installation personnalisée, les administrateurs peuvent utiliser le fichier Config.xml pour spécifier des instructions d’installation non disponibles dans cet outil. Les personnalisations suivantes ne peuvent être effectuées qu’avec le fichier Config.xml :

  - spécifier le chemin d’accès au point d’installation réseau ;

  - sélectionner les produits à installer ;

  - configurer la journalisation et l’emplacement du fichier de personnalisation de l’installation et les mises à jour des logiciels ;

  - spécifier les options d’installation telles que le nom de l’utilisateur ;

  - copier la source d’installation locale sur l’ordinateur de l’utilisateur sans installer Office ;

  - ajouter ou supprimer des langues de l’installation.

Nous vous recommandons d’utiliser le fichier config. xml pour configurer l’installation en mode silencieux de Lync 2013.

Par défaut, le fichier config. XML qui est stocké dans le dossier du produit principal (par \\exemple, produit. WW) indique au programme d’installation d’installer ce produit. Par exemple, le fichier config. xml dans le dossier suivant installe Lync 2013 :

  - \\\\partage\\\\du serveur\\Lync15 Lync. \\WW config. Xml

Les éléments config. XML les plus couramment utilisés pour l’installation de Lync 2013 sont répertoriés dans le tableau suivant.

### <a name="configxml-elements"></a>Éléments de Config.xml

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Élément</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuration</p></td>
<td><p>Élément de niveau supérieur (obligatoire). Contient l’attribut Product, par exemple : Product=Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>Spécifie la façon dont des fonctionnalités de produits spécifiques sont gérées pendant l’installation. Utilisez les attributs suivants pour empêcher l’installation de Business Connectivity Services, qui inclut les composants partagés qui interfèrent avec Outlook 2010 :</p>
<ul>
<li><p>ID =&quot;LOBiMain&quot;</p></li>
<li><p>État =&quot;absent&quot;</p></li>
<li><p>Enfants =&quot;force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Display</p></td>
<td><p>Niveau d’interface utilisateur affiché pour l’utilisateur par le programme d’installation. Les attributs type sont les suivants :</p>
<ul>
<li><p>CompletionNotice =&quot;oui&quot; | &quot;non&quot;(par défaut)</p></li>
<li><p>AcceptEULA =&quot;oui&quot; | &quot;non&quot;(par défaut)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Logging</p></td>
<td><p>Options déterminant le type de journalisation mis en œuvre par le programme d’installation. Les attributs types sont les suivants :</p>
<ul>
<li><p>Type =&quot;désactivé&quot; | &quot;standard&quot;(par défaut) | &quot;Commentaires&quot;</p></li>
<li><p>Template=”nomfichier.txt” (nom du fichier journal)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Paramètres</p></td>
<td><p>Spécifie les valeurs des propriétés de Windows Installer. Les attributs type sont les suivants :</p>
<ul>
<li><p>ID de paramètre&quot;=&quot; nom (nom de la propriété Windows Installer)</p></li>
<li><p>Value =&quot;valeur&quot; (valeur à affecter à la propriété)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>Chemin d’accès complet du point d’installation réseau à partir duquel l’installation doit s’exécuter. Comprend l’attribut Location :</p>
<ul>
<li><p>Location = "chemin d’accès"</p></li>
</ul></td>
</tr>
</tbody>
</table>


L’exemple suivant montre un fichier config. xml pour une installation en mode silencieux classique de Lync 2013.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Des informations détaillées sur l’utilisation du fichier config. xml pour effectuer des tâches d’installation et de <https://go.microsoft.com/fwlink/p/?linkid=267514>maintenance d’Office sont disponibles à l’adresse.

<div>

## <a name="to-customize-the-configxml-file"></a>Pour personnaliser le fichier Config.xml

1.  Ouvrez le fichier Config.xml avec un éditeur de texte, tel que le Bloc-notes.

2.  Recherchez les lignes qui contiennent les éléments que vous voulez changer.

3.  Modifiez l’entrée de l’élément avec les options automatisées que vous voulez utiliser. Veillez à supprimer les délimiteurs de commentaire, «\<\!-- » et « --\>». Par exemple, utilisez la syntaxe suivante :
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Enregistrez le fichier Config.xml.

</div>

</div>

<span> </span>

</div>

</div>

</div>

