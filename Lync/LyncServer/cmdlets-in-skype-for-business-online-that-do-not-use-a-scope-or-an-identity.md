---
title: Cmdlets dans Skype entreprise Online qui n’utilisent pas d’étendue ou d’identité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7f6632640277a6a99626c18f458100f6a8cea0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838092"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Cmdlets dans Skype entreprise Online qui n’utilisent pas d’étendue ou d’identité

 


Les applets de passe utilisés lors de la modification des listes autorisées et des listes bloquées (listes qui déterminent les organisations externes avec lesquelles les utilisateurs sont autorisés à communiquer) n’utilisent pas d’étendue ou d’identité. En fait, l’applet **de nouvelle applet de CsEdgeAllowAllKnownDomains** n’a aucun paramètre. Les applets de applet qui n’utilisent pas d’étendue ou d’identité sont les suivantes:

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))

Notez que, avec l’applet **de nouvelle cmdlet New-CsEdgeAllowList** et la cmdlet **New-CsEdgeDomainPattern** , vous devez inclure le paramètre domain. Par exemple :

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>Voir aussi


[Identités, étendues et clients dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

