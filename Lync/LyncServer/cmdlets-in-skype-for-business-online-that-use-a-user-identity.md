---
title: Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur
description: Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f838317f8b2779de862eb2df82ae1b348871e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545650"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur

 


Dans Skype entreprise Online, il existe plusieurs façons de faire référence à une identité d’utilisateur spécifique :

  - Utiliser le nom d’affichage des services de domaine Active Directory de l’utilisateur. Par exemple :
    
        -Identity "Ken Myer"

  - Utilisez l’adresse SIP de l’utilisateur. Par exemple :
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Utilisez le nom d’utilisateur principal de l’utilisateur. Par exemple :
    
        -Identity " kenmyer@litwareinc.com"

  - Utilisez le nom unique des services de domaine Active Directory de l’utilisateur. Par exemple :
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

Les applets de commande suivantes acceptent une identité d’utilisateur :

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))

  - [Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))

  - [Get-CsOnlineUser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))

  - [New-CsExUmContact](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))

  - [Remove-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))

  - [Remove-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))

  - [Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))

  - [Set-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))

Notez que vous n’avez pas besoin de spécifier l’identité d’un utilisateur lors de l’appel de l’une des cmdlets **Get-CS** . Dans ce cas, les cmdlets renvoient toutes les instances de l’élément spécifié. Par exemple, cette commande renvoie des informations sur tous les utilisateurs qui ont été activés pour Skype entreprise Online :

    Get-CsOnlineUser

Le paramètre Identity est obligatoire uniquement si vous souhaitez renvoyer des informations sur un utilisateur spécifique :

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>Voir aussi


[Identités, étendues et locataires dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

