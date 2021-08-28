---
title: Affecter des stratégies de conférence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Résumé : Découvrez comment affecter des stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 3ae21518cf53aad48d4fc9b6963d0e5402007db9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635278"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Affecter des stratégies de conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment affecter des stratégies de conférence dans Skype Entreprise Server.
  
Vous pouvez affecter des stratégies de conférence aux utilisateurs à l’aide de Skype Entreprise Server Management Shell et de l’cmdlet **Grant-CsConferencingPolicy.**
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Affecter des stratégies de conférence à l’aide Skype Entreprise Server Management Shell

Dans l’exemple suivant, la stratégie SalesConferencingPolicy est affectée à l’utilisateur dont l’identité est « Ken Myer » :
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Dans l’exemple suivant, la stratégie de conférence FinanceConferencingPolicy est affectée à tous les utilisateurs qui ont des comptes dans l’unité d’organisation Finance. Pour affecter la même stratégie à tous les utilisateurs d’une unité d’organisation donnée, l’applet de commande Get-CsUser est utilisée pour récupérer tous les comptes de cette unité. Une fois les comptes d’utilisateur récupérés, ces informations sont ensuite canales vers l’cmdlet Grant-CsConferencingPolicy qui affecte la stratégie FinanceConferencingPolicy à chaque utilisateur de la collection :
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Pour plus d’informations, notamment sur la syntaxe complète et la liste des paramètres, voir [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
