---
title: Déployer l’appel via le bureau dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Résumé : Découvrez comment déployer des appels via le bureau dans Skype pour Business Server pour tout ou partie de vos utilisateurs.'
ms.openlocfilehash: d0cee2cbf3a88514983efd77e2b1728b2df1e792
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227535"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Déployer l’appel via le bureau dans Skype pour Business Server
 
**Résumé :** Apprenez à déployer des appels via le bureau dans Skype pour Business Server pour tout ou partie de vos utilisateurs.
  
Utilisez ces étapes pour déployer un appel via le bureau pour vos utilisateurs. Considérations de planification décrits dans [Plan pour un appel via le bureau dans Skype pour Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). Dans les versions précédentes d’appel distant Lync Server contrôle est une fonctionnalité qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype pour Business Server, cette fonctionnalité a été remplacée par un appel via le bureau. 
  
## <a name="prerequisites-for-call-via-work"></a>Conditions requises pour l’appel via le bureau

Appel via le bureau utilise Unified Communications Web API (UCWA), qui est installé automatiquement sur tous les Skype pour les serveurs frontaux Business Server. Pour permettre aux utilisateurs d’appeler via le bureau, vous devez également les conditions préalables suivantes en place : 
  
- Vous devez disposer d’un serveur de médiation déployés, dans le cadre d’un serveur frontal ou d’un rôle autonome. Vous devez également déployer une passerelle IP-PBX.
    
- Tous les utilisateurs autorisés pour un appel via le bureau doivent avoir un Direct Inward Dialing (DID) sur le système téléphonique PBX. 
    
- Vous devez activer tous les utilisateurs d’appeler via le bureau pour Enterprise Voice. Lorsque vous effectuez cette opération, vous devez configurer le Skype pour numéro d’entreprise n’a pour chaque utilisateur au numéro DID correspondant pour le système téléphonique PBX correspondant. 
    
- Tous les utilisateurs qui utiliseront des appels via le bureau doivent avoir **La Configuration automatique** sélectionné dans l’option **Connexions avancées** dans leur Skype pour client d’entreprise. Cela permet au client découvrir les URL UCWA. **Configuration automatique** est sélectionné par défaut.
    
- Pour chaque utilisateur de l’appel via le bureau, activez le transfert d’appel et la sonnerie simultanée. 
    
- Pour chaque utilisateur de l’appel via le bureau, assurez-vous que l’option conférence rendez-vous conférence entrants et sortants sont activés. Cela permet à ces utilisateurs de se connecter et se déconnecter de Skype pour des conférences.
    
- Assurez-vous que la délégation, l’appel d’équipe et groupe de réponse sont désactivés pour chaque utilisateur de l’appel via le bureau.
    
## <a name="deploy-call-via-work"></a>Déployer l’appel via le bureau

Une fois les conditions préalables remplies, procédez comme suit :
  
- Créer un numéro de téléphone globale pour votre déploiement qui Skype pour les entreprises affiche l’ID d’appelant PBX d’utilisateurs qui utilisent des appels de l’appel via le bureau. 
    
- Créer une ou plusieurs stratégies d’appel via le bureau
    
- Affecter une stratégie de l’appel via le Bureau à chaque utilisateur qui est activé pour les appels vers le bureau
    
### <a name="create-the-call-via-work-global-phone-number"></a>Créez le numéro de téléphone global d’appel via le bureau

- Saisissez l’applet de commande suivant
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Par exemple, l’applet de commande suivant définit le numéro de téléphone global sur 1-555-123-4567.
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Créez une stratégie d’appel via le bureau

- Saisissez l’applet de commande suivant
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Par exemple, l’applet de commande suivante crée une stratégie d’appel via le bureau appelée ContosoUser1CvWP, oblige l’utilisateur à utiliser un numéro de rappel d’administration et définit ce numéro de rappel 1-555-789-1234.
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Affecter une stratégie de l’appel via le Bureau à un utilisateur

- Saisissez l’applet de commande suivant
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Par exemple, l’applet de commande suivante affecte la stratégie d’appel via le bureau « ContosoUser1CvWP » à l’utilisateur nommé **ContosoUser1**.
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Voir aussi

[Plan pour un appel via le bureau dans Skype pour Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

