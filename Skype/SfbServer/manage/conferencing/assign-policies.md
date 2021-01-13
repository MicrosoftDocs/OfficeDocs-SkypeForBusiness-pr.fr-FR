---
title: Attribuer des stratégies de conférence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Résumé : Découvrez comment affecter des stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: d13710d2cc4f6edf1cee16cbc9aa77799ceec8a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806474"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Attribuer des stratégies de conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment affecter des stratégies de conférence dans Skype Entreprise Server.
  
Vous pouvez affecter des stratégies de conférence à des utilisateurs à l’aide de Skype Entreprise Server Management Shell et de **l';grant-CsConferencingPolicy.**
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Affecter des stratégies de conférence à l’aide de Skype Entreprise Server Management Shell

Dans l’exemple suivant, la stratégie SalesConferencingPolicy est affectée à l’utilisateur dont l’identité est « Ken Myer » :
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Dans l’exemple suivant, la stratégie de conférence FinanceConferencingPolicy est affectée à tous les utilisateurs qui ont des comptes dans l’unité d’organisation Finance. Pour affecter la même stratégie à tous les utilisateurs d’une unité d’organisation donnée, l’applet de commande Get-CsUser est utilisée pour récupérer tous les comptes de cette unité. Une fois les comptes d’utilisateur récupérés, ces informations sont ensuite canales vers l’cmdlet Grant-CsConferencingPolicy qui affecte la stratégie FinanceConferencingPolicy à chaque utilisateur de la collection :
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Pour plus d’informations, notamment sur la syntaxe complète et la liste des paramètres, voir [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

