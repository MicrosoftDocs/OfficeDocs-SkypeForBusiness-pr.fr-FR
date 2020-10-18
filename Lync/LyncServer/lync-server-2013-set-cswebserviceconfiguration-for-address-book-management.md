---
title: 'Lync Server 2013 : Set-CsWebServiceConfiguration pour la gestion des carnets d’adresses'
description: 'Lync Server 2013 : Set-CsWebServiceConfiguration pour la gestion des carnets d’adresses.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set-CsWebServiceConfiguration for Address Book management
ms:assetid: 79d0edf5-23f3-4845-a7b7-e11b5a928bab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429709(v=OCS.15)
ms:contentKeyID: 48184572
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37dcd7676829c5a91e05667fa0ae0d74dc6f7dc1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575420"
---
# <a name="set-cswebserviceconfiguration-for-address-book-management-in-lync-server-2013"></a>Set-CsWebServiceConfiguration pour la gestion des carnets d’adresses dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Personnes autorisées à exécuter cette applet de commande : Par défaut, les membres des groupes qui suivent sont autorisés à exécuter localement l’applet de commande Set-CsWebServiceConfiguration : RTCUniversalServerAdmins. Pour retourner une liste de tous les rôles RBAC (Contrôle d’accès basé sur un rôle) auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés créés par vos soins), exécutez la commande suivante depuis l’invite Windows PowerShell :

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsWebServiceConfiguration"}

L’applet de commande Set-CsWebServiceConfiguration permet à l’administrateur de redéfinir un attribut existant dans la configuration des services web.

Par exemple :

    Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True

<div>

## <a name="see-also"></a>Voir aussi


[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

