---
title: 'Lync Server 2013: New-CsClientPolicy pour la gestion du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New-CsClientPolicy for Address Book management
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429726(v=OCS.15)
ms:contentKeyID: 48185771
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf1f7ebe085fc11d23381db9d1c474c79403d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-csclientpolicy-for-address-book-management-in-lync-server-2013"></a>Nouveauté-CsClientPolicy pour la gestion du carnet d’adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Qui peut exécuter cette applet de commande: par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande New-CsClientPolicy: RTCUniversalServerAdmins. Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

Le cmdlet New-CsClientPolicy définit un grand nombre de paramètres pour les clients de mise en service pour les fonctionnalités disponibles dans Lync Server 2013. Pour le service de carnet d’adresses, le paramètre AddressBookAvailability est intéressant. Ce paramètre a un impact direct sur les options disponibles pour les clients et propose trois options possibles:

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

Détermine la manière dont les clients peuvent accéder au carnet d’adresses. Si vous définissez ce paramètre, vous devez définir une des options. Si vous ne modifiez pas ce paramètre, le WebSearchAndFileDownload par défaut reste en vigueur.

Par exemple :

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

<div>

## <a name="see-also"></a>Voir aussi


[New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

