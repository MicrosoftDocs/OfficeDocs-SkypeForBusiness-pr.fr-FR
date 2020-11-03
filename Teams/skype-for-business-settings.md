---
title: Gérer les paramètres de Skype entreprise dans le centre d’administration Microsoft teams
author: lanachin
ms.author: v-lanac
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
description: Découvrez comment gérer les paramètres des fonctionnalités Skype entreprise dans le centre d’administration Microsoft Teams.
ms.openlocfilehash: 0a74b2586fa706dc8fe9db73c58b7d938eae59ee
ms.sourcegitcommit: 54e685b07d1c23100951d46913480989f046d534
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2020
ms.locfileid: "48827758"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gérer les paramètres de Skype entreprise dans le centre d’administration Microsoft teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

En tant qu’administrateur, le centre d’administration Microsoft teams vous permet de gérer les fonctionnalités de Skype entreprise pour les utilisateurs Skype entreprise de votre organisation. Vous pouvez gérer les paramètres [de votre organisation](#manage-skype-for-business-settings-for-your-organization) dans la page **Skype entreprise** et [les paramètres d’utilisateurs individuels](#manage-skype-for-business-settings-for-individual-users) dans l’onglet **Skype entreprise** de la page de détails de l’utilisateur.

La page **Skype entreprise** s’affiche uniquement si le mode de coexistence pour votre organisation n’est pas défini sur **équipes uniquement**. De même, vous ne verrez que l’onglet **Skype entreprise** pour un utilisateur si le mode de coexistence de l’utilisateur n’est pas l' **équipe**. Pour en savoir plus sur les modes de coexistence, voir [comprendre les équipes et la coexistence et l’interopérabilité de Skype entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md) et [définir vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> Les paramètres de Skype entreprise étaient auparavant dans le **portail hérité** dans le centre d’administration Microsoft Teams. Avec la mise hors service du portail hérité, nous avons migré les paramètres vers ces nouveaux emplacements dans le centre d’administration teams pour la gestion de Skype entreprise.

Pour pouvoir gérer les fonctionnalités de Skype entreprise dans le centre d’administration de Microsoft Teams, vous devez avoir le rôle d’administrateur [Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de l’administrateur général ou de l’administrateur Skype entreprise.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gestion des paramètres de Skype entreprise pour votre organisation

Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à paramètres à l’échelle de l' **organisation**  >  **Skype entreprise**. À partir de cet emplacement, vous pouvez configurer et gérer la diffusion de réunion Skype, la confidentialité de présence et les notifications de périphériques mobiles pour tous les utilisateurs Skype entreprise de votre organisation.

### <a name="skype-meeting-broadcast"></a>Diffusion de réunion Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Utilisez les paramètres suivants pour gérer la [diffusion de réunion Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) au sein de votre organisation.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Capture d’écran des paramètres de diffusion de réunion Skype dans le centre d’administration":::

- **Diffusions de réunion Skype** : activez cette fonction pour activer la diffusion de réunion Skype pour votre organisation. Après avoir activé cette fonction, vous devez [configurer votre réseau pour la diffusion de réunion Skype](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- Pour accéder en avant-première aux nouvelles fonctionnalités, **voir fonctionnalités d’aperçu** : activez cette fonction.
- Les **organisateurs peuvent planifier des réunions anonymes** : activez cette fonction si vous voulez permettre aux organisateurs de créer des événements de diffusion qui permettent à tout le monde à l’extérieur de votre organisation de participer sans se connecter. 
- **Enregistrez des réunions de diffusion de réunion Skype** : activez cette fonction pour permettre aux organisateurs et aux présentateurs d’enregistrer les réunions.  
- **URL du support technique pour les participants** : entrez l’URL d’assistance technique de votre organisation pour permettre aux participants de la réunion d’avoir besoin d’aide pendant une réunion.

### <a name="presence-and-mobile-notifications"></a>Notifications de présence et de téléphone mobile

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Utilisez les paramètres suivants pour gérer la confidentialité de présence de Skype entreprise et les notifications mobiles au sein de votre organisation.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Capture d’écran des paramètres de présence dans le centre d’administration":::

#### <a name="presence"></a>Présence

Par défaut, les utilisateurs Skype entreprise de votre organisation peuvent voir le statut de présence (disponible, occupé ou absent) d’autres utilisateurs de Skype entreprise. Choisissez l’une des options suivantes pour définir qui peut voir la présence de vos utilisateurs Skype entreprise.

- **Afficher automatiquement les informations de présence** : tout utilisateur de Skype entreprise de votre organisation qui n’a pas été ajouté à la liste **externe** ou **bloquée** de l’utilisateur peut voir la présence de cet utilisateur.
- **Afficher les informations de présence uniquement aux contacts d’un utilisateur** : tout utilisateur Skype entreprise dans la liste des contacts de l’utilisateur qui n’est pas ajouté à sa liste des contacts **externes** ou **bloqués** peut voir la présence de cet utilisateur. Les utilisateurs peuvent ignorer ce paramètre dans Skype entreprise en accédant aux **Settings**  >  **Tools**  >  **options** outils de configuration.

#### <a name="mobile-notifications"></a>Notifications mobiles

Vous pouvez déterminer si vos utilisateurs mobiles Skype entreprise reçoivent des alertes concernant les messages instantanés entrants et manqués, les messages vocaux et les appels en absence via un service de notifications de transmission. En fonction des appareils mobiles utilisés dans votre organisation, vous pouvez utiliser le **service de notification Microsoft émission** , le **service de notifications de transmission d’Apple** ou les deux.

Tenez compte des points suivants :

- Si vous désactivez les notifications de transmission, les utilisateurs recevront toutes les alertes lors du prochain démarrage de Skype entreprise sur leur appareil mobile.
- Par défaut, les notifications de transmission sont activées. Les utilisateurs individuels peuvent les désactiver dans Skype entreprise sur leur appareil mobile.
- Une fois les notifications Push désactivées, les utilisateurs ne peuvent plus les réactiver. 

> [!IMPORTANT]
> Microsoft utilise d'autres sociétés pour fournir des notifications Skype Entreprise pour appareils mobiles en temps réel aux utilisateurs de Windows Phone, iPhone et iPad. Consultez cette déclaration sur le respect de la [vie privée](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gestion des paramètres de Skype entreprise pour les utilisateurs individuels

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Pour gérer les paramètres de Skype entreprise pour les utilisateurs individuels, dans le volet de navigation de gauche du centre d’administration Teams, accédez à **utilisateurs** , cliquez sur le nom complet de l’utilisateur pour ouvrir la page des détails de l’utilisateur, puis sélectionnez l’onglet **paramètres de Skype entreprise** . À partir de cet emplacement, vous pouvez configurer l’accès externe et les paramètres de réunion pour l’utilisateur.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Capture d’écran de l’onglet Skype entreprise sur la page des détails de l’utilisateur":::

### <a name="external-access-settings"></a>Paramètres d’accès externe

Vous pouvez autoriser ou bloquer de manière sélective si un utilisateur peut communiquer avec des personnes extérieures à votre organisation.

- **Utilisateurs Skype entreprise externes** : activez cette fonction si vous voulez autoriser l’utilisateur à communiquer avec des utilisateurs de Skype entreprise dans des domaines fédérés.
- **Utilisateurs Skype externes** : activez cette fonction si vous voulez autoriser l’utilisateur à communiquer avec des utilisateurs de Skype. 

### <a name="meeting-settings"></a>Paramètres de la réunion

Vous pouvez configurer les paramètres de réunion suivants pour l’utilisateur.

- **Audio & vidéo** : choisissez l’un des paramètres audio et vidéo suivants :

    - **Aucun** : l’utilisateur ne peut pas utiliser l’audio ou la vidéo.
    - **Audio uniquement** : l’utilisateur peut utiliser le son, mais pas la vidéo.
    - **Audio et vidéo** : l’utilisateur peut utiliser les fonctionnalités audio et vidéo.
    - **Audio et vidéo (HD)** : l’utilisateur peut utiliser le son et la vidéo haute définition.
    
- **Enregistrer des conversations & des réunions** : activez cette fonction pour permettre à l’utilisateur d’enregistrer des conversations et des réunions.
- **Conformité** : activez cette fonction si vous êtes légalement tenu de conserver les informations stockées électroniquement. 
