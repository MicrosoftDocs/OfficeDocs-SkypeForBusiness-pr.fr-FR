---
title: Affectation ou modification des emplacements d’urgence pour les utilisateurs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Dans cet article, vous allez découvrir comment affecter ou modifier l’emplacement d’urgence d’un emplacement pour les utilisateurs de votre organisation.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9bd69356be22954ee1b1b44b2dcc1a52c1e72507
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634883"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Affectation ou modification de l’emplacement d’urgence d’un utilisateur

Quelle que soit l’option de connectivité [RST que](pstn-connectivity.md) vous choisissez, vous choisissez plans d’appel Microsoft, opérateur Connecter ou routage direct un emplacement d’urgence doit être affecté à chaque numéro de téléphone ou &mdash; &mdash; utilisateur.

Toutefois, en fonction de l’option de connectivité RSTN, la façon dont vous gérez et attribuez des emplacements d’urgence à un utilisateur peut varier. Pour plus d’informations, voir [Gérer les appels d’urgence.](what-are-emergency-locations-addresses-and-call-routing.md)

Cet article explique comment affecter  ou modifier l’emplacement d’urgence d’un utilisateur dans le Microsoft Teams d’administration ou à l’aide de PowerShell.

Cet article s’applique aux forfaits d’appels et aux Connecter.

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le navigation gauche du Centre d Microsoft Teams' administration, cliquez sur **Les** numéros Téléphone  >  **voix.**

2. Dans la page **Téléphone nombres,** cliquez sur l’onglet Nombres, sélectionnez un numéro d’utilisateur dans la liste, puis cliquez sur  **Modifier.**

3. Dans le **volet Édition,** sous Emplacement **d’urgence,** faites l’une des opérations suivantes :

    - Pour attribuer un lieu, recherchez l’emplacement, puis sélectionnez-le dans les résultats de la recherche.

    - Pour modifier l’emplacement déjà attribué à l’utilisateur, cliquez sur **X** pour supprimer l’emplacement et l’emplacement existants, recherchez et sélectionnez l’emplacement à affecter.

4. Selon que vous voulez envoyer un courrier électronique à l’utilisateur avec ses informations de numéro de téléphone, désactiver ou activer l’utilisateur de courrier avec des **informations de numéro de téléphone.** Par défaut, c’est le cas.

5. Cliquez sur **Appliquer**.

## <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsOnlineLisLocation.](/powershell/module/skype/set-csonlinelislocation)
    
## <a name="related-topics"></a>Sujets associés

- [Gestion des appels d’urgence](what-are-emergency-locations-addresses-and-call-routing.md)
- [Affecter ou modifier un emplacement d’urgence pour un utilisateur](assign-change-emergency-location-user.md)
- [Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](add-change-remove-emergency-location-organization.md)
- [Ajouter, modifier ou supprimer un lieu pour un emplacement d’urgence dans votre organisation](add-change-remove-emergency-place-organization.md)
- [Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)