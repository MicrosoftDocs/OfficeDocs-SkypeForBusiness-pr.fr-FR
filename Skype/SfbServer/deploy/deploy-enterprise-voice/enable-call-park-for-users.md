---
title: Activer le parc d’appels pour les utilisateurs de Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Autorisez les utilisateurs à utiliser le parc d’appels dans Skype entreprise Server Voice.
ms.openlocfilehash: 326b1156ea3b300301b46324d90dbc7dde088b3d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291587"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Activer le parc d’appels pour les utilisateurs de Skype entreprise
 
Autorisez les utilisateurs à utiliser le parc d’appels dans Skype entreprise Server Voice.
  
Par défaut, le parc d’appels est désactivé pour tous les utilisateurs. Les utilisateurs ne peuvent pas parcer les appels ou récupérer les appels en stationnement tant qu’ils sont activés pour le parc d’appels dans la politique vocale.
  
Vous pouvez activer le parc d’appels au niveau de l’étendue globale, ou à l’étendue du site ou l’étendue de l’utilisateur. L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale. Si vous avez plusieurs stratégies vocales, passez en revue toutes les stratégies pour activer le parc d’appels, pas seulement la politique globale.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Pour utiliser le panneau de configuration Skype entreprise Server pour activer le parc d’appels pour les utilisateurs

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Cliquez sur l’onglet **Stratégie de la voix**.
    
5. Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.
    
6. Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.
    
7. Cliquez sur **OK** pour enregistrer la stratégie de voix.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Utiliser des cmdlets pour activer le parc d’appels pour les utilisateurs

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Exécutez :
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Par exemple, pour activer le parc d’appels pour la stratégie vocale globale par défaut:
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Voir aussi



[Création ou modification d’une stratégie de voix et configuration des enregistrements d’utilisation RTC dans Skype entreprise](voice-policy-and-pstn-usage-records.md)

