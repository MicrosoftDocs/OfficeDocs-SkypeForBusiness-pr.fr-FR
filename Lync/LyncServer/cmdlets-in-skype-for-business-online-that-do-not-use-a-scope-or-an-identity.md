---
title: Applets de commande dans Skype entreprise Online qui n’utilisent pas d’étendue ni d’identité
description: Applets de commande dans Skype entreprise Online qui n’utilisent pas d’étendue ni d’identité.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7d893c4cf9203c8657dfbdfd7fb2bf46dbdfe4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545720"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>Applets de commande dans Skype entreprise Online qui n’utilisent pas d’étendue ni d’identité

 


Les applets de commande utilisées lors de la modification des listes autorisées et des listes bloquées (listes qui déterminent les organisations externes avec lesquelles vos utilisateurs sont autorisés à communiquer) n’utilisent ni une étendue ni une identité. En fait, la cmdlet **New-CsEdgeAllowAllKnownDomains** n’a aucun paramètre. Les applets de commande qui n’utilisent ni une étendue ni une identité sont les suivantes :

  - [New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))

  - [New-CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))

  - [New-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))

Notez que, avec la cmdlet **New-CsEdgeAllowList** et la cmdlet **New-CsEdgeDomainPattern** , vous devez inclure le paramètre domain. Par exemple :

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>Voir aussi


[Identités, étendues et locataires dans Skype entreprise Online](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Applets de commande Skype entreprise Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

