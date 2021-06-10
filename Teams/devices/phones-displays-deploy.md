---
title: Déployer Teams téléphones mobiles et Teams’affichage à l’aide d’Intune
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Cet article fournit une vue d’ensemble des fonctionnalités qui sont Microsoft Teams aux affichages.
ms.openlocfilehash: 178f8c594f8953c56a2d354806e86f4a19de028f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120776"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Déployer Teams téléphones mobiles et Teams’affichage à l’aide d’Intune

Cet article vous donne une vue d’ensemble du déploiement de Teams téléphones et de Teams’affichages à l’aide d’Intune.

## <a name="conditional-access"></a>Accès conditionnel

L’accès conditionnel est Azure Active Directory (Azure AD) qui vous permet de vous assurer que les appareils qui accèdent à vos ressources Office 365 sont correctement gérés et sécurisés.  Si vous appliquez des stratégies d’accès conditionnel au service Teams, les appareils Android (y compris les téléphones Teams et les affichages Teams) qui accèdent à Teams doivent être inscrits à Intune et leurs paramètres doivent respecter vos stratégies.  Si l’appareil n’est pas inscrit à Intune, ou s’il est inscrit mais que ses paramètres ne respectent pas vos stratégies, l’accès conditionnel empêche un utilisateur de se connecté ou d’utiliser l’application Teams sur l’appareil.

En règle générale, les stratégies de conformité définies dans Intune sont affectées à des groupes d’utilisateurs.  Cela signifie que si vous attribuez une politique de conformité Android à user@contoso.com, cette stratégie s’appliquera également à leur smartphone Android et à tout appareil Teams Android user@contoso.com connecté.

Si vous utilisez l’accès conditionnel, qui nécessite l’application de l’inscription Intune, vous devez configurer deux éléments pour permettre le succès de votre inscription Intune :

- **Licence Intune** L’utilisateur qui se Teams l’appareil doit être titulaire d’une licence pour Intune.  Tant que l’appareil Teams est connecté à un compte d’utilisateur dispose d’une licence Intune valide, l’appareil est automatiquement inscrit à Microsoft Intune dans le cadre du processus de inscription.
- **Configurer Intune** Un client Intune correctement configuré doit être configuré pour l’inscription administrateur d’appareils Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurer Intune pour qu’il s’Teams appareils Android

Teams Les appareils Android sont gérés par intune via la gestion des administrateurs d’appareils Android. Pour que les appareils soient inscrits à Intune, il existe quelques étapes de base à suivre.  Si vous gérez déjà des appareils avec Intune, vous avez probablement déjà effectué toutes ces choses.  Si ce n’est pas le cas, voici comment faire :

1. Définissez Intune MDM (mobile device management) Authority.  Si vous n’êtes jamais utilisé dans Intune auparavant, vous devez définir l’autorité de gestion des périphériques mobiles avant de pouvoir inscrire des appareils. Pour plus d’informations, voir [Définir l’autorité de gestion des appareils mobiles.](/intune/fundamentals/mdm-authority-set)  Cette étape n’est à réaliser qu’une seule fois lors de la création d’un client Intune.
2. Activez l’inscription de l’administrateur d’appareils Android. Les appareils à base Teams Android sont gérés en tant qu’administrateurs d’appareils avec Intune.  L’inscription de l’administrateur de périphérique est par défaut non créditée pour les nouveaux locataires.  Pour plus d’informations, consultez [l’inscription des administrateurs d’appareils Android.](/intune/enrollment/android-enroll-device-administrator)
3. Attribuer des licences aux utilisateurs. Les utilisateurs Teams’appareils inscrits à Intune doivent se voir attribuer une licence Intune valide. Pour plus d’informations, voir Attribuer des licences aux utilisateurs afin qu’ils peuvent [inscrire des appareils dans Intune.](/intune/fundamentals/licenses-assign)
4. Attribuer des stratégies de conformité d’administrateur d’appareils.  Créez une stratégie de conformité d’administrateur d’appareil Android et attribuez-la au groupe Azure Active Directory qui contient les utilisateurs qui vont se Teams appareils mobiles. Pour plus d’informations, voir Utiliser des stratégies de conformité pour définir des règles pour les appareils [que vous gérez avec Intune.](/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Voir aussi

[Téléphones pour Teams](phones-for-teams.md)

[Téléphones IP certifiés pour les Microsoft Teams](teams-ip-phones.md)

[Teams affiche](teams-displays.md)

[Gérer vos périphériques dans Teams](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)