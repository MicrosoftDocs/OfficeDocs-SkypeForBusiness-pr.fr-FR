---
title: Applets de commande dans Skype entreprise Online qui utilisent l’étendue globale et l’étendue de la balise
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8063334f2cea6fcca768754197bacbd30869461
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755074"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Applets de commande dans Skype entreprise Online qui utilisent l’étendue globale et l’étendue de la balise

 


Dans Skype entreprise Online, les stratégies peuvent être configurées au niveau de l’étendue *globale* ou de l’étendue de la *balise* (ou *étendue par utilisateur*). Lorsque vous utilisez les cmdlets **Get-CS** , il n’est pas nécessaire de spécifier une étendue ou une identité. Si vous appelez l’une de ces applets de commande sans aucun paramètre, tous les éléments pertinents seront retournés. Par exemple, cette commande renvoie des informations sur toutes les stratégies d’accès externe :

    Get-CsExternalAccessPolicy

Si vous souhaitez limiter les données renvoyées, vous devez inclure uniquement le paramètre Identity ou le paramètre Filter. Par exemple, pour renvoyer uniquement la stratégie globale, utilisez la commande suivante :

    Get-CsExternalAccessPolicy -Identity "global"

Pour renvoyer une stratégie par utilisateur dont l’identité est « RedmondAccessPolicy », utilisez la commande suivante :

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> Lorsque vous faites référence à une stratégie utilisateur, le <STRONG>préfixe</STRONG> de balise est facultatif. Cette syntaxe, qui inclut le préfixe, est également valide :<BR>Get-CsExternalAccessPolicy – Identity "tag : RedmondAccessPolicy"



Pour renvoyer toutes les stratégies à l’exception des stratégies globales (c’est-à-dire, toutes les stratégies par utilisateur), utilisez la commande suivante :

    Get-CsExternalAccessPolicy -Filter "tag:*"

Les applets de commande suivantes fonctionnent sur l’étendue globale et sur l’étendue par utilisateur (balise) :

  - [Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> Malgré le nom, les plans de numérotation sont des stratégies, de façon fonctionnelle. Le terme <EM>plan de numérotation</EM> est utilisé à la place, par exemple, de la stratégie de numérotation, afin de préserver la terminologie utilisée avec les versions précédentes de Lync Server.



## <a name="see-also"></a>Voir aussi


[Identités, étendues et locataires dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

