---
title: Activer les utilisateurs pour Voix Entreprise dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Résumé : Découvrez comment permettre aux utilisateurs de prendre et de recevoir des appels à l’aide de Voix Entreprise dans Skype Entreprise Server.'
ms.openlocfilehash: a910ecb8638b926be9d04234c6f429a97cbd28f2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387340"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>Activer les utilisateurs pour Voix Entreprise dans Skype Entreprise Server
 
**Résumé :** Découvrez comment permettre aux utilisateurs de prendre et de recevoir des appels à l’aide de Voix Entreprise dans Skype Entreprise Server.
  
Après avoir déployé Voix Entreprise ou appel via le travail, vous pouvez utiliser les procédures suivantes pour permettre à un utilisateur d’effectuer des appels à l’aide Voix Entreprise :
  
> [!NOTE]
> Des procédures suivantes, seule la première peut être effectuée à l’aide Skype Entreprise Server panneau de commande. Pour les autres procédures, vous pouvez utiliser uniquement Skype Entreprise Server Management Shell. 
  
- Activez le compte d’utilisateur pour Voix Entreprise.
    
- (Facultatif) Attribuez au compte d’utilisateur une stratégie de voix spécifique à l’utilisateur.
    
- (Facultatif) Attribuez au compte d’utilisateur un plan de numérotation spécifique à l’utilisateur.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>Pour activer un compte d’utilisateur pour Voix Entreprise

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.
    
4. Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.
    
5. Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour Voix Entreprise.
    
6. Dans le menu **Edition**, cliquez sur **Afficher les détails**.
    
7. Dans la page **Modifier Skype Entreprise Server utilisateur**, sous **Téléphonie**, cliquez **sur Voix Entreprise**.
    
8. Cliquez **sur URI de** ligne, puis tapez un numéro de téléphone unique et normal (par exemple, `tel:+14255550200`).
    
9. Cliquez sur **Valider**.
    
Pour terminer l’activation d’un utilisateur pour Voix Entreprise, assurez-vous qu’une stratégie de voix et un plan de numérotation lui sont affectés, qu’il soit global (affecté par défaut) ou spécifique à l’utilisateur. Par défaut, une stratégie de voix globale et un plan de numérotation sont attribués à tous les utilisateurs. Si une stratégie de voix ou un plan de numérotation existe au niveau du site sur lequel le compte d’utilisateur est homed, ces stratégies de site s’appliquent automatiquement à l’utilisateur. Pour appliquer une stratégie de voix ou un plan de numérotation par utilisateur à un utilisateur, vous devez exécuter les cmdlets **Grant-CsVoicePolicy** et **Grant-CsDialPlan** . Pour plus d’informations, voir les procédures suivantes dans cette rubrique.
## <a name="voice-policy-assignment"></a>Attribution de stratégie de voix

Les stratégies de voix au niveau global et au niveau du site sont automatiquement affectées à tous les comptes d’utilisateur activés pour Voix Entreprise. Vous pouvez également créer des stratégies de voix qui s’appliquent à des utilisateurs ou des groupes spécifiques. Ces stratégies utilisateur doivent être explicitement attribuées aux utilisateurs ou groupes. Si vous souhaitez utiliser la stratégie de voix globale ou de site pour tous les utilisateurs activés pour Voix Entreprise, vous pouvez ignorer cette section et passer à la section Affectation du [plan](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) de numérotation plus loin dans cette rubrique.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>Pour affecter une stratégie de voix spécifique à l’utilisateur

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Pour assigner une stratégie de voix utilisateur existante à un utilisateur, exécutez la commande suivante à l’invite :
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Par exemple :
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    Dans cet exemple, la stratégie de voix **VoicePolicyJapan** est attribuée à l’utilisateur dont le nom complet est Bob Kelly.
    
## <a name="dial-plan-assignment"></a>Affectation de plan de numérotation
<a name="BKMK_DialPlanAssignment"> </a>

Pour terminer la configuration des comptes d’utilisateurs des utilisateurs de Voix Entreprise ou de conférence rendez-vous, il convient de leur assigner un plan de numérotation. Les comptes d’utilisateurs utilisent automatiquement le plan de numérotation global ou, le cas présent, le plan de numérotation au niveau du site, lorsque vous n’affectez pas explicitement un plan de numérotation utilisateur existant. Si vous souhaitez utiliser le plan de numérotation global ou de site pour tous les utilisateurs activés pour Voix Entreprise, vous pouvez ignorer cette section.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>Pour affecter un plan de numérotation spécifique à l’utilisateur

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Pour assigner un plan de numérotation spécifique à un utilisateur, exécutez la commande suivante à l’invite :
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    Par exemple :
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    Dans cet exemple, le plan de numérotation utilisateur nommé **DialPlanJapan** est attribué à l’utilisateur nommé Bob Kelly.
    

