---
title: 'Lync Server 2013: Get-CsAddressBookConfiguration pour la gestion du carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32cf7be49d38db8f0b5b520247830f65cac5a3c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Get-CsAddressBookConfiguration pour la gestion du carnet d’adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Qui peut exécuter cette applet de commande: par défaut, les membres des groupes suivants sont autorisés à exécuter l’applet de commande Get-CsAddressBookConfiguration localement: RTCUniversalServerAdmins. Pour renvoyer la liste de tous les rôles de contrôle d’accès basés sur des rôles (RBAC) affectés à cette applet de commande (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de l’invite Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

La cmdlet Get-CsAddressBookConfiguration renvoie des informations sur une configuration qui existe déjà.

Par exemple :

    Get-CsAddressBookConfiguration -Identity site:Redmond

Le regroupement de fonctionnalités de Get-CsAddressBookConfiguration et de Set-CsAddressBookConfiguration permet à l’administrateur de définir les configurations à modifier, puis d’appliquer les modifications. Par exemple, l’Association suivante:

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

Renvoie toutes les configurations de tous les sites et applique le RunTimeOfDay de 23:00 heures aux configurations.

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

