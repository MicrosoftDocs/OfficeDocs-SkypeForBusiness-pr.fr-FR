---
title: Désactiver hybride pour effectuer la migration vers le nuage
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cette annexe inclut des procédures détaillées permettant de désactiver hybride dans le cadre de la consolidation de cloud pour les équipes et Skype pour les entreprises.
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247646"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Désactiver hybride pour effectuer la migration vers le nuage

Après avoir déplacé tous les utilisateurs sur site vers le nuage, vous pouvez retirer la Skype sur site pour le déploiement d’entreprise. Outre la suppression de n’importe quel matériel, une étape importante consiste à séparer logiquement ce déploiement sur site à partir d’Office 365 en désactivant hybride. Désactivation hybride se compose des 3 étapes :

1. Mettre à jour les enregistrements DNS pour pointer vers Office 365.
2. Désactiver le domaine fractionné dans le client Office 365.
3. Désactiver la possibilité de communiquer avec Office 365 dans sur prem.


Ces étapes doivent être effectuées ensemble en tant qu’unité. Plus d’informations sont fournies ci-dessous.

> [!Note] 
> Rarement, modification DNS de pointage dans les locaux vers Office 365 pour votre organisation peut entraîner la fédération avec d’autres organisations arrêt avant que d’autres organisations mises à jour leur configuration de fédération :<ul><li>
Les organisations fédérées qui utilisent l’ancien modèle de fédération directe (également appelé serveur partenaire autorisé) vous devrez mettre à jour les entrées de domaines autorisés pour leur organisation permet de supprimer le nom de domaine complet du proxy. Ce modèle de fédération héritée n’est pas basé sur les enregistrements SRV DNS, afin que cette configuration système plus à jour une fois que votre organisation se déplace vers le nuage. </li><li>Toute organisation fédérée qui ne dispose pas d’un fournisseur d’hébergement activé pour sipfed.online.lync. <span>com vous devrez mettre à jour leur configuration afin d’activer qui. Cela est possible uniquement si l’organisation fédérée est purement localement et n’a jamais fédérée avec n’importe quel hybride ou le locataire en ligne. Dans ce cas, la fédération avec ces organisations ne fonctionnera pas jusqu'à ce qu’ils permettent à leur fournisseur d’hébergement.</li></ul>Si vous pensez qu’un de vos partenaires fédérés peuvent utiliser la fédération directe ont fédéré avec n’importe quel en ligne ou organisation hybride, nous vous recommandons de que les envoyer une communication sur ce que vous vous préparez à terminer votre migration vers le nuage.

1.  *Mettre à jour DNS pour pointer vers Office 365.*
DNS externe de l’organisation de l’organisation locale doit être mis à jour afin que Skype pour les enregistrements d’entreprise pointent vers Office 365 au lieu du déploiement local. Plus particulièrement :

    |Type d’enregistrement|Nom|DURÉE DE VIE|Valeur|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span>com|
    |CNAME| lyncdiscover|   3600|   WebDir.Online.Lync. <span>com|
    |CNAME| SIP|    3600|   sipdir.Online.Lync. <span>com|
    |CNAME| répondre à|   3600|   WebDir.Online.Lync. <span>com|
    |CNAME| Dialin  |3600|  WebDir.Online.Lync. <span>com|

2.  *Désactiver l’espace d’adressage SIP partagé dans le client Office 365.*
La commande suivante doit être effectuée à partir d’un Skype pour fenêtre Business Online PowerShell.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Désactiver la possibilité de communiquer avec Office 365 dans sur prem.*  
La commande suivante doit être effectuée à partir d’une fenêtre de PowerShell locale.  Si vous avez précédemment importé un Skype pour la session Business en ligne, démarrez un nouveau Skype pour la session PowerShell Business.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>Voir aussi

[Consolidation de cloud pour les équipes et Skype pour les entreprises](cloud-consolidation.md)