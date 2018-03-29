---
title: Activation des utilisateurs pour Voix Entreprise dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Résumé : Apprenez à permettre aux utilisateurs d’effectuer et de recevoir des appels à l’aide de Voix Entreprise dans Skype pour Business Server 2015.'
ms.openlocfilehash: d187723b347121400bfbce00d238851f2d0651a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server-2015"></a>Activation des utilisateurs pour Voix Entreprise dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment permettre aux utilisateurs d’effectuer et de recevoir des appels à l’aide de Voix Entreprise dans Skype pour Business Server 2015.
  
Après le déploiement de Voix Entreprise ou l’appeler Via le travail, vous pouvez utiliser les procédures suivantes pour activer un utilisateur effectuer des appels à l’aide de Voix Entreprise :
  
> [!NOTE]
> Des procédures suivantes, seule la première peut être effectuée à l’aide de Skype pour le panneau de configuration de Business Server. Pour les autres procédures, vous pouvez utiliser Skype uniquement pour Business Server Management Shell. 
  
- Activer le compte d’utilisateur pour les Voix Entreprise.
    
- (Facultatif) Affectez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.
    
- (Facultatif) Affectez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Pour activer un compte d’utilisateur de Voix Entreprise

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.
    
2. Ouvrez Skype pour le panneau de configuration de Business Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour les Voix Entreprise.
    
6. Dans le menu **Edition**, cliquez sur **Afficher les détails**.
    
7. Dans la page **Modifier les Skype pour l’utilisateur de serveur d’entreprise** , **téléphonie**, cliquez sur **Voix Entreprise**.
    
8. Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200).
    
9. Cliquez sur **Valider**.
    
Pour terminer l’activation d’un utilisateur de Voix Entreprise, assurez-vous que l’utilisateur reçoit une stratégie voice et un plan de numérotation, si global (affectée par défaut) ou spécifiques à l’utilisateur. Par défaut, tous les utilisateurs sont affectés à une stratégie voice global et plan de numérotation. S’il existe une stratégie de voix ou un plan de numérotation au niveau du site sur lequel un compte d’utilisateur est hébergé, cette stratégie de site s’applique automatiquement à l’utilisateur. Pour appliquer une stratégie de voix par utilisateur ou numérotation de plan à un utilisateur, vous devez exécuter les applets de commande **Grant-CsVoicePolicy** et **CsDialPlan de la subvention** . Pour plus d’informations, reportez-vous aux procédures suivantes de cette rubrique.
## <a name="voice-policy-assignment"></a>Affectation d’une stratégie de voix

Stratégies voice global et au niveau du site sont automatiquement affectés à tous les comptes d’utilisateurs qui sont activés pour les Voix Entreprise. Vous pouvez également créer des stratégies de voix qui s’appliquent à des utilisateurs ou à des groupes spécifiques. Ces stratégies utilisateur doivent être affectées explicitement à des utilisateurs ou à des groupes. Si vous souhaitez utiliser le global ou site stratégie voice pour tous les utilisateurs qui sont activés pour les Voix Entreprise, vous pouvez ignorer cette section et passez à la section [Affectation de Plan d’accès](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) plus loin dans cette rubrique.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Pour affecter une stratégie de voix spécifique à l’utilisateur

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Pour affecter une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Exemple :
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    Dans cet exemple, la stratégie voice avec le nom **VoicePolicyJapan**est attribuée à l’utilisateur avec le nom d’affichage Bob Kelly.
    
## <a name="dial-plan-assignment"></a>Affectation d’un plan de numérotation
<a name="BKMK_DialPlanAssignment"> </a>

Pour terminer la configuration de compte d’utilisateur pour les utilisateurs de Voix Entreprise ou utilisateurs de conférence à distance, l’utilisateur doit être affecté à un plan de numérotation. Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, le cas échéant, le plan de numérotation au niveau du site si vous n’affectez pas explicitement un plan de numérotation utilisateur existant. Si vous souhaitez utiliser le global ou site de plan de numérotation pour tous les utilisateurs qui sont activés pour les Voix Entreprise, vous pouvez ignorer cette section.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Affectation d’un plan de numérotation propre à un utilisateur

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Pour affecter un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Exemple :
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    Dans cet exemple, l’utilisateur avec le nom d’affichage Bob Kelly reçoit le plan de numérotation utilisateur avec le nom **DialPlanJapan**.
    

