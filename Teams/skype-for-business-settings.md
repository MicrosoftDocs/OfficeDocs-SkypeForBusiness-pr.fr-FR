---
title: Gérer les paramètres de Skype Entreprise dans le Centre d’administration Microsoft Teams
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment gérer les paramètres des fonctionnalités de Skype Entreprise dans le Centre d’administration Microsoft Teams.
ms.openlocfilehash: 944a5f8101b8355f4a2cc3e18966e5eb01b94be9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834214"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gérer les paramètres de Skype Entreprise dans le Centre d’administration Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

En tant qu’administrateur, le Centre d’administration Microsoft Teams est l’endroit où vous gérez les fonctionnalités de Skype Entreprise pour les utilisateurs de Skype Entreprise dans votre organisation. Vous pouvez gérer les [paramètres](#manage-skype-for-business-settings-for-your-organization) de votre organisation sur la page **Skype** Entreprise et les [paramètres](#manage-skype-for-business-settings-for-individual-users) des utilisateurs individuels sous l’onglet **Skype** Entreprise des pages de détails de l’utilisateur.

Vous verrez uniquement la page **Skype** Entreprise si le mode de coexistence pour votre organisation n’est pas réglé sur **Teams uniquement.** De même, vous ne verrez l’onglet **Skype** Entreprise d’un utilisateur que si le mode de coexistence de l’utilisateur n’est pas **Seulement Teams.** Pour en savoir plus sur les modes de coexistence, voir Comprendre la [coexistence](teams-and-skypeforbusiness-coexistence-and-interoperability.md) et l’interopérabilité de Teams et Skype Entreprise, et Définir vos paramètres de coexistence et [de mise à niveau.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> Les paramètres de Skype Entreprise étaient auparavant dans **le portail hérité** du Centre d’administration Microsoft Teams. Avec l’abandon de l’ancien portail, nous avons migré les paramètres vers ces nouveaux emplacements dans le Centre d’administration Teams pour la gestion de Skype Entreprise.

Pour gérer les fonctionnalités de Skype Entreprise dans le Centre d’administration Microsoft Teams, vous devez avoir le rôle d’administrateur [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) d’administrateur global ou d’administrateur Skype Entreprise.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gérer les paramètres de Skype Entreprise pour votre organisation

Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez dans les paramètres à **l’échelle** de l’organisation  >  **De Skype Entreprise.** À partir de là, vous pouvez configurer et gérer la diffusion de réunion Skype, la confidentialité des informations de présence et les notifications sur les appareils mobiles pour tous les utilisateurs Skype Entreprise de votre organisation.

### <a name="skype-meeting-broadcast"></a>Diffusion de réunion Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Utilisez les paramètres suivants pour gérer la [diffusion de réunion Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) dans votre organisation.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Capture d’écran des paramètres de diffusion de réunion Skype dans le Centre d’administration":::

- **Diffusions de réunion Skype**: activez cette fonction pour activer la diffusion de réunion Skype pour votre organisation. Après avoir activé cette fonctionnalité, vous devez configurer votre réseau pour [la diffusion de réunion Skype.](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Découvrez les fonctionnalités d’aperçu**: activer cette fonctionnalité pour accéder en avant-première aux nouvelles fonctionnalités.
- **Les organisateurs peuvent planifier** des réunions anonymes : activer cette fonction si vous souhaitez que les organisateurs créent des événements de diffusion qui permettent à tous les utilisateurs extérieurs à votre organisation de participer sans avoir à se connecter. 
- **Enregistrez des réunions de** diffusion de réunion Skype : activez cette fonction pour permettre aux organisateurs et aux présentateurs d’enregistrer les réunions.  
- **URL du support** technique pour les participants : Entrez l’URL du support technique que les participants à la réunion peuvent utiliser s’ils ont besoin d’aide pendant une réunion.

### <a name="presence-and-mobile-notifications"></a>Notifications de présence et de téléphone mobile

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Utilisez les paramètres suivants pour gérer la confidentialité des informations de présence et les notifications mobiles de Skype Entreprise dans votre organisation.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Capture d’écran des paramètres de présence dans le Centre d’administration":::

#### <a name="presence"></a>Présence

Par défaut, les utilisateurs de Skype Entreprise de votre organisation peuvent voir le statut de présence d’autres utilisateurs Skype Entreprise (par exemple, Disponible, Occupé(e) ou Absent(e). Choisissez l’une des personnes suivantes pour définir qui peut voir la présence de vos utilisateurs Skype Entreprise.

- **Afficher automatiquement** les informations de présence : tous les utilisateurs Skype Entreprise de  votre  organisation qui n’ont pas été ajoutés à la liste externe ou bloquée de l’utilisateur peuvent voir sa présence.
- Afficher les informations de présence uniquement aux **contacts d’un** utilisateur : Tout utilisateur Skype Entreprise  dans  la liste des contacts de l’utilisateur qui n’est pas ajouté à sa liste externe ou bloquée peut voir la présence de cet utilisateur. Les utilisateurs peuvent remplacer ce paramètre dans Skype Entreprise en se rendre dans les options **Des outils**  >    >  **de paramètres.**

#### <a name="mobile-notifications"></a>Notifications mobiles

Vous pouvez définir si vos utilisateurs mobiles Skype Entreprise obtiennent des alertes concernant les messages instantanés entrants et manqués, les messages vocaux et les appels manqués via un service de notifications Push. Selon les appareils mobiles utilisés dans votre organisation, vous pouvez utiliser le service de notifications Push **Microsoft,** le service de **notifications Push Apple,** ou les deux.

Tenez compte des points suivants :

- Si vous désactiver les notifications Push, les utilisateurs seront informés de toutes les alertes lors du démarrage suivant de Skype Entreprise sur leur appareil mobile.
- Par défaut, les notifications Push sont désactivées. Les utilisateurs peuvent les désactiver dans Skype Entreprise sur leur appareil mobile.
- Une fois les notifications Push désactivées, les utilisateurs ne peuvent plus les réactiver. 

> [!IMPORTANT]
> Microsoft utilise d'autres sociétés pour fournir des notifications Skype Entreprise pour appareils mobiles en temps réel aux utilisateurs de Windows Phone, iPhone et iPad. Consultez cette [déclaration de confidentialité.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gérer les paramètres de Skype Entreprise pour des utilisateurs individuels

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Pour gérer les paramètres de Skype Entreprise pour des utilisateurs individuels, dans le navigation gauche du Centre d’administration Teams, sélectionnez **Utilisateurs,** cliquez sur le nom complet de l’utilisateur pour ouvrir la page des détails de l’utilisateur, puis sélectionnez l’onglet Paramètres de Skype Entreprise.  À partir de là, vous pouvez configurer l’accès externe et les paramètres de réunion pour l’utilisateur.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Capture d’écran de l’onglet Skype Entreprise sur la page des détails de l’utilisateur":::

### <a name="external-access-settings"></a>Paramètres d’accès externe

Vous pouvez autoriser ou bloquer de manière sélective la communication d’un utilisateur avec des personnes extérieures à votre organisation.

- **Utilisateurs externes de Skype** Entreprise : activer cette fonction si vous voulez autoriser l’utilisateur à communiquer avec les utilisateurs de Skype Entreprise dans des domaines fédérés.
- **Utilisateurs Skype externes**: activer cette fonction si vous souhaitez autoriser l’utilisateur à communiquer avec les utilisateurs de Skype. 

### <a name="meeting-settings"></a>Paramètres de réunion

Vous pouvez configurer les paramètres de réunion suivants pour l’utilisateur.

- **Audio & vidéo**: choisissez l’un des paramètres audio et vidéo suivants :

    - **Aucun**: l’utilisateur ne peut pas utiliser l’audio ou la vidéo.
    - **Audio uniquement**: l’utilisateur peut utiliser l’audio, mais pas la vidéo.
    - **Audio et vidéo**: l’utilisateur peut utiliser l’audio et la vidéo.
    - **Audio et vidéo (HD)**: l’utilisateur peut utiliser l’audio et la vidéo haute définition.
    
- **Enregistrer des conversations & réunions**: activer cette fonction pour permettre à l’utilisateur d’enregistrer des conversations et des réunions.
- **Conformité**: Activer cette fonction si vous êtes légalement tenu de conserver les informations stockées électroniquement. 
