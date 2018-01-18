---
title: "Configurer votre réseau de diffusion de réunion Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Obtenir des informations sur la fonctionnalité de diffusion de réunion Skype de Skype pour entreprise en ligne qui vous permet de planifier, produire et diffusion ou une manifestation grand public en ligne jusqu'à 10 000 participants."
ms.openlocfilehash: 3e4afb09d6a65654af418e14cc124e3c78dc0e0c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurer votre réseau de diffusion de réunion Skype

Une fois que vous [Activez diffusion de réunion Skype](enable-skype-meeting-broadcast.md) de diffusion de réunion Skype, vous devez configurer votre réseau. Effectuez cette étape si vous souhaitez maintenir des conférences Web et autres émissions pour les personnes à l’extérieur de votre entreprise.
  
Si vous n’êtes pas familiarisé avec la configuration de votre pare-feu, envisager d’engager un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) d’effectuer cette étape pour vous.
  
Pour ignorer cette étape et l’ajouter à la place une autre entreprise vous pouvez inviter les diffusions à votre fédération, suivez les étapes de [Autoriser les utilisateurs à contacter Skype externe pour les utilisateurs professionnels](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## <a name="step-1-set-up-allowed-domains"></a>Étape 1 : Configurer des domaines autorisés

Pour configurer des domaines autorisés, utilisez l' **une** des méthodes suivantes :
  
### 

 **Méthode 1 : Utiliser le centre d’administration Office 365**
  
1. Visitez le **Centre d’administration Office 365** et dans la navigation de gauche, cliquez sur **paramètres** > **Services &amp; des compléments**, puis cliquez sur **Skype pour les entreprises**.
    
2. Dans la page **partage externe** sous **exceptions du domaine**, sélectionnez **tous les domaines sont bloqués à l’exception**et entrez les domaines suivants, séparés par une virgule (,) :
    
  - noammeetings.Lync.com
    
  - emeameetings.Lync.com
    
  - apacmeetings.Lync.com
    
  - Resources.Lync.com
    
3. Cliquez sur **Enregistrer**.
    
### 

 **Méthode 2 : Utiliser Windows PowerShell**
  
- Dans le **Menu Démarrer**, avec le bouton droit de **Windows PowerShell** , puis cliquez sur **Exécuter en tant qu’administrateur**. Dans la fenêtre **Windows PowerShell** , tapez chaque ligne et appuyez sur ENTRÉE.
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Étape 2 : Ajout de diffusion réunion Skype domaines, des URL et IP adresses

La deuxième étape du processus d’installation consiste à ajouter des domaines qui sont nécessaires et ensuite ajouter des adresses IP et des URL qui sont requis pour la diffusion de réunion Skype fonctionner.
  
- **Ajouter le Skype requis pour les professionnels en ligne URL de point de terminaison et adresses IP voir celles qui sont requises** [ici](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurer la diffusion de réunion Skype dans les organisations et les déploiements hybride

Si vous avez un Skype pour l’organisation d’entreprise en ligne et d’un déploiement sur site de Lync Server 2010, Microsoft Lync Server 2013 et Skype pour Business Server 2015 et avez des utilisateurs à la fois en ligne et sur site, les autres étapes d’installation dont vous aurez besoin de Outre celles ci-dessus pour activer votre organisation sur place communiquer avec Skype pour entreprise en ligne et d’autoriser tous les utilisateurs puissent créer et joindre une diffusion de réunion Skype. Pour voir quelles sont ces exigences, consultez [configurer votre déploiement sur site de diffusion de réunion Skype](https://go.microsoft.com/fwlink/?LinkId=617070).
  
## <a name="related-topics"></a>Rubriques connexes

[Activer la diffusion de réunion Skype](enable-skype-meeting-broadcast.md)
  
[URL et plages d'adresses IP Office 365](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

