---
title: Activer le parc d’appel pour les utilisateurs Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Activez les utilisateurs pour le parc Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 262821cfef675c3af631cacd38f0cca4f2195fe7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775784"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Activer le parc d’appel pour les utilisateurs Skype Entreprise
 
Activez les utilisateurs pour le parc Skype Entreprise Server Voix Entreprise.
  
Par défaut, le parc d’appel est désactivé pour tous les utilisateurs. Les utilisateurs ne peuvent pas parer des appels ou récupérer des appels par parcés tant qu’ils n’ont pas été activés pour le parcier d’appel dans la stratégie de voix.
  
Vous pouvez activer le parcer d’appel au niveau de l’étendue globale, du site ou de l’utilisateur. L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale. Si vous avez plusieurs stratégies de voix, examinez toutes les stratégies pour activer le parcier d’appel, et pas seulement la stratégie globale.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Pour utiliser le Panneau de Skype Entreprise Server pour activer le parcier d’appel pour les utilisateurs

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Cliquez sur l’onglet **Stratégie de la voix**.
    
5. Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.
    
6. Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.
    
7. Cliquez sur **OK** pour enregistrer la stratégie de voix.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Pour utiliser des cmdlets pour activer le parcier d’appel pour les utilisateurs

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.
    
2. Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
3. Exécutez :  
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Par exemple, pour activer le parc d’appel pour la stratégie de voix globale par défaut :
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Voir aussi



[Créer ou modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Skype Entreprise](voice-policy-and-pstn-usage-records.md)

