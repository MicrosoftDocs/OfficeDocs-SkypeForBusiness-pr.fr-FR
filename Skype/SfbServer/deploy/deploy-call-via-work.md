---
title: Déploiement d’un appel via le travail dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Résumé: Découvrez comment déployer un appel via le travail dans Skype entreprise Server pour tout ou partie de vos utilisateurs.'
ms.openlocfilehash: a2d4783f39ca19fd751295f4725f686d843f8d5b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286389"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Déploiement d’un appel via le travail dans Skype entreprise Server
 
**Résumé:** Découvrez comment déployer un appel via votre travail dans Skype entreprise Server pour tout ou partie de vos utilisateurs.
  
Suivez ces étapes pour déployer l’appel via le Bureau pour vos utilisateurs. Les considérations en matière de planification sont décrites dans la rubrique [planifier un appel via le travail dans Skype entreprise Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). Dans les versions précédentes du contrôle d’appel distant de Lync Server est une fonctionnalité qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype entreprise Server, cette fonction a été remplacée par un appel via le travail. 
  
## <a name="prerequisites-for-call-via-work"></a>Prérequis pour les appels via le Bureau

L’appel par le biais de l’utilisation utilise Unified Communications Web API (UCWA), qui est automatiquement installé sur tous les serveurs frontaux Skype entreprise Server. Pour permettre aux utilisateurs d’effectuer des appels par le biais de leur bureau, vous devez également disposer de la configuration requise suivante: 
  
- Un serveur de médiation doit être déployé par le biais d’un serveur frontal ou d’un rôle autonome. Vous devez également déployer une passerelle IP-PBX.
    
- Tous les utilisateurs qui seront activés pour les appels via le professionnel doivent disposer d’une numérotation directe vers l’intérieur du système téléphonique PBX. 
    
- Vous devez activer tous les appels via les utilisateurs professionnels pour voix entreprise. Lorsque vous procédez ainsi, vous devez configurer le numéro Skype entreprise pour chaque utilisateur sur le numéro de téléphone PBX correspondant au système PBX correspondant. 
    
- La **configuration automatique** de tous les utilisateurs qui utiliseront un appel via le Bureau doit être sélectionnée dans l’option de **connexion avancée** du client Skype entreprise. Cela permet au client de découvrir les URL UCWA. **Configuration automatique** est sélectionné par défaut.
    
- Pour chaque appel via l’utilisateur de votre entreprise, activez le transfert d’appel et la sonnerie simultanée. 
    
- Pour chaque appel par le biais de l’utilisateur travaillant, assurez-vous que les appels entrants et les conférences rendez-vous sont activés. Cela permet aux utilisateurs d’accéder à des conférences Skype entreprise et de les se déconnecter.
    
- Assurez-vous que la délégation, l’appel d’équipe et le groupe de réponse sont désactivés pour chaque appel via l’utilisateur de travail.
    
## <a name="deploy-call-via-work"></a>Déployer l’appel via le bureau

Une fois les conditions préalables remplies, procédez comme suit :
  
- Créez un numéro de téléphone global pour votre déploiement, que Skype entreprise affiche sur l’IDENTIFIant de l’appelant PBX des utilisateurs effectuant un appel par le biais d’appels professionnels. 
    
- Créer un ou plusieurs appels via une stratégie de bureau
    
- Assigner un appel via une stratégie de bureau à chaque utilisateur qui sera activé pour appel via le Bureau
    
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

    Par exemple, l’applet de commande suivante crée un appel via une stratégie de bureau appelée ContosoUser1CvWP, exige que l’utilisateur utilise un numéro de rappel d’administration et définit ce numéro de rappel sur 1-555-789-1234.
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Assigner un appel via une stratégie de bureau à un utilisateur

- Saisissez l’applet de commande suivant
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Par exemple, l’applet de commande suivante affecte l’appel via la stratégie de bureau «ContosoUser1CvWP» à l’utilisateur nommé **ContosoUser1**.
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Voir aussi

[Planifier un appel via le travail dans Skype entreprise Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

