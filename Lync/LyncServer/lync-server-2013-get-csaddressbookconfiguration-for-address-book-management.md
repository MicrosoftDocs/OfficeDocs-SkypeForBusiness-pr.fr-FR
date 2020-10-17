---
title: 'Lync Server 2013 : Get-CsAddressBookConfiguration pour la gestion des carnets d’adresses'
description: 'Lync Server 2013 : Get-CsAddressBookConfiguration pour la gestion des carnets d’adresses.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsAddressBookConfiguration for Address Book management
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429721(v=OCS.15)
ms:contentKeyID: 48185264
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91b96aead7b7038464f3166691a5952b9ff850dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567000"
---
# <a name="get-csaddressbookconfiguration-for-address-book-management-in-lync-server-2013"></a>Get-CsAddressBookConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement l’applet de commande Get-CsAddressBookConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

L’applet de commande Get-CsAddressBookConfiguration retourne des informations sur une configuration qui existe déjà.

Par exemple :

    Get-CsAddressBookConfiguration -Identity site:Redmond

L’association fonctionnelle des applets de commande Get-CsAddressBookConfiguration et Set-CsAddressBookConfiguration permet à l’administrateur de définir les configurations à modifier, puis d’apporter les modifications. Par exemple, la combinaison suivante :

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

Retourne toutes les configurations dans tous les sites et applique la propriété RunTimeOfDay définie sur 23:00 aux configurations.

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsAddressBookConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAddressBookConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

