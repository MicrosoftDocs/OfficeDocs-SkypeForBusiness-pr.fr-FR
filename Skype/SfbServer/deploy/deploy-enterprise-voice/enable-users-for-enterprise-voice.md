---
title: Activer les utilisateurs pour Enterprise Voice sur Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Résumé : Découvrez comment permettre aux utilisateurs d’émettre et recevoir des appels à l’aide d’Enterprise Voice dans Skype pour Business Server.'
ms.openlocfilehash: b02155f424e8b3f29881caf8c4a29db6f76cb807
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882968"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Activer les utilisateurs pour Enterprise Voice sur Skype pour Business Server
 
**Résumé :** Découvrez comment permettre aux utilisateurs d’émettre et recevoir des appels à l’aide d’Enterprise Voice dans Skype pour Business Server.
  
Après avoir déployé Enterprise Voice ou appel via le bureau, vous pouvez utiliser les procédures suivantes pour activer un utilisateur effectuer des appels à l’aide de Enterprise Voice :
  
> [!NOTE]
> Des procédures suivantes, seul le premier peut être effectué à l’aide de Skype pour le panneau de configuration serveur Business. Pour le reste des procédures, vous pouvez utiliser uniquement Skype pour Business Server Management Shell. 
  
- Activer le compte d’utilisateur pour voix entreprise.
    
- (Facultatif) Affectez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.
    
- (Facultatif) Affectez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Pour activer un compte d’utilisateur pour voix entreprise

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.
    
2. Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour Enterprise Voice.
    
6. Dans le menu **Edition**, cliquez sur **Afficher les détails**.
    
7. Dans la page **Modifier les Skype pour Business Server utilisateur** , sous **téléphonie**, cliquez sur **Enterprise Voice**.
    
8. Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200).
    
9. Cliquez sur **Valider**.
    
Pour terminer d’activer un utilisateur pour Enterprise Voice, n’oubliez pas que l’utilisateur reçoit une stratégie de voix et un plan de numérotation, nature globale (affectée par défaut) ou spécifiques à l’utilisateur. Par défaut, tous les utilisateurs sont affectés à une stratégie de voix globale et plan de numérotation. S’il existe une stratégie de voix ou un plan de numérotation au niveau du site sur lequel un compte d’utilisateur est hébergé, cette stratégie de site s’applique automatiquement à l’utilisateur. Pour appliquer une stratégie de voix ou un plan de numérotation à un utilisateur, vous devez exécuter les applets de commande **Grant-CsVoicePolicy** et **Grant-CsDialPlan**. Pour plus d’informations, reportez-vous aux procédures suivantes de cette rubrique.
## <a name="voice-policy-assignment"></a>Affectation d’une stratégie de voix

Stratégies de voix globale et au niveau du site sont automatiquement affectés à tous les comptes d’utilisateurs activés pour Enterprise Voice. Vous pouvez également créer des stratégies de voix qui s’appliquent à des utilisateurs ou à des groupes spécifiques. Ces stratégies utilisateur doivent être affectées explicitement à des utilisateurs ou à des groupes. Si vous souhaitez utiliser le modèle global ou site de la stratégie de voix pour tous les utilisateurs activés pour Enterprise Voice, vous pouvez ignorer cette section et passez à la section [Affectation de Plan de numérotation](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) plus loin dans cette rubrique.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Pour affecter une stratégie de voix spécifique à l’utilisateur

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
3. Pour affecter une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Par exemple :
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    Dans cet exemple, l’utilisateur dont le nom complet Bob Kelly est affectée à la stratégie de voix portant le nom **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Affectation d’un plan de numérotation
<a name="BKMK_DialPlanAssignment"> </a>

Pour terminer la configuration de compte d’utilisateur pour les utilisateurs d’Enterprise Voice ou les utilisateurs de conférence rendez-vous, l’utilisateur doit être affecté à un plan de numérotation. Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, le cas échéant, le plan de numérotation au niveau du site si vous n’affectez pas explicitement un plan de numérotation utilisateur existant. Si vous souhaitez utiliser le modèle global ou site de plan de numérotation pour tous les utilisateurs activés pour Enterprise Voice, vous pouvez ignorer cette section.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Affectation d’un plan de numérotation propre à un utilisateur

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.
    
3. Pour affecter un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Exemple :
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    Dans cet exemple, l’utilisateur dont le nom complet Bob Kelly est affecté le plan de numérotation utilisateur **intitulé dialplanjapan**.
    

