---
title: Modifier les paramètres de configuration de réunion dans Skype Entreprise Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Résumé : Découvrez comment modifier les paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: 2f0d1220312ac810d26fdd4691492133e54db9b6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119413"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modifier les paramètres de configuration de réunion dans Skype Entreprise Server
 
**Résumé :** Découvrez comment modifier les paramètres de configuration de réunion dans Skype Entreprise Server.
  
Vous pouvez modifier les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modifier les paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Configuration de **la réunion.**
    
4. Dans la liste des configurations de réunion, cliquez sur la configuration à modifier, cliquez sur **Modifier,** puis cliquez sur Afficher **les détails.**
    
5. Dans **Modifier la configuration de la réunion**, modifiez les paramètres de configuration, à l’exception du nom de configuration qui ne peut pas être modifié.
    
6. Cliquez sur **Valider**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modifier les paramètres de configuration de réunion à l’aide de Skype Entreprise Server Management Shell

Pour modifier les paramètres de configuration de réunion, utilisez l’cmdlet **Set-CsMeetingConfiguration.**
  
La commande présentée dans l’exemple suivant modifie les paramètres de configuration de réunion affectés au site Redmond (-Identity site:Redmond). Dans ce cas, la valeur de la propriété DesignateAsPresenter est définie sur Tout le monde :
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Pour plus d’informations, y compris une liste complète des paramètres, voir [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
