---
title: Activer les utilisateurs pour voix entreprise dans Skype entreprise Server
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
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Résumé: Découvrez comment permettre aux utilisateurs d’émettre et de recevoir des appels à l’aide d’Enterprise Voice dans Skype entreprise Server.'
ms.openlocfilehash: 8a94fe28cc492cdeac5eee476d6886fc8674ae13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303297"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Activer les utilisateurs pour voix entreprise dans Skype entreprise Server
 
**Résumé:** Découvrez comment permettre aux utilisateurs d’émettre et de recevoir des appels à l’aide d’Enterprise Voice dans Skype entreprise Server.
  
Après avoir déployé une voix d’entreprise ou un appel par le biais de votre entreprise, vous pouvez utiliser les procédures suivantes pour permettre à un utilisateur d’effectuer des appels à l’aide de la voix entreprise:
  
> [!NOTE]
> Parmi les procédures ci-dessous, seules les premières peuvent être effectuées à l’aide du panneau de configuration Skype entreprise Server. Pour les procédures restantes, vous pouvez uniquement utiliser Skype entreprise Server Management Shell. 
  
- Activez le compte d’utilisateur voix entreprise voix.
    
- (Facultatif) Affectez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.
    
- (Facultatif) Affectez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Pour activer un compte d’utilisateur pour voix entreprise

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.
    
2. Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.
    
5. Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.
    
6. Dans le menu **Edition**, cliquez sur **Afficher les détails**.
    
7. Dans la page **modifier l’utilisateur de Skype entreprise Server** , sous **téléphonie**, cliquez sur **voix entreprise**.
    
8. Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200).
    
9. Cliquez sur **Valider**.
    
Pour terminer l’activation d’un utilisateur pour voix entreprise, assurez-vous que l’utilisateur dispose d’une stratégie vocale et d’un plan de numérotation, qu’il s’agisse de global (attribué par défaut) ou d’utilisateur. Par défaut, tous les utilisateurs se voient attribuer une stratégie vocale globale et un plan de numérotation. S’il existe une stratégie de voix ou un plan de numérotation au niveau du site sur lequel un compte d’utilisateur est hébergé, cette stratégie de site s’applique automatiquement à l’utilisateur. Pour appliquer une stratégie de voix ou un plan de numérotation à un utilisateur, vous devez exécuter les applets de commande **Grant-CsVoicePolicy** et **Grant-CsDialPlan**. Pour plus d’informations, reportez-vous aux procédures suivantes de cette rubrique.
## <a name="voice-policy-assignment"></a>Affectation d’une stratégie de voix

Les stratégies de voix globale et de niveau site sont automatiquement affectées à tous les comptes d’utilisateurs activés pour Enterprise Voice. Vous pouvez également créer des stratégies de voix qui s’appliquent à des utilisateurs ou à des groupes spécifiques. Ces stratégies utilisateur doivent être affectées explicitement à des utilisateurs ou à des groupes. Si vous souhaitez utiliser la politique globale ou vocale pour tous les utilisateurs qui sont activés pour voix entreprise, vous pouvez ignorer cette section et poursuivre la section [affectation de plan](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) de numérotation plus loin dans cette rubrique.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Pour affecter une stratégie de voix spécifique à l’utilisateur

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Pour affecter une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Par exemple :
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    Dans cet exemple, l’utilisateur portant le nom d’affichage Bob Kelly reçoit la politique vocale portant le nom **VoicePolicyJapan**.
    
## <a name="dial-plan-assignment"></a>Affectation d’un plan de numérotation
<a name="BKMK_DialPlanAssignment"> </a>

Pour achever la configuration de compte d’utilisateur pour les utilisateurs d’Enterprise Voice ou les utilisateurs de conférences rendez-vous, l’utilisateur doit être affecté d’un plan de numérotation. Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, le cas échéant, le plan de numérotation au niveau du site si vous n’affectez pas explicitement un plan de numérotation utilisateur existant. Si vous souhaitez utiliser le plan de numérotation global ou de numérotation de site pour tous les utilisateurs qui sont activés pour voix entreprise, vous pouvez ignorer cette section.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Affectation d’un plan de numérotation propre à un utilisateur

1. À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Pour affecter un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Exemple :
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    Dans cet exemple, l’utilisateur portant le nom d’affichage Bob Kelly reçoit le plan de numérotation de l’utilisateur portant le nom **DialPlanJapan**.
    

