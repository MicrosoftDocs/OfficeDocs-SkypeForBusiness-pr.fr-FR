---
title: Gérer Skype Entreprise paramètres d’administration dans le Microsoft Teams d’administration
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment gérer les paramètres des fonctionnalités Skype Entreprise dans le Centre Microsoft Teams’administration.
ms.openlocfilehash: 0b16cea1cf29c0ff2c6362bc91e13f2241574d83
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848167"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gérer Skype Entreprise paramètres d’administration dans le Microsoft Teams d’administration

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

En tant qu’administrateur, Microsoft Teams centre d’administration vous permet de gérer Skype Entreprise fonctionnalités pour les Skype Entreprise utilisateurs dans votre organisation. Vous pouvez gérer les [paramètres](#manage-skype-for-business-settings-for-your-organization) de votre organisation sur la page **Skype Entreprise** et les [paramètres](#manage-skype-for-business-settings-for-individual-users) des utilisateurs individuels dans **l’onglet** Skype Entreprise des pages de détails de l’utilisateur.

Vous verrez uniquement la page **Skype Entreprise** si le mode de coexistence pour votre organisation n’est pas **Teams.** De même, vous verrez uniquement **l’onglet Skype Entreprise’un** utilisateur si le mode de coexistence de l’utilisateur n’est pas **Teams uniquement.** Pour en savoir plus sur les modes de coexistence, voir Comprendre Teams et [Skype Entreprise coexistence](teams-and-skypeforbusiness-coexistence-and-interoperability.md) et l’interopérabilité, et Définir vos paramètres de coexistence et [de mise à niveau.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> Skype Entreprise de gestion de données étaient auparavant dans **le portail hérité** du Centre Microsoft Teams’administration. Avec l’abandon de l’ancien portail, nous avons migré les paramètres vers ces nouveaux emplacements dans le centre d’administration Teams pour Skype Entreprise gestion.

Vous devez avoir le rôle [d Azure AD administrateur](/azure/active-directory/roles/permissions-reference) global ou d’administrateur Skype Entreprise pour gérer les fonctionnalités Skype Entreprise dans le Microsoft Teams d’administration.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gérer Skype Entreprise de gestion des paramètres pour votre organisation

Dans le panneau de navigation gauche du Microsoft Teams d’administration, allez dans les **paramètres à** l’échelle de l’organisation  >  **Skype Entreprise.** À partir de là, vous pouvez configurer et gérer la diffusion Réunion Skype, la confidentialité des informations de présence et les notifications sur les appareils mobiles pour tous les Skype Entreprise utilisateurs dans votre organisation.

### <a name="skype-meeting-broadcast"></a>Diffusion de réunion Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Utilisez les paramètres suivants pour gérer [Réunion Skype diffusion](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) dans votre organisation.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Capture d’écran Réunion Skype paramètres de diffusion dans le Centre d’administration.":::

- **Réunion Skype diffusions :** activez cette fonction pour activer Réunion Skype diffusion pour votre organisation. Après avoir activé cette fonctionnalité, vous devez configurer votre réseau pour [Réunion Skype diffusion.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Découvrez les fonctionnalités d’aperçu**: activer cette fonctionnalité pour accéder en avant-première aux nouvelles fonctionnalités.
- **Les organisateurs peuvent planifier** des réunions anonymes : activer cette fonction si vous souhaitez que les organisateurs créent des événements de diffusion qui permettent à tous les utilisateurs extérieurs à votre organisation de participer sans avoir à se connecter. 
- **Enregistrer Réunion Skype diffusion de réunions :** activez cette fonction pour permettre aux organisateurs et aux présentateurs d’enregistrer les réunions.  
- **URL du support** technique pour les participants : Entrez l’URL du support technique de votre organisation que les participants à la réunion peuvent utiliser s’ils ont besoin d’aide pendant une réunion.

### <a name="presence-and-mobile-notifications"></a>Notifications de présence et de téléphone mobile

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Utilisez les paramètres suivants pour gérer les notifications Skype Entreprise confidentialité de la présence mobile et les notifications mobiles dans votre organisation.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Capture d’écran des paramètres de présence dans le Centre d’administration.":::

#### <a name="presence"></a>Présence

Par défaut, Skype Entreprise utilisateurs de votre organisation peuvent voir le statut de présence (par exemple Disponible, Occupé(e) ou Absent(e) d’autres Skype Entreprise utilisateurs. Choisissez l’une des personnes suivantes pour définir qui peut voir la présence de vos Skype Entreprise utilisateurs.

- **Afficher automatiquement** les informations de présence : tout Skype Entreprise utilisateur de votre organisation qui  n’a pas été ajouté à la liste externe ou bloquée de l’utilisateur peut voir sa présence. 
- Afficher les informations de présence uniquement aux **contacts d’un** utilisateur : tout utilisateur Skype Entreprise dans  la  liste des contacts de l’utilisateur qui n’est pas ajouté à sa liste externe ou bloquée peut voir la présence de cet utilisateur. Les utilisateurs peuvent remplacer ce paramètre dans Skype Entreprise en vous Paramètres  >  **Options**  >  **outils.**

#### <a name="mobile-notifications"></a>Notifications mobiles

Vous pouvez définir si vos utilisateurs mobiles Skype Entreprise recevoir des alertes concernant les messages instantanés entrants et manqués, les messages vocaux et les appels manqués via un service de notifications Push. En fonction des appareils mobiles utilisés dans votre organisation, vous pouvez utiliser le service de notifications Push **Microsoft,** le service de **notifications Push Apple,** ou les deux.

Tenez compte des points suivants :

- Si vous désactiverez les notifications Push, les utilisateurs auront toutes les alertes au prochain démarrage d’Skype Entreprise sur leur appareil mobile.
- Par défaut, les notifications Push sont désactivées. Les utilisateurs individuels peuvent les désactiver Skype Entreprise sur leur appareil mobile.
- Une fois les notifications Push désactivées, les utilisateurs ne peuvent plus les réactiver. 

> [!IMPORTANT]
> Microsoft utilise d'autres sociétés pour fournir des notifications Skype Entreprise pour appareils mobiles en temps réel aux utilisateurs de Windows Phone, iPhone et iPad. Consultez cette [déclaration de confidentialité.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gérer les Skype Entreprise d’utilisateurs individuels

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Pour gérer les paramètres de Skype Entreprise d’utilisateurs individuels, dans le navigation gauche du Centre d’administration Teams, sélectionnez Utilisateurs, cliquez sur le nom complet de l’utilisateur pour ouvrir la page des détails de l’utilisateur, puis sélectionnez l’onglet **paramètres Skype Entreprise.** À partir de là, vous pouvez configurer l’accès externe et les paramètres de réunion pour l’utilisateur.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Capture d’écran Skype Entreprise’onglet sur la page de détails de l’utilisateur.":::

### <a name="external-access-settings"></a>Paramètres d’accès externe

Vous pouvez autoriser ou bloquer de manière sélective la communication d’un utilisateur avec des personnes extérieures à votre organisation.

- **Utilisateurs Skype Entreprise** externes : activer cette fonction si vous voulez autoriser l’utilisateur à communiquer avec d Skype Entreprise utilisateurs dans des domaines fédérés.
- **Utilisateurs Skype externes**: activer cette fonction si vous voulez autoriser l’utilisateur à communiquer avec Skype utilisateurs. 

### <a name="meeting-settings"></a>Paramètres de réunion

Vous pouvez configurer les paramètres de réunion suivants pour l’utilisateur.

- **Audio & vidéo**: choisissez l’un des paramètres audio et vidéo suivants :

    - **Aucun**: l’utilisateur ne peut pas utiliser l’audio ou la vidéo.
    - **Audio uniquement**: l’utilisateur peut utiliser l’audio, mais pas la vidéo.
    - **Audio et vidéo**: l’utilisateur peut utiliser l’audio et la vidéo.
    - **Audio et vidéo (HD)**: l’utilisateur peut utiliser l’audio et la vidéo haute définition.
    
- **Enregistrer des conversations & réunions**: activer cette fonction pour permettre à l’utilisateur d’enregistrer des conversations et des réunions.
- **Conformité**: Activer cette fonction si vous êtes légalement tenu de conserver les informations stockées électroniquement.