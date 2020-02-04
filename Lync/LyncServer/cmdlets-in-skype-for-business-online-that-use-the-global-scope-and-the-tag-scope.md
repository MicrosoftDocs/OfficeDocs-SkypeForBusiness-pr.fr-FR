---
title: Cmdlets dans Skype entreprise Online utilisant l’étendue globale et l’étendue des indicateurs
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 04eb5f71a0092452eb8b24fa9acf53d46fb3bcd5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728094"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a>Cmdlets dans Skype entreprise Online utilisant l’étendue globale et l’étendue des indicateurs

 


Dans Skype entreprise Online, les stratégies peuvent être configurées au niveau de l’étendue *globale* ou au niveau de l' *étendue des balises* (ou d’une *étendue par utilisateur*). Lorsque vous utilisez les applets **de cmdlet Get-CS** , vous n’avez pas à spécifier une étendue ou une identité. Si vous appelez l’une de ces applets de lignes sans paramètre, tous les éléments appropriés seront renvoyés. Par exemple, cette commande renvoie des informations sur toutes les stratégies d’accès externe :

    Get-CsExternalAccessPolicy

Vous devez inclure uniquement le paramètre Identity ou Filter si vous souhaitez limiter les données renvoyées. Par exemple, pour renvoyer uniquement la stratégie globale, utilisez la commande suivante :

    Get-CsExternalAccessPolicy -Identity "global"

Pour renvoyer une stratégie par utilisateur ayant l’identité « RedmondAccessPolicy », utilisez la commande suivante :

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> Lorsque vous faites référence à une stratégie par utilisateur, le <STRONG>préfixe</STRONG> de balise est facultatif. Cette syntaxe, qui inclut le préfixe, est également valide :<BR>Get-CsExternalAccessPolicy-Identity "tag : RedmondAccessPolicy"



Pour renvoyer toutes les stratégies, à l’exception des stratégies globales (c’est-à-dire toutes les stratégies par utilisateur), utilisez la commande suivante :

    Get-CsExternalAccessPolicy -Filter "tag:*"

Les applets de commande suivantes fonctionnent à la fois sur l’étendue globale et sur l’étendue par utilisateur (balise) :

  - [Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))

  - [Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))

  - [Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))

  - [Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))


> [!NOTE]  
> Malgré le nom, les plans de numérotation sont des politiques qui s’exécutent de façon fonctionnelle. Le <EM>plan de numérotation</EM> est utilisé à la place (par exemple, la stratégie de numérotation) pour conserver la terminologie utilisée avec les versions précédentes de Lync Server.



## <a name="see-also"></a>Voir aussi


[Identités, étendues et clients dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

