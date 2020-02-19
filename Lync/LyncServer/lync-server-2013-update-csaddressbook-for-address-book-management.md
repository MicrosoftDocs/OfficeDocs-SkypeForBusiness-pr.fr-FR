---
title: 'Lync Server 2013 : Update-CsAddressBook pour la gestion des carnets d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dc4452eadb1584f9e99e9b1b3508e507c2e8fff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a>Update-CsAddressBook pour la gestion des carnets d’adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes suivants sont autorisés à exécuter localement l’applet de commande Update-CsAddressBook : RTCUniversalUserAdmins, RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

L’applet de commande Update-CsAddressBook remplace la commande **abserver.exe –syncNow** d’Office Communications Server. Cette applet de commande sert à lancer une synchronisation immédiatement au lieu d’attendre qu’elle s’effectue à l’heure initialement prévue. Dans le premier exemple, la commande met à jour tous les carnets d’adresses dans l’organisation. Dans le second exemple, elle met uniquement à jour le carnet d’adresses associé au serveur défini.

<div>


> [!NOTE]  
> Dans Lync Server 2013, le réplicateur d’utilisateurs Lync Server récupère les modifications à partir d’Active Directory et met à jour la base de données utilisateur Lync Server en fonction d’un intervalle configuré. Lync Server User Replicator propagera également les modifications à la base de données RTCab rapidement, sans que l’administrateur doive exécuter Update-CSAddressBook. Les administrateurs devront seulement exécuter Update-CSAddressBook si le téléchargement du fichier de carnet d’adresses est activé.



</div>

Par exemple :

   ```PowerShell
    Update-CsAddressBook
   ```

   ```PowerShell
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a>Voir aussi


[Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

