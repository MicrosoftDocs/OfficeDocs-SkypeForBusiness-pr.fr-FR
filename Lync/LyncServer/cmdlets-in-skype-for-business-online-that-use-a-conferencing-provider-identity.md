---
title: Applets de commande dans Skype entreprise Online qui utilisent l’identité d’un fournisseur de services de conférence
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accaad94f5e29863ac948ea64d061d23b811105f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755126"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a>Applets de commande dans Skype entreprise Online qui utilisent l’identité d’un fournisseur de services de conférence

 


Pour renvoyer des informations sur tous les fournisseurs de services d’audioconférence avec lesquels votre organisation a contracté, vous pouvez simplement appeler la cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) sans aucun paramètre :

    Get-CsAudioConferencingProvider

Si vous souhaitez limiter les données renvoyées à un seul fournisseur (dans cet exemple, le fournisseur contoso audio services), utilisez le paramètre Identity :

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

Il n’existe qu’une seule cmdlet Skype entreprise Online qui accepte un ID de fournisseur de services d’audioconférence :

  - [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))

## <a name="see-also"></a>Voir aussi


[Identités, étendues et locataires dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

