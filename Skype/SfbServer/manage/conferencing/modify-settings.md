---
title: Modifier les paramètres de configuration de réunion dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Résumé : Découvrez comment modifier les paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: 2f57f0a7d6bd445e84cf0d9feb43997613d35794
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848557"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modifier les paramètres de configuration de réunion dans Skype Entreprise Server
 
**Résumé :** Découvrez comment modifier les paramètres de configuration de réunion dans Skype Entreprise Server.
  
Vous pouvez modifier les paramètres de configuration de réunion à l’Skype Entreprise Server du Panneau de configuration ou Skype Entreprise Server Management Shell.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modifier les paramètres de configuration de réunion à l’aide Skype Entreprise Server panneau de configuration

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur **Configuration de la réunion.**
    
4. Dans la liste des configurations de réunion, cliquez sur la configuration à modifier, cliquez sur **Modifier,** puis cliquez sur Afficher **les détails.**
    
5. Dans **Modifier la configuration de la réunion**, modifiez les paramètres de configuration, à l’exception du nom de configuration qui ne peut pas être modifié.
    
6. Cliquez sur **Valider**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modifier les paramètres de configuration de réunion à l’aide Skype Entreprise Server Management Shell

Pour modifier les paramètres de configuration de réunion, utilisez l’cmdlet **Set-CsMeetingConfiguration.**
  
La commande présentée dans l’exemple suivant modifie les paramètres de configuration de réunion affectés au site Redmond (-Identity site:Redmond). Dans ce cas, la valeur de la propriété DesignateAsPresenter est définie sur Tout le monde :
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Pour plus d’informations, y compris une liste complète des paramètres, voir [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
