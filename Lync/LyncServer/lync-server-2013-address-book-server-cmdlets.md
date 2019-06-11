---
title: 'Lync Server 2013: cmdlets du serveur du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 634e6ae86a68cece6472d04ba1870159dc9b866f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a>Cmdlets du serveur du carnet d’adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-26_

Les serveurs de carnets d’adresses sont intermédiaires entre les services de domaine Active Directory et Microsoft Lync Server 2013. Le serveur du carnet d’adresses vérifie que les informations utilisateur stockées dans Lync Server 2013 sont synchronisées avec les informations utilisateur stockées dans Active Directory. Pour cela, la synchronisation périodique des fichiers du carnet d’adresses et des informations stockées dans la base de données utilisateur. À son tour, Lync Server inclut plusieurs cmdlets pour la gestion des serveurs du carnet d’adresses.

<div>

## <a name="address-book-server-cmdlets"></a>Cmdlets du serveur du carnet d’adresses

Vous ne pouvez pas configurer les paramètres de serveur du carnet d’adresses dans Lync Server Control Panel. Windows PowerShell est l’outil principal de gestion de ces paramètres. La liste suivante répertorie les applets de commande qui concernent directement la gestion du serveur du carnet d’adresses:

**Serveur de carnet d’adresses**

  - <span></span>  
    [Get-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))

  - <span></span>  
    [Nouveau-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))

  - <span></span>  
    [Remove-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))

  - <span></span>  
    [Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Update-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Blog Lync Server PowerShell](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

