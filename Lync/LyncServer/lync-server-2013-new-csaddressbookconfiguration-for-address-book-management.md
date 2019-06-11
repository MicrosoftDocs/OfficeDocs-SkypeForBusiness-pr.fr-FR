---
title: 'Lync Server 2013: New-CsAddressBookConfiguration pour la gestion du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsAddressBookConfiguration for Address Book management
ms:assetid: a58ddc8c-ae04-4141-b69e-e45374a67d72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429718(v=OCS.15)
ms:contentKeyID: 48184985
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a11829a6c0dd4e53f5684e5b950e3adf755811
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Nouveauté-CsAddressBookConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Qui peut exécuter cette applet de commande: par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande New-CsAddressBookConfiguration: RTCUniversalServerAdmins. Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsAddressBookConfiguration"}

L’applet de nouvelle applet de nouveau-CsAddressBookConfiguration crée une nouvelle configuration pour gérer le comportement du carnet d’adresses. Spécifiques à cette applet de commande permet de définir si le service de carnet d’adresses crée les fichiers de téléchargement du client, la façon dont les règles de normalisation sont utilisées et la durée de conservation des fichiers delta et compacts, ainsi que la taille du fichier Delta heure de la journée de création du carnet d’adresses du fichier complet et ce qu’il doit être de la synchronisation des informations de la base de données utilisateur.

Par exemple :

    New-CsAddressBookConfiguration -Identity site:Redmond -KeepDuration 15 -SynchronizePollingInterval 00:10:00

<div>

## <a name="see-also"></a>Voir aussi


[New-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

