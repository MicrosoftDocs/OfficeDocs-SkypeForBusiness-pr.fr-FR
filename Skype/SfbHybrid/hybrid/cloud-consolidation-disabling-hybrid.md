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
description: Cette annexe comprend des étapes détaillées pour la désactivation de l’hybride dans le cadre de la consolidation du cloud pour Teams et Skype Entreprise.
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277256"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Désactiver le mode hybride pour terminer la migration vers le cloud

Après avoir déplacé tous les utilisateurs de l’environnement local vers le cloud, vous pouvez mettre hors service le déploiement de Skype Entreprise local. En plus de supprimer du matériel, une étape critique consiste à séparer logiquement ce déploiement local de Microsoft 365 ou Office 365 en désactivant l’hybride. La désactivation hybride se compose de 3 étapes :

1. Mettez à jour les enregistrements DNS pour qu’ils pointent vers Microsoft 365 ou Office 365.

2. Désactivez le domaine fractioné dans l’organisation Microsoft 365 ou Office 365.

3. Désactivez la possibilité de communiquer en local avec Microsoft 365 ou Office 365.

Ces étapes doivent être réalisées ensemble. Les détails sont fournis ci-dessous. En outre, des instructions sont fournies pour la gestion des numéros de téléphone pour les utilisateurs migrés une fois le déploiement local déconnecté.

Une fois ces étapes terminées, les serveurs Skype Entreprise locaux ne sont plus utilisés et ces serveurs peuvent être re-image.

> [!Important] 
>Vous devez continuer à synchroniser les attributs msRTCSIP dans Active Directory via Azure AD Connect dans Azure AD.  N’effacer aucun de ces attributs, sauf si le support l’y a demandé.  N’exécutez Disable-CsUser dans l’environnement local. Si vous devez modifier l’adresse SIP d’un utilisateur, faites-le dans votre annuaire Active Directory local et laissez ce changement se synchroniser avec Azure AD via Azure AD Connect, comme décrit ci-dessous. De même, si vous devez modifier un numéro de téléphone et que l’URI de ligne de l’utilisateur est déjà défini en local, vous devez le modifier dans l’annuaire Active Directory local.
>L’effacement des attributs msRTCSIP locaux une fois que vous avez migré à partir de l’local peut entraîner une perte de service pour les utilisateurs !


1.  *Mettez à jour le DNS pour qu’il pointe vers Microsoft 365 ou Office 365.*
Le DNS externe de l’organisation pour l’organisation sur site doit être mis à jour afin que les enregistrements Skype Entreprise pointent vers Microsoft 365 ou Office 365 au lieu du déploiement local. Notamment :

    |Type d’enregistrement|Nom|Durée de vie|Value (Valeur)|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|
    |CNAME| meet|   3600|   webdir.online.lync. <span> com|
    |CNAME| dialin  |3600|  webdir.online.lync. <span> com|

    En outre, les enregistrements CNAME pour la meet ou dialin (le cas présent) peuvent être supprimés. Enfin, tous les enregistrements DNS pour Skype Entreprise dans votre réseau interne doivent être supprimés.

    > [!Note] 
    > Dans de rares cas, la modification du DNS de pointage local vers Office 365 pour votre organisation peut entraîner l’arrêt de la fédération avec d’autres organisations jusqu’à ce que cette autre organisation met à jour sa configuration de fédération :
    >
    > - Toutes les organisations fédérées qui utilisent l’ancien modèle de fédération directe (également appelé serveur partenaire autorisé) doivent mettre à jour leurs entrées de domaine autorisées pour que leur organisation supprime le nom de domaine réservé au proxy. Ce modèle de fédération hérité n’est pas basé sur des enregistrements DNS SRV, de sorte qu’une telle configuration ne sera plus à jour une fois que votre organisation sera installée dans le cloud.
    > 
    > - Toute organisation fédérée qui n’a pas de fournisseur d’hébergement activé pour sipfed.online.lync. <span> com devra mettre à jour sa configuration pour l’activer. Cette situation n’est possible que si l’organisation fédérée est purement sur site et n’a jamais été fédérée avec un client hybride ou en ligne. Dans ce cas, la fédération avec ces organisations ne fonctionne pas tant qu’elles n’ont pas activé leur fournisseur d’hébergement.
    >
    > Si vous pensez que l’un de vos partenaires fédérés peut utiliser la fédération directe ou n’avoir été fédéré avec aucune organisation en ligne ou hybride, nous vous suggérons de leur envoyer une communication à ce sujet lorsque vous vous préparez à terminer votre migration vers le cloud.


2.  *Désactivez l’espace d’adressare SIP partagé dans l’organisation Microsoft 365 ou Office 365.*
La commande ci-dessous doit être effectuée à partir d’une fenêtre PowerShell Skype Entreprise Online.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Désactiver la possibilité en local de communiquer avec Microsoft 365 ou Office 365.*  
La commande ci-dessous doit être effectuée à partir d’une fenêtre PowerShell sur site :

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Gérer les adresses SIP et les numéros de téléphone des utilisateurs qui ont été migrés en local

Les administrateurs peuvent gérer les utilisateurs qui ont été précédemment déplacés d’un serveur Skype Entreprise local vers le cloud, même après la désaffectation du déploiement local. Si vous souhaitez apporter des modifications à l’adresse SIP d’un utilisateur ou à l’URI de ligne d’un utilisateur (et que l’adresse SIP ou l’URI de ligne est déjà défini dans l’annuaire Active Directory local), vous devez le faire dans l’annuaire Active Directory local et laisser les valeurs circuler vers Azure AD. Cela ne nécessite PAS Skype Entreprise Server local. Au lieu de cela, vous pouvez modifier ces attributs directement dans Active Directory local, à l’aide du logiciel en ligne MMC Utilisateurs et ordinateurs Active Directory ou à l’aide de PowerShell. Si vous utilisez le logiciel en snap-in MMC, ouvrez la page des propriétés de l’utilisateur, cliquez sur l’onglet Éditeur d’attributs et recherchez les attributs appropriés à modifier :

- Pour modifier l’adresse SIP d’un utilisateur, modifiez le `msRTCSIP-PrimaryUserAddress` . En outre, si l’attribut contient une valeur SIP, mettez à jour cette valeur SIP pour qu’elle `ProxyAddresses` corresponde à la nouvelle valeur de `msRTCSIP-PrimaryUserAddress` . Si elle ne contient pas de valeur SIP, vous pouvez la laisser vide.

- Pour modifier le numéro de téléphone d’un utilisateur, modifiez `msRTCSIP-Line` *s’il a déjà une valeur.*

  ![Outil utilisateurs et ordinateurs Active Directory](../media/disable-hybrid-1.png)
  
Si l’utilisateur n’avait à l’origine pas de valeur pour l’environnement local avant le déplacement, vous pouvez modifier l’URI de ligne à l’aide du paramètre - dans `LineURI` l’cmdlet `onpremLineUri` [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) dans le module PowerShell de Skype Entreprise Online.


## <a name="see-also"></a>Voir aussi

[Consolidation du cloud pour Teams et Skype Entreprise](cloud-consolidation.md)
