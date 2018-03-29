---
title: Déployer l’appel via le bureau dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Résumé : Apprenez à déployer appeler Via le travail dans Skype pour Business Server 2015, pour tout ou partie de vos utilisateurs.'
ms.openlocfilehash: 325134bd4e24621bbb223ccc47180274256eaca2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-via-work-in-skype-for-business-server-2015"></a>Déployer l’appel via le bureau dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment déployer appeler Via le travail dans Skype pour Business Server 2015, pour tout ou partie de vos utilisateurs.
  
Suivez ces étapes pour déployer l’appeler Via le travail de vos utilisateurs. Considérations relatives à la planification sont décrits dans le [Plan pour appeler Via le travail dans Skype pour Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md). Dans les versions précédentes d’appel à distance de Lync Server contrôle était une fonctionnalité qui a permis aux utilisateurs de contrôler leur téléphone PBX avec Lync Server. Dans Skype pour le serveur de l’entreprise, cette fonctionnalité a été remplacée à appeler Via le travail. 
  
## <a name="prerequisites-for-call-via-work"></a>Conditions requises pour un appel Via le travail

Appeler Via le travail utilise Unified Communications Web API (UCWA), qui est automatiquement installé sur tous les Skype pour Business Server serveurs frontaux. Pour permettre aux utilisateurs d’appeler Via le travail, vous devez également les conditions préalables suivantes en place : 
  
- Vous devez disposer d’un serveur de médiation déployé, dans le cadre d’un serveur frontal ou d’un rôle autonome. Vous devez également déployer une passerelle IP-PBX.
    
- Tous les utilisateurs qui seront activés pour appeler Via le travail doivent avoir un appel vers l’intérieur directe (DID) sur le système téléphonique PBX. 
    
- Vous devez activer tous les utilisateurs d’appeler Via le travail de Voix Entreprise. Lorsque vous effectuez cette opération, vous devez configurer le Skype pour entreprise n’a un numéro pour chaque utilisateur au numéro DID correspondant pour le système téléphonique PBX correspondant. 
    
- Tous les utilisateurs qui utiliseront appeler Via le travail doivent avoir **La Configuration automatique** est sélectionnée dans l’option **Avancée de connexions** dans leur Skype pour client d’entreprise. Cela permet au client de découvrir les URL UCWA. **Configuration automatique** est sélectionné par défaut.
    
- Pour chaque utilisateur d’appeler Via le travail, activer le transfert d’appel et les appels simultanés. 
    
- Pour chaque utilisateur d’appeler Via le travail, vérifiez que l’option dans l’accès à la conférence et les conférences à distance sont activées. Cela permet à ces utilisateurs d’obtenir d’et vers Skype pour des conférences.
    
- Assurez-vous que le groupe réponse, appel d’équipe et la délégation sont désactivés pour chaque utilisateur d’appeler Via le travail.
    
## <a name="deploy-call-via-work"></a>Déployer l’appel via le bureau

Une fois les conditions préalables remplies, procédez comme suit :
  
- Créer un numéro de téléphone de global pour votre déploiement Skype pour entreprise affiche l’ID d’appelant PBX d’utilisateurs qui utilisent des appels de l’appeler Via le travail. 
    
- Créer une ou plusieurs stratégies d’appeler Via le travail
    
- Affecter une stratégie de l’appeler Via le travail à chaque utilisateur qui est activé pour les appeler Via le travail
    
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
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber
    <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

  ```

    Par exemple, l’applet de commande suivant crée une stratégie d’appeler Via le travail appelée ContosoUser1CvWP, l’utilisateur doit utiliser un numéro de rappel admin et définit ce numéro de rappel à 1-555-789-1234.
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Affecter une stratégie à appeler Via le travail à un utilisateur

- Saisissez l’applet de commande suivant
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Par exemple, l’applet de commande suivante affecte la stratégie de l’appeler Via le travail « ContosoUser1CvWP » à l’utilisateur nommé **ContosoUser1**.
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Voir aussi

#### 

[Plan pour un appel Via le travail dans Skype pour Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

