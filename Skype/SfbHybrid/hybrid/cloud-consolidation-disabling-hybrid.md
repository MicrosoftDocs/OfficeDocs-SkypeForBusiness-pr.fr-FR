---
title: Désactiver l’environnement hybride pour terminer la migration vers le Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cette annexe inclut des étapes détaillées sur la désactivation de l’environnement hybride dans le cadre de la consolidation du Cloud pour teams et Skype entreprise.
ms.openlocfilehash: d441d9fcc5e4f2cec495efabdbea423eaaec882c
ms.sourcegitcommit: 7920c47eb73e665dad4bf7214b28541d357bce25
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37962051"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Désactiver l’environnement hybride pour terminer la migration vers le Cloud

Après avoir déplacé tous les utilisateurs de l’organisation locale vers le Cloud, vous pouvez mettre hors service le déploiement Skype entreprise sur site. Outre la suppression d’un matériel, une étape essentielle consiste à séparer de manière logique ce déploiement sur site d’Office 365 en désactivant l’environnement hybride. La désactivation de l’environnement hybride se compose de trois étapes :

1. Mettez à jour les enregistrements DNS pour qu’ils pointent vers Office 365.

2. Désactivez le domaine fractionné dans le client Office 365.

3. Désactivez la fonctionnalité en local pour communiquer avec Office 365.

Ces étapes doivent être réalisées ensemble en tant qu’unité. Vous trouverez ci-dessous des informations détaillées. En outre, des recommandations sont fournies pour la gestion des numéros de téléphone des utilisateurs migrés une fois que le déploiement local est déconnecté.

> [!Note] 
> Dans de rares cas, il est possible que la Fédération avec d’autres organisations cesse de fonctionner avec le pointage local vers Office 365 pour votre organisation, jusqu’à ce que l’autre organisation ait mis à jour sa configuration de Fédération :<ul><li>
Toutes les organisations fédérées qui utilisent l’ancien modèle de Fédération directe (également appelé serveur partenaire autorisé) doivent mettre à jour leurs entrées de domaine autorisées pour leur organisation afin de supprimer le nom de domaine complet du proxy. Ce modèle de Fédération hérité n’est pas basé sur les enregistrements DNS SRV, de sorte qu’une telle configuration est devenue obsolète une fois que votre organisation passe dans le Cloud. </li><li>Toute organisation fédérée qui n’a pas de fournisseur d’hébergement activé pour sipfed. online. Lync. <span>com doit mettre à jour sa configuration pour l’activer. Cette situation n’est possible que si l’organisation fédérée est purement locale et n’a jamais été fédérée avec un client hybride ou en ligne. Dans ce cas, la Fédération avec ces organisations ne fonctionnera pas tant qu’elles n’auront pas activé leur fournisseur d’hébergement.</li></ul>Si vous pensez qu’un de vos partenaires fédérés peut utiliser la Fédération directe ou avoir fédéré avec une organisation en ligne ou hybride, nous vous suggérons de lui envoyer une communication à ce sujet à mesure que vous vous préparez à effectuer votre migration vers le Cloud.

1.  *Mettez à jour DNS pour qu’il pointe vers Office 365.*
Le DNS externe de l’Organisation pour l’organisation locale doit être mis à jour de manière à ce que les enregistrements Skype entreprise pointent vers Office 365 au lieu du déploiement local. Notamment :

    |Type d’enregistrement|Nom|TTL (Durée de vie)|Value (Valeur)|
    |---|---|---|---|
    |SRV|_sipfederationtls. _ TCP|3600|100 1 5061 sipfed. online. Lync. <span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir. online. Lync. <span>com|
    |CNAME| lyncdiscover|   3600|   webdir. online. Lync. <span>com|
    |CNAME| sip|    3600|   sipdir. online. Lync. <span>com|
    |CNAME| satisfaction|   3600|   webdir. online. Lync. <span>com|
    |CNAME| Dialin  |3600|  webdir. online. Lync. <span>com|

2.  *Désactivez l’espace d’adressage SIP partagé dans le client Office 365.*
La commande ci-dessous doit être exécutée à partir d’une fenêtre PowerShell de Skype entreprise online.

    ```
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Désactivez la fonctionnalité sur local pour communiquer avec Office 365.*  
La commande ci-dessous doit être exécutée à partir d’une fenêtre PowerShell locale.  Si vous avez déjà importé une session Skype entreprise Online, démarrez une nouvelle session Skype entreprise PowerShell comme suit :

```
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Gérer les numéros de téléphone pour les utilisateurs qui ont été migrés à partir de l’installation locale

Les administrateurs peuvent gérer les utilisateurs qui ont été précédemment déplacés d’un serveur Skype entreprise local vers le Cloud, même après la désactivation du déploiement local. Il existe deux possibilités :

- L’utilisateur n’a pas de valeur pour lineURI en local avant le déplacement. 

  Dans ce cas, vous pouvez modifier le LineURI à l’aide des paramètres-onpremLineUri de la [cmdlet Set-Csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) dans le module Skype entreprise Online PowerShell.

- L’utilisateur avait une lineURI locale avant le déplacement (vraisemblablement parce que l’utilisateur a été activé pour voix entreprise). 

  Si vous souhaitez modifier le lineURI, vous devez le faire dans l’annuaire Active Directory local et laisser la valeur circuler dans Azure AD. Il n’est pas nécessaire d’utiliser Skype entreprise Server sur site. Au lieu de cela, cet attribut, msRTCSIP-Line, peut être modifié directement dans l’annuaire Active Directory local, à l’aide du composant logiciel enfichable MMC utilisateurs et ordinateurs Active Directory, ou à l’aide de PowerShell. Si vous utilisez le composant logiciel enfichable MMC, ouvrez la page Propriétés de l’utilisateur, cliquez sur l’onglet Éditeur d’attributs, puis recherchez msRTCSIP-Line.

  ![Outil utilisateurs et ordinateurs Active Directory](../media/disable-hybrid-1.png)

## <a name="see-also"></a>Voir aussi

[Consolidation du Cloud pour teams et Skype entreprise](cloud-consolidation.md)
