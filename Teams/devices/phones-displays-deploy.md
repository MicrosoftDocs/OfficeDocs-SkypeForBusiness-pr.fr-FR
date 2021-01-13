---
title: Déployer les téléphones et les affichages Teams à l’aide d’Intune
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
description: Cet article fournit une vue d’ensemble des fonctionnalités qui sont pris en charge par les affichages Microsoft Teams.
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825414"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Déployer les téléphones et les affichages Teams à l’aide d’Intune

Cet article vous donne une vue d’ensemble du déploiement des téléphones et des affichages Teams à l’aide d’Intune.

## <a name="conditional-access"></a>Accès conditionnel

L’accès conditionnel est une fonctionnalité d’Azure Active Directory (Azure AD) qui vous permet de vous assurer que les appareils qui accèdent à vos ressources Office 365 sont correctement gérés et sécurisés.  Si vous appliquez des stratégies d’accès conditionnel au service Teams, les appareils Android (y compris les téléphones Et les affichages Teams) qui accèdent à Teams doivent être inscrits à Intune et leurs paramètres doivent respecter vos stratégies.  Si l’appareil n’est pas inscrit à Intune, ou s’il est inscrit mais que ses paramètres ne respectent pas vos stratégies, l’accès conditionnel empêche un utilisateur de se connecté à l’application Teams ou d’utiliser l’application Teams sur l’appareil.

En règle générale, les stratégies de conformité définies dans Intune sont affectées à des groupes d’utilisateurs.  Cela signifie que si vous affectez une politique de conformité Android à user@contoso.com, cette stratégie s’appliquera de façon égale à leur smartphone Android et à tout appareil Teams Android sur user@contoso.com connecté.

Si vous utilisez l’accès conditionnel, qui nécessite l’application de l’inscription Intune, vous devez configurer deux éléments pour permettre la réussite de votre inscription Intune :

- **Licence Intune** L’utilisateur qui se connecté à l’appareil Teams doit être titulaire d’une licence pour Intune.  Tant que l’appareil Teams est connecté à un compte d’utilisateur dispose d’une licence Intune valide, l’appareil est automatiquement inscrit à Microsoft Intune dans le cadre du processus de inscription.
- **Configurer Intune** Un client Intune correctement configuré doit être configuré pour l’inscription administrateur d’appareils Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurer Intune pour inscrire des appareils Teams sur Android

Les appareils Teams sur Android sont gérés dans Intune via la gestion de l’administrateur d’appareils Android (DA). Pour que les appareils soient inscrits à Intune, il existe quelques étapes de base à suivre.  Si vous gérez déjà des appareils avec Intune, vous avez probablement déjà effectué toutes ces choses.  Si ce n’est pas le cas, voici comment faire :

1. Définissez Intune MDM (mobile device management) Authority.  Si vous n’avez jamais utilisé Intune auparavant, vous devez définir l’autorité de gestion des périphériques mobiles avant de pouvoir inscrire des appareils. Pour plus d’informations, voir [Définir l’autorité de gestion des appareils mobiles.](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)  Cette étape n’est à réaliser qu’une seule fois lors de la création d’un client Intune.
2. Activez l’inscription de l’administrateur d’appareils Android. Les appareils Teams android sont gérés en tant qu’appareils d’administrateur d’appareils avec Intune.  L’inscription de l’administrateur de périphérique est par défaut non créditée pour les nouveaux locataires.  Pour plus d’informations, consultez [l’inscription de l’administrateur d’appareils Android.](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)
3. Attribuer des licences aux utilisateurs. Une licence Intune valide doit être attribuée aux utilisateurs d’appareils Teams s’inscrivant à Intune. Pour plus d’informations, voir Attribuer des licences aux utilisateurs afin qu’ils peuvent [inscrire des appareils dans Intune.](https://docs.microsoft.com/intune/fundamentals/licenses-assign)
4. Attribuer des stratégies de conformité d’administrateur d’appareils.  Créez une stratégie de conformité de l’administrateur d’appareils Android et attribuez-la au groupe Azure Active Directory qui contient les utilisateurs qui se seront connectés aux appareils Teams. Pour plus d’informations, voir Utiliser des stratégies de conformité pour définir des règles pour les appareils [que vous gérez avec Intune.](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)

## <a name="see-also"></a>Voir aussi

[Téléphones pour Teams](phones-for-teams.md)

[Téléphones IP certifiés pour Microsoft Teams](teams-ip-phones.md)

[Teams s’affiche](teams-displays.md)

[Gérer vos périphériques dans Teams](device-management.md)

[Place de marché Teams](https://office.com/teamsdevices)
