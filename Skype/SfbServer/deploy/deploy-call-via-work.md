---
title: Déployer l’appel via le travail dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Résumé : Découvrez comment déployer l’appel via le travail dans Skype Entreprise Server pour tout ou partie de vos utilisateurs.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825004"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Déployer l’appel via le travail dans Skype Entreprise Server
 
**Résumé :** Découvrez comment déployer appel via le travail dans Skype Entreprise Server pour tout ou partie de vos utilisateurs.
  
Utilisez ces étapes pour déployer Appel via le travail pour vos utilisateurs. Les considérations de planification sont abordées dans [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). Dans les versions précédentes de Lync Server, le contrôle d’appel distant était une fonctionnalité qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype Entreprise Server, cette fonctionnalité a été remplacée par Appel via le travail. 
  
## <a name="prerequisites-for-call-via-work"></a>Conditions préalables pour l’appel via le travail

L’appel via le travail utilise l’API web de communications unifiées (UCWA), qui est automatiquement installée sur tous les serveurs frontux Skype Entreprise Server. Pour activer les utilisateurs pour l’appel via le travail, vous devez également avoir les conditions préalables suivantes en place : 
  
- Vous devez avoir déployé un serveur de médiation, soit dans le cadre d’un serveur frontal, soit en tant que rôle autonome. Vous devez également déployer une passerelle IP-PBX.
    
- Tous les utilisateurs qui seront activés pour l’appel via le travail doivent avoir un SDN (Direct Inward Dialing) sur le système téléphonique PBX. 
    
- Vous devez activer tous les utilisateurs de l’appel via le Voix Entreprise. Lorsque vous faites cela, vous devez configurer le numéro DID de Skype Entreprise pour chaque utilisateur sur le numéro DID correspondant pour le système téléphonique PBX correspondant. 
    
- La **configuration** automatique doit être sélectionnée dans l’option Connexions avancées de leur client Skype Entreprise pour tous les **utilisateurs** qui utiliseront l’appel via le travail. Cela permet au client de découvrir les URL UCWA. **La sélection automatique** est la sélection par défaut.
    
- Pour chaque utilisateur Appel via le travail, activez le forwarding d’appel et la sonnerie simultanée. 
    
- Pour chaque utilisateur Appel via le travail, assurez-vous que les appels sortants et de conférences sont activés. Cela permet à ces utilisateurs d’entrer et de sortir des conférences Skype Entreprise.
    
- Assurez-vous que la délégation, l’appel d’équipe et le groupe Response Group sont désactivés pour chaque utilisateur Appel via le travail.
    
## <a name="deploy-call-via-work"></a>Déployer l’appel via le bureau

Une fois les conditions préalables en place, faites les étapes suivantes :
  
- Créez un numéro de téléphone global pour votre déploiement, que Skype Entreprise affiche sur l’ID d’appelant PBX des utilisateurs qui effectuent des appels via le réseau téléphonique. 
    
- Créer une ou plusieurs stratégies d’appel via le travail
    
- Affecter une stratégie Appel via le travail à chaque utilisateur qui sera activé pour l’appel via le travail
    
### <a name="create-the-call-via-work-global-phone-number"></a>Créer le numéro de téléphone global Appel via le travail

- Tapez l’cmdlet suivante
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Par exemple, l’cmdlet suivante définit le numéro de téléphone global sur 1-555-123-4567.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Créer une stratégie Appel via le travail

- Tapez l’cmdlet suivante
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Par exemple, l’cmdlet suivante crée une stratégie Appel via le bureau appelée ContosoUser1CvWP, oblige l’utilisateur à utiliser un numéro de rappel d’administrateur et définit ce numéro de rappel sur 1-555-789-1234.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Affecter une stratégie Appel via le travail à un utilisateur

- Tapez l’cmdlet suivante
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Par exemple, l’cmdlet suivante affecte la stratégie Appel via le travail « ContosoUser1CvWP » à l’utilisateur nommé **ContosoUser1**.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Voir aussi

[Planifier l’appel via le travail dans Skype Entreprise Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

