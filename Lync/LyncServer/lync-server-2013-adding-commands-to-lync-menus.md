---
title: 'Lync Server 2013 : ajout de commandes aux menus de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 738f745d4f91458b95e95e5cc5770c34ed4e8c88
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521351"
---
# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Ajout de commandes aux menus Lync dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-04-11_

Vous pouvez ajouter des commandes personnalisées aux menus Lync 2013 et transmettre l’URI (Uniform Resource Identifier) SIP de l’utilisateur actuel et des contacts sélectionnés à l’application de démarrage de la commande personnalisée.

Les commandes personnalisées que vous ajoutez peuvent apparaître sur un ou plusieurs des menus suivants :

  - Le menu Outils, sur la barre de menus dans la fenêtre principale Lync

  - Le menu contextuel pour les contacts dans la liste des contacts

  - Menu autres options, dans la fenêtre de conversation

  - Le menu contextuel pour les personnes mentionnées sur la liste des participants dans la fenêtre de conversation

  - Le menu options dans une carte de visite

Vous pouvez définir des commandes personnalisées pour deux types d'applications possédant une des caractéristiques suivantes :

  - S’appliquer uniquement à l’utilisateur actuel et être lancées sur l’ordinateur local.

  - Englober des utilisateurs supplémentaires, comme par exemple un programme de collaboration en ligne, et devant être lancées sur l’ordinateur de chaque utilisateur.

La commande personnalisée peut être appelée des manières suivantes :

  - Sélectionner un ou plusieurs utilisateurs puis choisir la commande personnalisée.

  - Commencer une conversation entre deux ou plusieurs parties, puis choisir la commande personnalisée.

<div>

## <a name="to-add-a-custom-command"></a>Pour ajouter une commande personnalisée

Utilisez les paramètres de Registre du tableau suivant pour ajouter une commande aux menus. Ces entrées sont placées dans le registre à l’un des emplacements suivants :

  - Pour le système d’exploitation 32 bits : le \_ \_ \\ logiciel \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ sessionmanager \\ apps de l’ordinateur local

  - Pour 64 bits : HKEY \_ \_ Software local \\ machine \\ Wow6432Node \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ sessionmanager \\ apps

### <a name="custom-command-registry-entries"></a>Entrées du registre de commandes personnalisées

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
<td><p>DWORD</p></td>
<td><p>0 = exécutable (par défaut)</p>
<div>

> [!NOTE]  
> Requiert ApplicationInstallPath.


</div>
<p>1 = protocole</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Chemin d’accès complet de l’exécutable.</p>
<div>

> [!NOTE]  
> Doit être spécifié si l’ApplicationType est 0 (exécutable).


</div></td>
</tr>
<tr class="even">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Chemin d’accès complet à lancer avec des paramètres, y compris les paramètres par défaut <em>%user-id%</em> et <em>%contact-id%</em>.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Session locale. L’application démarre sur l’ordinateur local.</p>
<p>1 = Session à deux personnes (par défaut). Lync 2013 démarre l’application localement, puis envoie une notification de bureau à l’autre utilisateur. Ce dernier clique alors sur la notification pour lancer l’application spécifiée sur son ordinateur.</p>
<p>2 = Session à plusieurs. Lync 2013 démarre l’application localement, puis envoie des notifications de bureau aux autres utilisateurs. L’autre utilisateur clique sur la notification pour démarrer l’application spécifiée sur son ordinateur.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Liste des menus dans lesquels cette commande apparaît, séparés par des points-virgules. Les valeurs possibles sont les suivantes :</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</p></td>
</tr>
</tbody>
</table>


Par exemple, le fichier suivant de l’Editeur du Registre (.REG) montre les résultats de l'addition d'un point de menu Gestionnaire de contacts vente Contoso à un menu Actions dans la fenêtre de conversation :

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

Pour accéder à une commande personnalisée une fois qu’elle a été ajoutée, effectuez l’une des opérations suivantes, en fonction des valeurs ExtensibleMenu que vous définissez :

  - **MainWindowActions**     Dans la fenêtre principale Lync, cliquez sur **Outils**, puis sur votre commande personnalisée.

  - **MainWindowRightClick**     Dans la fenêtre principale Lync, cliquez avec le bouton droit sur un contact, puis cliquez sur votre commande personnalisée.

  - **ConversationWindowActions**     Dans la fenêtre de conversation, cliquez sur l’icône **autres options** , puis sur votre commande personnalisée.

  - **ConversationWindowRightClick**     Dans la fenêtre de conversation, cliquez avec le bouton droit sur le nom d’un contact, puis cliquez sur votre commande personnalisée.

</div>

</div>

<span> </span>

</div>

</div>

</div>

