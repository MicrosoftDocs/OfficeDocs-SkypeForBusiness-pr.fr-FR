---
title: Configurer votre réseau pour la Diffusion de réunion Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: e1f10ad5036e2866cc480491e98bd2dd7396895a
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23862214"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurer votre réseau pour la Diffusion de réunion Skype

Après avoir [Activer la diffusion de réunion Skype](enable-skype-meeting-broadcast.md) de diffusion de réunion Skype, vous devez configurer votre réseau. Effectuez cette étape si vous souhaitez bloquer les conférences Web et autres diffusions pour les personnes à l’extérieur de votre entreprise.

Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.

Pour ignorer cette étape et l’ajouter à la place une autre entreprise de votre fédération afin que vous pouvez les inviter à diffusions, suivez les étapes de [Autoriser les utilisateurs à contacts Skype externe pour les utilisateurs professionnels](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).

## <a name="step-1-set-up-allowed-domains"></a>Étape 1 : Configurer des domaines autorisés

Utilisez l' **une** des méthodes suivantes pour configurer des domaines autorisés :

###

 **Méthode 1 : Utiliser le centre d’administration Office 365**

1. Accédez au **Centre d’administration Office 365** et puis, dans la navigation de gauche, cliquez sur **paramètres** > **Services &amp; compléments**, puis choisissez **Skype pour les entreprises**.

2. Dans la page **partage externe** sous **exceptions du domaine**, sélectionnez **tous les domaines bloqués à l’exception**, puis entrez les domaines suivants, séparés par une virgule (,) :

  - noammeetings.Lync.com

  - emeameetings.Lync.com

  - apacmeetings.Lync.com

  - Resources.Lync.com

3. Cliquez sur **Enregistrer**.

###

 **Méthode 2 : Utiliser Windows PowerShell**

- Dans le **Menu Démarrer**, avec le bouton droit de **Windows PowerShell** , cliquez sur **Exécuter en tant qu’administrateur**. In the **Windows PowerShell** window, type each line and press Enter.

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Étape 2 : Ajout de diffusion réunion Skype, les URL et les domaines IP adresses

La deuxième étape du processus d’installation est vous permet d’ajouter des domaines qui sont nécessaires, puis ajoutez des adresses IP et les URL qui sont requis pour la diffusion de réunion Skype travailler.

- **Ajouter le Skype requis pour les URL de point de terminaison Business en ligne et les adresses IP en consultant la rubrique celles qui sont requises** [ici](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurer la diffusion de réunion Skype dans les déploiements et les organisations hybrides

Si vous avez un Skype pour l’organisation d’entreprise en ligne et d’un déploiement local de Lync Server 2010, Microsoft Lync Server 2013 et Skype pour Business Server 2015 et avez des utilisateurs à la fois en ligne et sur site, il existe des autres étapes de configuration que vous devrez faire dans Outre celles ci-dessus pour permettre à votre organisation locale communiquer avec Skype pour Business Online et autoriser tous les utilisateurs puissent créer et participer à une réunion Skype de diffusion. Pour voir quelles sont les conditions requises, voir [configuration de votre déploiement sur site de diffusion de réunion Skype](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Rubriques connexes

[Autoriser la diffusion de réunion Skype](enable-skype-meeting-broadcast.md)

[URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



