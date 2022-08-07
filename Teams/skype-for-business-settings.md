---
title: Gérer Skype Entreprise paramètres dans le Centre d’administration Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
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
description: Découvrez comment gérer les paramètres des fonctionnalités Skype Entreprise dans le Centre d’administration Microsoft Teams.
ms.openlocfilehash: 26b2ba51d42a7be227b513d72add3e34f07d0fcd
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269759"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gérer Skype Entreprise paramètres dans le Centre d’administration Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

En tant qu’administrateur, le Centre d’administration Microsoft Teams est l’endroit où vous gérez Skype Entreprise fonctionnalités pour Skype Entreprise utilisateurs de votre organisation. Vous pouvez gérer les paramètres [de votre organisation](#manage-skype-for-business-settings-for-your-organization) sur la page **Skype Entreprise** et les paramètres [des utilisateurs individuels](#manage-skype-for-business-settings-for-individual-users) sous l’onglet **Skype Entreprise** des pages de détails utilisateur.

La page **Skype Entreprise** s’affiche uniquement si le mode de coexistence de votre organisation n’est pas défini **sur Teams uniquement**. De même, vous ne verrez l’onglet **Skype Entreprise** pour un utilisateur que si le mode de coexistence de l’utilisateur n’est pas **Uniquement Teams**. Pour en savoir plus sur les modes de coexistence, consultez [Comprendre Teams et Skype Entreprise coexistence et interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md) et [définir vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> Skype Entreprise paramètres étaient précédemment dans le **portail hérité** dans le Centre d’administration Microsoft Teams. Avec la mise hors service du portail hérité, nous avons migré les paramètres vers ces nouveaux emplacements dans le Centre d’administration Teams pour la gestion Skype Entreprise.

Le [rôle d’administrateur Azure AD](/azure/active-directory/roles/permissions-reference) de l’administrateur général ou de l’administrateur Skype Entreprise doit vous être attribué pour gérer Skype Entreprise fonctionnalités dans le Centre d’administration Microsoft Teams.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gérer les paramètres de Skype Entreprise pour votre organisation

Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **paramètres** >  à **l’échelle** de l’organisation Skype Entreprise. À partir de là, vous pouvez configurer et gérer Réunion Skype notifications de diffusion, de confidentialité de présence et d’appareil mobile pour tous les utilisateurs Skype Entreprise de votre organisation.

### <a name="skype-meeting-broadcast"></a>Diffusion de réunion Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Utilisez les paramètres suivants pour gérer [Réunion Skype diffusion](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) dans votre organisation.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Capture d’écran des paramètres de diffusion Réunion Skype dans le Centre d’administration.":::

- **Réunion Skype Diffusions** : activez cette option pour activer Réunion Skype Diffusion pour votre organisation. Une fois cette fonctionnalité activée, vous devez [configurer votre réseau pour Réunion Skype Diffusion](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **Voir les fonctionnalités en préversion** : activez cette option pour accéder en avant-première aux nouvelles fonctionnalités.
- **Les organisateurs peuvent planifier des réunions anonymes** : activez cette option si vous souhaitez permettre aux organisateurs de créer des événements de diffusion qui permettent à toute personne extérieure à votre organisation de participer sans avoir à se connecter. 
- **Enregistrer Réunion Skype diffuser des réunions** : activez cette option pour permettre aux organisateurs et aux présentateurs d’enregistrer les réunions.  
- **URL de support technique pour les participants** : entrez l’URL de support de votre organisation que les participants à la réunion peuvent utiliser s’ils ont besoin d’aide pendant une réunion.

### <a name="presence-and-mobile-notifications"></a>Notifications de présence et mobiles

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Utilisez les paramètres suivants pour gérer Skype Entreprise la confidentialité de la présence et les notifications mobiles dans votre organisation.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Capture d’écran des paramètres de présence dans le Centre d’administration.":::

#### <a name="presence"></a>Présence

Par défaut, Skype Entreprise utilisateurs de votre organisation peuvent voir l’état de présence (par exemple, Disponible, Occupé ou Absent) d’autres utilisateurs Skype Entreprise. Choisissez l’une des options suivantes pour définir qui peut voir la présence de vos utilisateurs Skype Entreprise.

- **Afficher automatiquement les informations de présence** : tout utilisateur Skype Entreprise de votre organisation qui n’a pas été ajouté à la liste **externe** ou **bloquée** de l’utilisateur peut voir la présence de cet utilisateur.
- **Afficher les informations de présence uniquement aux contacts d’un utilisateur** : tout utilisateur Skype Entreprise dans la liste contacts de l’utilisateur qui n’est pas ajouté à sa liste **externe** ou **bloquée** peut voir la présence de cet utilisateur. Les utilisateurs peuvent remplacer ce paramètre dans Skype Entreprise en cliquant sur **Options** des **outils** >  de **paramètres** > .

#### <a name="mobile-notifications"></a>Notifications mobiles

Vous pouvez définir si vos Skype Entreprise utilisateurs mobiles reçoivent des alertes sur les messages instantanés entrants et manqués, les messages vocaux et les appels manqués via un service de notification Push. Selon les appareils mobiles utilisés dans votre organisation, vous pouvez utiliser le **service de notification Push Microsoft**, le **service de notification Push Apple** ou les deux.

Tenez compte des points suivants :

- Si vous désactivez les notifications Push, les utilisateurs recevront toutes les alertes la prochaine fois qu’ils démarreront Skype Entreprise sur leur appareil mobile.
- Par défaut, les notifications Push sont activées. Les utilisateurs individuels peuvent les désactiver dans Skype Entreprise sur leur appareil mobile.
- Une fois les notifications Push désactivées, les utilisateurs ne peuvent plus les réactiver. 

> [!IMPORTANT]
> Microsoft utilise d'autres sociétés pour fournir des notifications Skype Entreprise pour appareils mobiles en temps réel aux utilisateurs de Windows Phone, iPhone et iPad. Consultez cette [déclaration de confidentialité](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gérer les paramètres Skype Entreprise pour les utilisateurs individuels

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Pour gérer Skype Entreprise paramètres pour les utilisateurs individuels, dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Utilisateurs**, cliquez sur le nom d’affichage de l’utilisateur pour ouvrir la page de détails de l’utilisateur, puis sélectionnez l’onglet **paramètres Skype Entreprise**. À partir de là, vous pouvez configurer les paramètres d’accès externe et de réunion pour l’utilisateur.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Capture d’écran de l’onglet Skype Entreprise sur la page de détails de l’utilisateur.":::

### <a name="external-access-settings"></a>Paramètres d’accès externe

Vous pouvez autoriser ou bloquer de manière sélective si un utilisateur peut communiquer avec des personnes extérieures à votre organisation.

- **Utilisateurs externes Skype Entreprise** : activez cette option si vous souhaitez permettre à l’utilisateur de communiquer avec Skype Entreprise utilisateurs dans des domaines fédérés.
- **Utilisateurs Skype externes** : activez cette option si vous souhaitez autoriser l’utilisateur à communiquer avec les utilisateurs Skype. 

### <a name="meeting-settings"></a>Paramètres de réunion

Vous pouvez configurer les paramètres de réunion suivants pour l’utilisateur.

- **Audio & Video** : choisissez l’un des paramètres audio et vidéo suivants :

    - **Aucun** : l’utilisateur ne peut pas utiliser d’audio ou de vidéo.
    - **Audio uniquement** : l’utilisateur peut utiliser l’audio, mais pas la vidéo.
    - **Audio et vidéo** : l’utilisateur peut utiliser l’audio et la vidéo.
    - **Audio et vidéo (HD)** : l’utilisateur peut utiliser la vidéo audio et haute définition.
    
- **Enregistrer les conversations & réunions** : activez cette option pour permettre à l’utilisateur d’enregistrer les conversations et les réunions.
- **Conformité** : activez cette option si vous êtes légalement tenu de conserver les informations stockées électroniquement.