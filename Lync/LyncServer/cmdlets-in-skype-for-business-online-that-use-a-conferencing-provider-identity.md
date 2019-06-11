---
title: Cmdlets dans Skype entreprise Online utilisant l’identité d’un fournisseur de conférence
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e36c04b2f5728ff624a280696bacf4eacb032967
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838093"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Cmdlets dans Skype entreprise Online utilisant l’identité d’un fournisseur de conférence

 


Pour renvoyer des informations sur tous les fournisseurs de services d’audioconférence pour lesquels votre organisation a contracté une conversation, vous pouvez simplement appeler la cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\)) sans paramètres:

    Get-CsAudioConferencingProvider

Si vous souhaitez limiter les données renvoyées à un seul fournisseur (dans cet exemple, les services audio du fournisseur contoso), puis utilisez le paramètre Identity:

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

Il n’y a qu’une applet de connexion Skype entreprise Online qui accepte un ID de fournisseur de services d’audioconférence:

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>Voir aussi


[Identités, étendues et clients dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

