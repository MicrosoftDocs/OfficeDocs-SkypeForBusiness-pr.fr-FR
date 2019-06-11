---
title: 'Lync Server 2013: ajout de commandes aux menus Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Ajouter des commandes aux menus Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-04-11_

Vous pouvez ajouter des commandes personnalisées aux menus de Lync 2013 et transmettre l’URI (Uniform Resource Identifier) SIP de l’utilisateur actuel et des contacts sélectionnés à l’application qui démarre la commande personnalisée.

Les commandes personnalisées que vous ajoutez peuvent apparaître dans un ou plusieurs des menus suivants:

  - Menu Outils, dans la barre de menus de la fenêtre principale de Lync

  - Menu contextuel des contacts de la liste de contacts

  - Menu autres options, dans la fenêtre de conversation

  - Menu contextuel pour les personnes figurant dans la liste des participants de la fenêtre de conversation

  - Menu options dans une carte de visite

Vous pouvez définir des commandes personnalisées pour deux types d’applications (applications qui effectuent l’une des opérations suivantes:

  - S’applique uniquement à l’utilisateur actuel et est démarré sur l’ordinateur local.

  - Impliquez des utilisateurs supplémentaires, tels qu’un programme de collaboration en ligne, qui doivent être démarrés sur l’ordinateur de chaque utilisateur.

La commande personnalisée peut être appelée de l’une des façons suivantes:

  - Sélectionnez un ou plusieurs utilisateurs, puis choisissez la commande personnalisée.

  - Démarrer une conversation à deux ou plusieurs parties, puis sélectionner la commande personnalisée.

<div>

## <a name="to-add-a-custom-command"></a>Pour ajouter une commande personnalisée

Utilisez les paramètres de Registre du tableau suivant pour ajouter une commande aux menus. Ces entrées sont placées dans le registre à l’un des emplacements suivants:

  - Pour le système d’exploitation\_32\_bits\\:\\HKEY\\logiciel\\de\\l'\\ordinateur\\local Microsoft Office 15,0 des applications Lync sessionmanager

  - Pour les systèmes d’exploitation\_64\_bits\\:\\HKEY\\logiciel\\de\\l'\\ordinateur\\local\\Wow6432Node Microsoft Office 15,0 Lync sessionmanager apps

### <a name="custom-command-registry-entries"></a>Entrées de registre de commandes personnalisées

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Type</th>
<th>Données</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nom</p></td>
<td><p>REG_SZ</p></td>
<td><p>Nom de l’application tel qu’il apparaît dans le menu.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>INSÉRÉ</p></td>
<td><p>0 = exécutable (par défaut)</p>
<div>

> [!NOTE]  
> Nécessite ApplicationInstallPath.


</div>
<p>1 = Protocole</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Chemin d’accès complet du fichier exécutable.</p>
<div>

> [!NOTE]  
> Doit être spécifié si ApplicationType est défini sur 0 (exécutable).


</div></td>
</tr>
<tr class="even">
<td><p> Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Chemin complet pour démarrer avec tout autre paramètre, y compris les paramètres par défaut <em>% User-ID%</em> et% <em>contact-ID%</em>.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>INSÉRÉ</p></td>
<td><p>0 = session locale. L’application est démarrée sur l’ordinateur local.</p>
<p>1 = session à deux parties (par défaut). Lync 2013 démarre l’application localement, puis envoie une notification de bureau à l’autre utilisateur. L’autre utilisateur clique sur la notification pour démarrer l’application sur son ordinateur.</p>
<p>2 = session multipartie. Lync 2013 démarre l’application localement, puis envoie des notifications de bureau aux autres utilisateurs. L’autre utilisateur clique sur la notification pour démarrer l’application spécifiée sur son ordinateur.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Liste des menus dans lesquels cette commande s’affiche, en les séparant par un point-virgule. Valeurs possibles :</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</p></td>
</tr>
</tbody>
</table>


Par exemple, l’éditeur du Registre suivant (. REG) affiche les résultats de l’ajout d’un élément de menu du gestionnaire de contacts commerciaux contoso au menu actions dans la fenêtre de conversation:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a>Pour accéder à une commande personnalisée

Pour accéder à une commande personnalisée après l’avoir ajoutée, effectuez l’une des opérations suivantes, en fonction des valeurs ExtensibleMenu que vous définissez:

  - **MainWindowActions**   dans la fenêtre principale de Lync, cliquez sur **Outils**, puis sur votre commande personnalisée.

  - **MainWindowRightClick**   dans la fenêtre principale de Lync, cliquez avec le bouton droit sur un contact, puis cliquez sur votre commande personnalisée.

  - **ConversationWindowActions**   dans la fenêtre de conversation, cliquez sur l’icône **plus d’options** , puis cliquez sur votre commande personnalisée.

  - **ConversationWindowRightClick**   dans la fenêtre de conversation, cliquez avec le bouton droit sur le nom d’un contact, puis cliquez sur votre commande personnalisée.

</div>

</div>

<span> </span>

</div>

</div>

</div>

