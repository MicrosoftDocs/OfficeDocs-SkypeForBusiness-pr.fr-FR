---
title: Cmdlets dans Skype entreprise Online utilisant une identité d’utilisateur
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce46e700a65f00625aeebad1032c54a5affeaa19
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233112"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>Cmdlets dans Skype entreprise Online utilisant une identité d’utilisateur

 


Dans Skype entreprise Online, il existe plusieurs façons de faire référence à une identité d’utilisateur individuelle:

  - Utilisez le nom complet des services de domaine Active Directory de l’utilisateur. Par exemple :
    
        -Identity "Ken Myer"

  - Utilisez l’adresse SIP de l’utilisateur. Par exemple :
    
        -Identity "sip:kenmyer@litwareinc.com"

  - Utilisez le nom d’utilisateur principal de l’utilisateur. Par exemple :
    
        -Identity " kenmyer@litwareinc.com"

  - Utilisez le nom unique des services de domaine Active Directory de l’utilisateur. Par exemple :
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

Les applets de commande suivantes acceptent l’identité d’un utilisateur:

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))

  - [Get-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))

  - [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))

  - [New-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))

  - [Remove-CsExUmContact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))

  - [Remove-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))

  - [Set-CsExUmContact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))

  - [Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))

Notez que vous n’avez pas besoin de spécifier d’identité d’utilisateur lors de l’appel d’une des cmdlets **Get-CS** . Dans ce cas, les applets de passe retournent toutes les instances de l’élément spécifié. Par exemple, la commande suivante renvoie des informations sur tous les utilisateurs qui ont été activés pour Skype entreprise Online:

    Get-CsOnlineUser

Le paramètre Identity est requis uniquement si vous souhaitez renvoyer des informations pour un utilisateur spécifique:

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>Voir aussi


[Identités, étendues et clients dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

