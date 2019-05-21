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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: f9a85a1f64f88b55d99c7a27694a46b7ea885849
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301287"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurer votre réseau pour la Diffusion de réunion Skype

Après l' [activation](enable-skype-meeting-broadcast.md) de la diffusion de réunion Skype, vous devez configurer votre réseau. Cette étape permet de mettre en avant des webinaires et d’autres émissions pour des personnes extérieures à votre entreprise.

Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.

Pour ignorer cette étape et ajouter une autre entreprise à votre Fédération pour pouvoir inviter celles-ci à être diffusées, suivez les étapes de la rubrique [autoriser les utilisateurs à contacter des utilisateurs Skype entreprise externes](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).

## <a name="step-1-set-up-allowed-domains"></a>Étape 1: configurer les domaines autorisés

Pour configurer des domaines autorisés, utilisez l' **une** des méthodes suivantes:

## #

 **Méthode 1: utiliser le centre d’administration Office 365**

1. Accédez au **Centre d’administration Office 365** , puis, dans le volet de navigation de gauche, cliquez sur **paramètres** > des**compléments services &amp; **, puis sélectionnez **Skype entreprise**.

2. Dans la page **partage externe** , sous **exceptions de domaine**, sélectionnez **tous les domaines sont bloqués à l’exception**de, puis entrez les domaines suivants, en les séparant par une virgule (,):

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Cliquez sur **Enregistrer**.

## #

 **Méthode 2: utiliser Windows PowerShell**

- Dans le **menu Démarrer**, cliquez avec le bouton droit sur **Windows PowerShell** , puis cliquez sur **exécuter en tant qu’administrateur**. In the **Windows PowerShell** window, type each line and press Enter.

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Étape 2: ajouter des domaines, des URL et des adresses IP pour la diffusion de réunion Skype

La deuxième étape du processus de configuration consiste à ajouter d’abord les domaines nécessaires, puis à ajouter des adresses IP et des URL requises pour le bon fonctionnement de la diffusion de réunion Skype.

- **Ajoutez les URL et adresses IP de points de terminaison Skype entreprise Online requises en vérifiant lesquelles sont nécessaires** . [ici](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurer la diffusion de réunion Skype dans les déploiements et les organisations hybrides

Si vous disposez d’une organisation Skype entreprise Online et d’un déploiement local de Lync Server 2010, Microsoft Lync Server 2013 et de Skype entreprise Server 2015 et que les utilisateurs sont connectés et en local, vous devez effectuer les opérations suivantes. vous pouvez également accéder à ces éléments pour permettre à votre organisation locale de communiquer avec Skype entreprise Online et de permettre aux utilisateurs de participer à une diffusion de réunion Skype. Pour connaître la configuration requise, reportez-vous à [la section configurer votre déploiement local pour la diffusion de réunion Skype](https://go.microsoft.com/fwlink/?LinkId=617070).

## <a name="related-topics"></a>Voir aussi

[Activer une diffusion de réunion Skype](enable-skype-meeting-broadcast.md)

[URL et plages d’adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



