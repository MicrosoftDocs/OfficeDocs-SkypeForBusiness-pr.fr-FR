---
title: Désactiver le mode hybride pour terminer la migration vers le cloud
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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Cette annexe inclut des étapes détaillées sur la désactivation de l’environnement hybride dans le cadre de la consolidation du Cloud pour teams et Skype entreprise.
ms.openlocfilehash: f852a3fb44408c6601be8c6bd4f07946419cea71
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269658"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Désactiver le mode hybride pour terminer la migration vers le cloud

Après avoir déplacé tous les utilisateurs de l’environnement local vers le cloud, vous pouvez mettre hors service le déploiement de Skype Entreprise local. Outre la suppression d’un matériel, une étape importante consiste à séparer de manière logique ce déploiement sur site de Microsoft 365 ou Office 365 en désactivant l’environnement hybride. La désactivation de l’environnement hybride se compose de trois étapes :

1. Mettez à jour les enregistrements DNS pour qu’ils pointent vers Microsoft 365 ou Office 365.

2. Désactivez le domaine fractionné dans l’organisation Microsoft 365 ou Office 365.

3. Désactivez la fonctionnalité en local pour communiquer avec Microsoft 365 ou Office 365.

Ces étapes doivent être réalisées ensemble en tant qu’unité. Vous trouverez ci-dessous des informations détaillées. En outre, des recommandations sont fournies pour la gestion des numéros de téléphone des utilisateurs migrés une fois que le déploiement local est déconnecté.

Une fois ces étapes terminées, les serveurs Skype entreprise locaux ne sont plus utilisés et ces serveurs peuvent être recréés.

> [!Important] 
>Vous devez continuer à laisser les attributs msRTCSIP dans Active Directory Sync via Azure AD Connect dans Azure AD.  N’effacez pas ces attributs sauf s’il est demandé par le support technique.  N’exécutez pas Disable-CsUser dans l’environnement local. Si vous devez modifier l’adresse SIP d’un utilisateur, faites-le dans votre annuaire Active Directory local et laissez cette modification synchronisée dans Azure AD via Azure AD Connect, comme décrit ci-dessous. De même, si vous devez modifier un numéro de téléphone et que le LineURI de l’utilisateur est déjà défini en local, vous devez le modifier dans l’annuaire Active Directory local.
>L’effacement des attributs msRTCSIP locaux après avoir effectué une migration à partir de l’installation locale pourrait entraîner la perte de service pour les utilisateurs.

> [!Note] 
> Dans de rares cas, le fait de modifier le serveur DNS vers Microsoft 365 ou Office 365 pour votre organisation peut entraîner l’arrêt de la Fédération avec d’autres organisations jusqu’à ce que l’autre organisation ait mis à jour sa configuration de Fédération :<ul><li>
Toutes les organisations fédérées qui utilisent l’ancien modèle de Fédération directe (également appelé serveur partenaire autorisé) doivent mettre à jour leurs entrées de domaine autorisées pour leur organisation afin de supprimer le nom de domaine complet du proxy. Ce modèle de Fédération hérité n’est pas basé sur les enregistrements DNS SRV, de sorte qu’une telle configuration est devenue obsolète une fois que votre organisation passe dans le Cloud. </li><li>Toute organisation fédérée qui n’a pas de fournisseur d’hébergement activé pour sipfed. online. Lync. <span> com doit mettre à jour sa configuration pour l’activer. Cette situation n’est possible que si l’organisation fédérée est purement locale et n’a jamais été fédérée avec un client hybride ou en ligne. Dans ce cas, la Fédération avec ces organisations ne fonctionnera pas tant qu’elles n’auront pas activé leur fournisseur d’hébergement.</li></ul>Si vous pensez qu’un de vos partenaires fédérés peut utiliser la Fédération directe ou avoir fédéré avec une organisation en ligne ou hybride, nous vous suggérons de lui envoyer une communication à ce sujet à mesure que vous vous préparez à effectuer votre migration vers le Cloud.

1.  *Mettre à jour le DNS pour qu’il pointe vers Microsoft 365 ou Office 365.*
Le DNS externe de l’Organisation pour l’organisation locale doit être mis à jour de manière à ce que les enregistrements Skype entreprise pointent vers Microsoft 365 ou Office 365 au lieu du déploiement local. Notamment :

    |Type d’enregistrement|Nom|Durée de vie|Value (Valeur)|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed. online. Lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir. online. Lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir. online. Lync. <span> com|
    |CNAME| sip|    3600|   sipdir. online. Lync. <span> com|
    |CNAME| satisfaction|   3600|   webdir. online. Lync. <span> com|
    |CNAME| Dialin  |3600|  webdir. online. Lync. <span> com|

    En outre, des enregistrements CNAMe pour la réunion ou la numérotation (le cas échéant) peuvent être supprimés. Enfin, tous les enregistrements DNS pour Skype entreprise dans votre réseau interne doivent être supprimés.

    > [!Note] 
    > Dans de rares cas, il est possible que la Fédération avec d’autres organisations cesse de fonctionner avec le pointage local vers Office 365 pour votre organisation, jusqu’à ce que l’autre organisation ait mis à jour sa configuration de Fédération :
    >
    > - Toutes les organisations fédérées qui utilisent l’ancien modèle de Fédération directe (également appelé serveur partenaire autorisé) doivent mettre à jour leurs entrées de domaine autorisées pour leur organisation afin de supprimer le nom de domaine complet du proxy. Ce modèle de Fédération hérité n’est pas basé sur les enregistrements DNS SRV, de sorte qu’une telle configuration est devenue obsolète une fois que votre organisation passe dans le Cloud.
    > 
    > - Toute organisation fédérée qui n’a pas de fournisseur d’hébergement activé pour sipfed. online. Lync. <span> com doit mettre à jour sa configuration pour l’activer. Cette situation n’est possible que si l’organisation fédérée est purement locale et n’a jamais été fédérée avec un client hybride ou en ligne. Dans ce cas, la Fédération avec ces organisations ne fonctionnera pas tant qu’elles n’auront pas activé leur fournisseur d’hébergement.
    >
    > Si vous pensez qu’un de vos partenaires fédérés peut utiliser la Fédération directe ou n’a pas été fédéré avec une organisation en ligne ou hybride, nous vous suggérons de lui envoyer une communication à ce sujet à mesure que vous vous préparez à effectuer votre migration vers le Cloud.


2.  *Désactivez l’espace d’adressage SIP partagé dans l’organisation Microsoft 365 ou Office 365.*
La commande ci-dessous doit être exécutée à partir d’une fenêtre PowerShell de Skype entreprise online.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Désactivez la fonctionnalité locale pour communiquer avec Microsoft 365 ou Office 365.*  
La commande ci-dessous doit être exécutée à partir d’une fenêtre PowerShell locale :

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Gérer les adresses SIP et les numéros de téléphone pour les utilisateurs qui ont été migrés à partir de l’organisation locale

Les administrateurs peuvent gérer les utilisateurs qui ont été précédemment déplacés d’un serveur Skype entreprise local vers le Cloud, même après la désactivation du déploiement local. Si vous souhaitez modifier l’adresse SIP d’un utilisateur ou l’URI de ligne d’un utilisateur (et si l’adresse SIP ou l’URI de ligne est déjà défini dans l’annuaire Active Directory local), vous devez le faire dans l’annuaire Active Directory local et laisser les valeurs passer à Azure AD. Il n’est pas nécessaire d’utiliser Skype entreprise Server sur site. Au lieu de cela, vous pouvez modifier ces attributs directement dans l’annuaire Active Directory local, à l’aide du composant logiciel enfichable MMC utilisateurs et ordinateurs Active Directory, ou à l’aide de PowerShell. Si vous utilisez le composant logiciel enfichable MMC, ouvrez la page Propriétés de l’utilisateur, cliquez sur l’onglet Éditeur d’attributs, puis recherchez les attributs appropriés à modifier :

- Pour modifier l’adresse SIP d’un utilisateur, modifiez le `msRTCSIP-PrimaryUserAddress` . En outre, si l' `ProxyAddresses` attribut contient une valeur SIP, mettez à jour la valeur SIP de sorte qu’elle corresponde à la nouvelle valeur de `msRTCSIP-PrimaryUserAddress` . S’il ne contient pas de valeur SIP, vous pouvez le laisser vide.

- Pour modifier le numéro de téléphone d’un utilisateur, modifiez `msRTCSIP-Line` *-le s’il contient déjà une valeur*.

  ![Outil utilisateurs et ordinateurs Active Directory](../media/disable-hybrid-1.png)
  
Si l’utilisateur n’a pas à l’origine une valeur pour `LineURI` l’environnement local avant le déplacement, vous pouvez modifier l’LineURI à l’aide du `onpremLineUri` paramètre-de la [cmdlet Set-Csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) dans le module Skype entreprise Online PowerShell.


## <a name="see-also"></a>Voir aussi

[Consolidation du Cloud pour teams et Skype entreprise](cloud-consolidation.md)
