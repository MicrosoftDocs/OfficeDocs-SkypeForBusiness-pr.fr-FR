---
title: Affecter des stratégies de conférence dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Résumé : Découvrez comment attribuer des stratégies de conférence de Skype pour Business Server.'
ms.openlocfilehash: 90a291c707be70d3d30d868013ec38b33f684050
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20969710"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Affecter des stratégies de conférence dans Skype pour Business Server
 
**Résumé :** Découvrez comment attribuer des stratégies de conférence de Skype pour Business Server.
  
Vous pouvez affecter des stratégies de conférence pour les utilisateurs à l’aide de Skype pour Business Server Management Shell et l’applet de commande **Grant-CsConferencingPolicy** .
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Affecter des stratégies de conférence à l’aide de Skype pour Business Server Management Shell

Dans l’exemple qui suit, la stratégie SalesConferencingPolicy est affectée à l’utilisateur dont l’identité est « Ken Myer » :
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Dans l’exemple ci-dessous, la stratégie de conférence FinanceConferencingPolicy est affectée à tous les utilisateurs disposant de comptes dans l’unité d’organisation Finance. Pour affecter la même stratégie à tous les utilisateurs d’une unité d’organisation donnée, l’applet de commande Get-CsUser est utilisée pour extraire tous les comptes de cette unité. Une fois tous les comptes extraits, ces informations sont ensuite redirigées vers l’applet de commande Grant-CsConferencingPolicy, qui affecte la stratégie FinanceConferencingPolicy à chaque utilisateur de la collection.
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Pour plus d’informations, y compris la syntaxe complète et une liste des paramètres, voir [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

