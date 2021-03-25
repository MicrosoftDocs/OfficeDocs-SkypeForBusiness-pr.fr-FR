---
title: Activer ou désactiver la conférence téléphonique dans Skype Entreprise Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Résumé : Découvrez comment utiliser le Panneau de contrôle ou Management Shell pour activer ou désactiver la conférence téléphonique dans Skype Entreprise Server.'
ms.openlocfilehash: ade7753f480856d68535daadda40eac6296a5d6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119463"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Activer ou désactiver la conférence téléphonique dans Skype Entreprise Server
 
**Résumé :** Découvrez comment utiliser le Panneau de contrôle ou Management Shell pour activer ou désactiver la conférence téléphonique dans Skype Entreprise Server.
  
Vous pouvez activer la conférence téléphonique à l’aide du Panneau de contrôle Skype Entreprise Server ou de Skype Entreprise Server Management Shell.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Activer ou désactiver la conférence téléphonique à l’aide du Panneau de contrôle Skype Entreprise Server

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez le Panneau de contrôle Skype Entreprise Server.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Stratégie **de conférence.**
    
4. Dans la liste des stratégies de conférence, sélectionnez celle pour laquelle vous voulez activer la conférence rendez-vous, cliquez sur **Modifier**, puis sur **Afficher les détails**. 
    
5. Pour autoriser les utilisateurs à rejoindre une réunion en composant un numéro d’accès, activez la case à cocher **Activer la conférence rendez-vous PSTN**. Par défaut, les utilisateurs peuvent accéder aux réunions par le biais du réseau téléphonique commuté (PSTN).
    
6. Cliquez sur **Valider**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Activer ou désactiver la conférence téléphonique à l’aide de Skype Entreprise Server Management Shell

Pour activer ou désactiver la conférence téléphonique, utilisez l’cmdlet **Set-CsConferencingPolicy** avec le paramètre EnableDialInConferencing comme suit :
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Pour plus d’informations, [voir Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
