---
title: 'Lync Server 2013 : cmdlets du serveur de carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Address Book Server cmdlets
ms:assetid: 33da45da-3c57-4d04-9679-f0e5a0cfd37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415643(v=OCS.15)
ms:contentKeyID: 48183793
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1782dbc22b94ed492878c545df70fa1bdaaeeeb3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="address-book-server-cmdlets-in-lync-server-2013"></a>Cmdlets de serveur de carnet d’adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-26_

Les serveurs de carnet d’adresses sont des intermédiaires entre les services de domaine Active Directory et Microsoft Lync Server 2013. Le serveur de carnet d’adresses garantit que les informations utilisateur stockées dans Lync Server 2013 sont synchronisées avec les informations utilisateur stockées dans Active Directory. Pour ce faire, les fichiers de carnet d’adresses sont régulièrement synchronisés avec les informations contenues dans la base de données utilisateur. En retour, Lync Server inclut un certain nombre d’applets de commande pour la gestion des serveurs de carnet d’adresses.

<div>

## <a name="address-book-server-cmdlets"></a>Applets de commande pour le serveur de carnet d’adresses

Vous ne pouvez pas configurer les paramètres du serveur de carnet d’adresses dans le panneau de configuration Lync Server. Windows PowerShell est l’outil principal pour la gestion de ces paramètres. La liste suivante indique les applets de commande directement associées à la gestion des serveurs de carnet d’adresses :

**Serveur de carnet d’adresses**

  - <span></span>  
    [Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - <span></span>  
    [New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - <span></span>  
    [Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - <span></span>  
    [Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

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

