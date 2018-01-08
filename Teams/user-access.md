---
title: "Gérer l'accès des utilisateurs à Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez comment activer ou désactiver le niveau d'accès par utilisateur."
ms.openlocfilehash: 66ec29077b83b799c85acce1b5869b82fb0b83f7
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2017
---
<a name="manage-user-access-to-microsoft-teams"></a>Gérer l'accès des utilisateurs à Microsoft Teams
=====================================

Au niveau utilisateur, l'accès à Microsoft Teams peut être activé ou désactivé par utilisateur en affectant ou en supprimant la licence du produit Microsoft Teams.

Actuellement, hormis l'affection ou la suppression de licence, il n'existe aucune option de stratégie, ni sous-ensemble de fonctionnalités, permettant d'activer ou de désactiver Microsoft Teams de manière individuelle.



> [!NOTE]
>Microsoft recommande d'activer Microsoft Teams pour tous les utilisateurs dans l'entreprise de manière à pouvoir créer des équipes organiques pour des projets et autres initiatives dynamiques. Même dans le cas de groupes pilote, il peut toujours être utile d'activer Microsoft Teams pour tous les utilisateurs, tout en ciblant uniquement les communications au groupe pilote d'utilisateurs.

Les licences Microsoft Teams de niveau utilisateur sont directement gérées via les interfaces de gestion utilisateur du centre d'administration Office 365. Un administrateur peut affecter des licences aux nouveaux utilisateurs lors de la création de comptes utilisateur ou à des utilisateurs disposant déjà d'un compte. L'administrateur doit disposer de droits d'administrateur général Office 365 ou d'administrateur de gestion des utilisateurs pour gérer les licences Microsoft Teams.

Lorsqu'une référence (SKU) de licence telle que Entreprise E3 ou E5 est affectée à un utilisateur, une licence Microsoft Teams est automatiquement affectée et le produit est activé pour l'utilisateur. Les administrateurs peuvent disposer d'un contrôle précis sur les services et licences Office 365 ; la licence Microsoft Teams peut être activée ou désactivée pour un utilisateur ou un groupe d'utilisateurs.

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

Une licence Microsoft Teams peut être désactivée à tout moment. Une fois la licence désactivée, les utilisateurs ne pourront plus accéder à Microsoft Teams ni afficher le produit dans le lanceur d'applications et la page d'accueil d'Office 365.

![Capture d'écran de la section Licences de produit dans le Centre d'administration Office 365, avec Microsoft Teams sélectionné.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

Outre le centre d'administration Office 365, les administrateurs d'Office 365 peuvent également utiliser PowerShell Office 365 pour affecter et supprimer des licences. Pour affecter une licence à un utilisateur, utilisez la syntaxe suivante :

Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"

Dans l'exemple suivant, une licence du plan de gestion des licences litwareinc:ENTERPRISEPACK (Office 365 Entreprise E3) est affectée à l'utilisateur sans licence belindan@litwareinc.com.

Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"

Pour obtenir plus de détails et d'exemples, reportez-vous à la page [*Attribuer des licences à des comptes d'utilisateurs avec Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).

Pour supprimer une licence d'un compte utilisateur existant, utilisez la syntaxe suivante :

Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"

Dans l'exemple suivant, la licence litwareinc:ENTERPRISEPACK (Office 365 Entreprise E3) est supprimée pour le compte d'utilisateur BelindaN@litwareinc.com.

Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"

Pour obtenir plus de détails et d'exemples, reportez-vous à la page [*Licence Office 365 et Windows PowerShell : Suppression d'une licence*](https://go.microsoft.com/fwlink/?linkid=855756).

| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |Point de décision         |<ul><li>Que prévoit votre organisation pour intégrer Microsoft Teams ?  (Groupe pilote ou licence ouvert)</li></ul>         |
|![Icône Étapes suivantes.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |Étapes suivantes         |<ul><li>Si l'intégration est effectuée via un projet pilote fermé, choisissez entre l'affectation de licence ou une communication ciblée.</li><li>En fonction de votre décision, prenez les mesures qui s'imposent pour garantir que seuls les utilisateurs du groupe pilote sont autorisés à accéder à Microsoft Teams (le cas échéant).</li><li>Indiquez les directives suivant lesquelles les utilisateurs auront accès ou non à Microsoft Teams ci-dessous.</li></ul>         |
