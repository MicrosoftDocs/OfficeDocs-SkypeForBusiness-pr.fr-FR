---
title: Modifier les stratégies de conférence dans Skype Entreprise Server
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Résumé : Découvrez comment modifier des stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 6bbba82c9785e074da492eb66cbdd943dc0cea35
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119423"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Modifier les stratégies de conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment modifier les stratégies de conférence dans Skype Entreprise Server.
  
Vous pouvez modifier les stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modifier les stratégies de conférence à l’aide du Panneau de contrôle Skype Entreprise Server

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Stratégie **de conférence.**
    
4. Dans la liste des stratégies de conférence, cliquez sur la stratégie de conférence souhaitée, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de conférence**, modifiez les paramètres de stratégie, à l’exception du nom de la stratégie qui ne peut pas être modifié.
    
6. Cliquez sur **Valider**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modifier les stratégies de conférence à l’aide de Skype Entreprise Server Management Shell

Pour modifier les stratégies de conférence, utilisez l’cmdlet **Set-CsConferencingPolicy.**
  
L’exemple suivant modifie une valeur de propriété de la stratégie de conférence SalesConferencingPolicy. La commande définit la valeur de la propriété AllowConferenceRecording sur False :
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Pour plus d’informations, notamment sur la syntaxe complète et la liste des paramètres, voir [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
