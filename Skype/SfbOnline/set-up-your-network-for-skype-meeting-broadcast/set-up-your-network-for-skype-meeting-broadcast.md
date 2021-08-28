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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 998fbb0a0c077507731d8db09521d49e5c5d635f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594848"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Configurer votre réseau pour la Diffusion de réunion Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Une fois [que Réunion Skype activé](enable-skype-meeting-broadcast.md) Réunion Skype diffusion, vous devez configurer votre réseau. Cette étape est prise en compte si vous souhaitez organiser des webinaires ou d’autres diffusions pour des personnes extérieures à votre entreprise.

> [!IMPORTANT]
> Skype Entreprise Online prend fin le 31 juillet 2021, date à laquelle l’accès au service prendra fin. Nous encourageons les clients à commencer la mise à niveau vers Microsoft Teams, le client principal pour les communications et le travail d’équipe dans Microsoft 365.

Si vous n'avez pas l'habitude de configurer votre pare-feu, envisagez de demander l'aide d'un [partenaire Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) pour effectuer cette étape pour vous.

Pour ignorer cette étape et ajouter une autre entreprise à votre fédération afin de les inviter à des diffusions, suivez les étapes de la procédure Autoriser les utilisateurs à contacter des utilisateurs Skype Entreprise [externes.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

## <a name="step-1-set-up-allowed-domains"></a>Étape 1 : configurer les domaines autorisés

Pour **configurer** des domaines autorisés, utilisez l’une des méthodes suivantes :

### <a name="method-1-use-the-admin-center"></a>Méthode 1 : utiliser le Centre d’administration

1. Dans le Centre d’administration, dans le navigation gauche, cliquez sur **Paramètres**  >  **&amp; Services,** puis sélectionnez **Skype Entreprise.**

2. Sur la page **Partage externe** sous **Exceptions** de domaine, sélectionnez Tous les domaines sont **bloqués** sauf, et entrez les domaines suivants, séparés par une virgule (,) :

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. Cliquez sur **Enregistrer**.

### <a name="method-2-use-windows-powershell"></a>Méthode 2 : utiliser la Windows PowerShell

- Dans le **menu Démarrer, cliquez** avec le bouton droit sur **Windows PowerShell** puis cliquez sur Exécuter en **tant qu’administrateur.** In the **Windows PowerShell** window, type each line and press Enter.

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>Étape 2 : ajouter Réunion Skype de diffusion, des URL et des adresses IP

La deuxième étape du processus de configuration consiste à ajouter les domaines nécessaires, puis à ajouter les adresses IP et URL requises pour que la diffusion Réunion Skype fonctionne.

- **Ajoutez les adresses SKYPE ENTREPRISE point de terminaison et d’adresses IP** en ligne en voyant les adresses requises [ici.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>Configurer la diffusion de réunion Skype dans les déploiements et les organisations hybrides

Si vous avez une organisation Skype Entreprise Online et un déploiement local de Lync Server 2010, de Microsoft Lync Server 2013 et de Skype Entreprise Server 2015 et que vous avez des utilisateurs à la fois en ligne et sur site, vous devez suivre d’autres étapes de configuration en plus de celle ci-dessus pour permettre à votre organisation sur site de communiquer avec Skype Entreprise Online et autoriser tous vos utilisateurs à rejoindre une diffusion Réunion Skype Broadcast. Pour consulter les conditions requises, consultez Configurer votre déploiement [local pour Réunion Skype Diffusion.](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)

## <a name="related-topics"></a>Rubriques connexes

[Activer une diffusion de réunion Skype](enable-skype-meeting-broadcast.md)

[URL et plages d’adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
