---
title: Activer le parcage d’appel pour les utilisateurs de Skype pour les entreprises
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Activer les utilisateurs pour la mise en garde d’appels dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 44e72cab776b08cbd0290bb15010d36d370d86b3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968222"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Activer le parcage d’appel pour les utilisateurs de Skype pour les entreprises
 
Activer les utilisateurs pour la mise en garde d’appels dans Skype pour Business Server Enterprise Voice.
  
Par défaut, la mise en garde d’appels est désactivé pour tous les utilisateurs. Les utilisateurs ne peuvent pas mettre en garde d’appels ou récupérer les appels mis en garde tant qu’ils sont activés pour le parcage d’appel dans la stratégie de voix.
  
Vous pouvez activer la mise en garde d’appels au niveau global ou au niveau de l’étendue site ou utilisateur. L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale. Si vous avez plusieurs stratégies de voix, passez en revue toutes les stratégies pour activer le parcage d’appel, pas seulement la stratégie globale.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Pour utiliser Skype pour Business Server Control Panel pour activer le parcage d’appel pour les utilisateurs

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Cliquez sur l’onglet **Stratégie de la voix**.
    
5. Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.
    
6. Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.
    
7. Cliquez sur **OK** pour enregistrer la stratégie de voix.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Pour utiliser les applets de commande pour activer le parcage d’appel pour les utilisateurs

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Exécutez :
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Par exemple, pour activer la mise en garde d’appels pour la stratégie de voix globale par défaut :
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Voir aussi



[Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Skype pour les entreprises](voice-policy-and-pstn-usage-records.md)

