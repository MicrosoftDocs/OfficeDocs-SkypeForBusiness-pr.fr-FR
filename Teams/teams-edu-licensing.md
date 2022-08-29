---
title: Attribuer des licences Microsoft Teams pour l’éducation
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Découvrez comment attribuer des licences pour Microsoft Teams pour l'éducation.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- admindeeplinkMAC
ms.openlocfilehash: e57780436167e3a872e78a717d12cd3acc35a6e9
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426801"
---
# <a name="assign-microsoft-teams-licenses-for-education"></a>Attribuer des licences Microsoft Teams pour l’éducation

Cet article s’adresse aux administrateurs informatiques en éducation qui doivent attribuer des licences d’équipe à leurs enseignants, membres du personnel et étudiants.

Pour préparer vos utilisateurs à Teams, vous devez :

1. [Activez Microsoft Teams pour votre établissement scolaire dans le Centre d'administration Microsoft 365](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).
2. Attribuez des licences aux comptes d’utilisateur pour l’accès aux services Microsoft 365, y compris Teams.

## <a name="ways-to-assign-teams-licenses"></a>Méthodes d’attribution de licences Teams

Vous pouvez attribuer des licences à des comptes d’utilisateurs :

- Individuellement ou à un petit groupe d’utilisateurs dans le Centre d'administration Microsoft 365.
- Automatiquement via l’appartenance à un groupe à l’aide de licences [basées sur powerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) ou [active directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).

Cet article explique comment attribuer des licences dans le Centre d'administration Microsoft 365.

Dans le Centre d'administration Microsoft 365, vous pouvez attribuer des licences aux utilisateurs sur l’une des opérations suivantes :

- Page **Licences** pour attribuer des licences de produit à des utilisateurs spécifiques.
- Page **Utilisateurs actifs** pour affecter les licences des utilisateurs à des produits spécifiques.

> [!NOTE]
> Vous devez être administrateur général, administrateur de facturation, administrateur de licence ou administrateur de gestion des utilisateurs. Pour plus d'informations, consultez [À propos des rôles d'administrateur Office 365](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>Attribution de licences à des utilisateurs via la page Licences

Dans la page **Licences** , vous voyez une liste de tous les produits pour lesquels vous avez des abonnements, le nombre total de licences pour chaque produit, le nombre de licences attribuées et le nombre de licences disponibles.

1. Dans le [Centre d’administration](https://go.microsoft.com/fwlink/p/?linkid=2024339), accédez à la page [Licences](https://go.microsoft.com/fwlink/p/?linkid=842264) **de facturation** > .

2. Sélectionnez le produit pour lequel vous voulez attribuer des licences. Microsoft Teams fait partie de la référence SKU Microsoft 365 A1 for Students gratuite.

3. Choisissez **Affecter des licences**.

4. Dans le volet **Attribuer des licences aux utilisateurs**, commencez à taper un nom, lequel qui doit générer une liste de noms.

5. Sélectionnez le nom que vous recherchez dans les résultats pour l’ajouter à la liste. Vous pouvez ajouter jusqu'à 20 utilisateurs à la fois.

6. Sélectionnez **Activer ou désactiver les applications et les services** pour attribuer ou supprimer l’accès à des éléments particuliers, tels que Microsoft Teams. Veillez à ce que **Microsoft Teams** et **Office pour le web (éducation)** soient sélectionnés.

7. Lorsque vous avez terminé, sélectionnez **Attribuer**, puis choisissez **Fermer**.

### <a name="change-the-apps-and-services-a-user-has-access-to"></a>Modifier les applications et services aux

1. Sélectionnez la ligne contenant l'utilisateur.

2. Dans le volet droit, sélectionnez ou désélectionnez les applications et services auxquels vous voulez octroyer ou supprimer l'accès.

3. Une fois terminé, sélectionnez **Enregistrer**, puis choisissez **Fermer**.

## <a name="assign-licenses-to-users-on-the-active-users-page"></a>Attribuer des licences aux utilisateurs sur la page Utilisateurs actifs

1. Dans le [Centre d’administration](https://go.microsoft.com/fwlink/p/?linkid=2024339), accédez à la page **Utilisateurs** > [actifs](https://go.microsoft.com/fwlink/p/?linkid=834822) .

2. Sélectionnez les cercles en regard un(des) nom(s) d'utilisateur(s) auquel(auxquels) vous voulez attribuer une(des) licence(s).

3. En haut, sélectionnez **Gérer les licences de produit**.

4. Dans le volet **Attribuer des licences de produits**, sélectionnez **Ajouter aux attributions de licence de produit existantes**  >  **Suivant**.

5. Dans le volet **Ajouter aux produits existants**, positionnez le bouton bascule sur **Actif** correspondant à la licence que vous voulez attribuer aux utilisateurs sélectionnés. Veillez à ce que **Microsoft Teams** et **Office pour le web (éducation)** soient sélectionnés.

   Par défaut, tous les services associés à cette(ces) licence(s) sont automatiquement attribués à un ou plusieurs utilisateurs. Vous pouvez limiter les services mis à disposition des utilisateurs. Positionnez le bouton bascule sur **Inactif** pour les services que vous ne souhaitez pas attribuer aux utilisateurs.

6. En bas du volet, sélectionnez **Ajouter** > **une fermeture**.
