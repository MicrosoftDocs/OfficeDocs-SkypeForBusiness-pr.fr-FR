---
title: Déploiement de l’affichage des téléphones et équipes d’équipe à l’aide de Intune
ms.author: v-lanac
author: lanachin
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
description: Cet article fournit une vue d’ensemble des fonctionnalités prises en charge par Microsoft Teams.
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787615"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Déploiement de l’affichage des téléphones et équipes d’équipe à l’aide de Intune

Cet article vous fournit une vue d’ensemble du déploiement des téléphones et équipes teams dans Intune.

## <a name="conditional-access"></a>Accès conditionnel

L’accès conditionnel est une fonctionnalité d’Azure Active Directory (Azure AD) qui vous permet de garantir que les appareils qui accèdent à vos ressources Office 365 sont correctement gérés et sont sécurisés.  Si vous appliquez des stratégies d’accès conditionnel au service équipes, les appareils Android (y compris les numéros de téléphone et les équipes Teams) qui accèdent aux équipes doivent être inscrits dans Intune et leurs paramètres doivent être conformes à vos stratégies.  Si l’appareil n’est pas inscrit dans Intune ou s’il est inscrit alors que ses paramètres ne sont pas conformes à vos stratégies, l’accès conditionnel empêche un utilisateur de se connecter à l’application teams sur l’appareil ou d’utiliser celle-ci.

Les stratégies de conformité définies dans Intune sont généralement affectées à des groupes d’utilisateurs.  Cela signifie que si vous attribuez une stratégie de conformité Android à user@contoso.com, celle-ci s’applique également à son smartphone Android et à tout appareil d’équipe Android sur lequel user@contoso.com se connecte.

Si vous utilisez l’accès conditionnel, qui nécessite l’inscription de Intune, au sein de votre organisation, vous devez configurer les éléments suivants pour permettre à l’inscription Intune réussie de :

- **Licence Intune** L’utilisateur qui se connecte à l’appareil teams doit être titulaire d’une licence pour Intune.  Tant que l’appareil teams est connecté à un compte d’utilisateur disposant d’une licence Intune valide, ce dernier sera automatiquement inscrit à Microsoft Intune dans le cadre du processus de connexion.
- **Configurer Intune** Un client Intune correctement configuré doit être configuré pour l’inscription de l’administrateur de l’appareil Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurer Intune pour inscrire des appareils sur Android teams

Les appareils Android en équipe sont gérés par le biais de Intune via la gestion de l’administrateur de périphériques Android (DA). Pour que les appareils puissent être inscrits dans Intune, vous devez effectuer les opérations de base suivantes.  Si vous gérez déjà des appareils avec Intune dès aujourd’hui, vous avez sans doute déjà réalisé ces éléments.  Si ce n’est pas le cas, procédez comme suit :

1. Définissez le service Intune GPM (gestion des appareils mobiles).  Si vous n’avez jamais utilisé Intune auparavant, vous devez définir l’administration de la gestion des périphériques mobiles avant de pouvoir inscrire des appareils. Pour plus d’informations, reportez-vous à [la rubrique définition de l’autorité de gestion des appareils mobiles](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).  Il s’agit d’une étape ponctuelle qui doit être exécutée lors de la création d’un client Intune.
2. Activez l’inscription de l’administrateur de l’appareil Android. Les appareils d’équipe Android sont gérés en tant qu’appareils d’administration d’appareils avec Intune.  Par défaut, l’inscription de l’administrateur de l’appareil est désdésactivée pour les clients nouvellement créés.  Pour plus d’informations, reportez-vous à la rubrique inscription de l' [administrateur de périphériques Android](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).
3. Attribution de licences à des utilisateurs. Les utilisateurs des appareils d’équipe qui s’inscrivent à Intune doivent avoir reçu une licence Intune valide. Pour plus d’informations, consultez [attribuer des licences aux utilisateurs afin qu’ils puissent inscrire des appareils dans Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).
4. Attribution de stratégies de conformité de l’administrateur de périphériques.  Créez une stratégie de conformité de l’administrateur de périphériques Android et attribuez-la au groupe Azure Active Directory qui contient les utilisateurs qui se connecteront aux appareils Teams. Pour plus d’informations, reportez-vous [à utiliser des stratégies de conformité pour définir des règles pour les appareils que vous gérez avec Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Voir aussi

[Téléphones pour Teams](phones-for-teams.md)

[Téléphones IP certifiés pour Microsoft teams](teams-ip-phones.md)

[Teams s’affiche](teams-displays.md)

[Gérer vos périphériques dans Teams](device-management.md)

[Marketplace teams](https://office.com/teamsdevices)
