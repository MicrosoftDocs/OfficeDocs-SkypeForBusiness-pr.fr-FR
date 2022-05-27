---
title: Déployez des téléphones Teams, des écrans Teams, des panneaux Teams et des Salles Microsoft Teams sur Android à l’aide de Intune
ms.author: serdars
author: SerdarSoysal
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
ms.localizationpriority: medium
description: Cet article fournit une vue d’ensemble des fonctionnalités prises en charge par Microsoft Teams Android appareils.
ms.openlocfilehash: 17f5e537b44d3aacd967ff5e8ffaa84df9da3f9b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674856"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Déployez des téléphones Teams, des écrans Teams, des panneaux Teams et des Salles Microsoft Teams sur Android à l’aide de Intune

Cet article vous donne une vue d’ensemble du déploiement de téléphones Teams, d’affichages Teams, de panneaux Teams et de Salles Microsoft Teams sur Android à l’aide de Intune.

## <a name="conditional-access"></a>Accès conditionnel

L’accès conditionnel est une fonctionnalité Azure Active Directory (Azure AD) qui vous permet de vous assurer que les appareils qui accèdent à vos ressources Office 365 sont correctement gérés et sécurisés.  Si vous appliquez des stratégies d’accès conditionnel au service Teams, Android des appareils (notamment des téléphones Teams, des écrans Teams, des panneaux Teams et des Salles Microsoft Teams sur Android) dans lesquels l’accès Teams doit être inscrit Intune et leurs paramètres doivent respecter vos stratégies.  Si l’appareil n’est pas inscrit dans Intune, ou s’il est inscrit mais que ses paramètres ne sont pas conformes à vos stratégies, l’accès conditionnel empêche un utilisateur de se connecter à l’application Teams ou de l’utiliser sur l’appareil.

En règle générale, les stratégies de conformité définies dans Intune sont affectées à des groupes d’utilisateurs.  Cela signifie que si vous attribuez une stratégie de conformité Android à user@contoso.com, cette stratégie s’applique également à son smartphone Android et à tout appareil Teams basé sur Android qui user@contoso.com se connecte.

Si vous utilisez l’accès conditionnel, qui nécessite l’application de Intune inscription, dans votre organisation, vous devez configurer quelques éléments pour permettre une inscription Intune réussie :

- **Intune licence** L’utilisateur qui se connecte à l’appareil Teams doit disposer d’une licence pour Intune.  Tant que l’appareil Teams est connecté à un compte d’utilisateur disposant d’une licence Intune valide, l’appareil est automatiquement inscrit dans Microsoft Intune dans le cadre du processus de connexion.
- **Configurez Intune** Vous devez disposer d’un locataire Intune correctement configuré pour l’inscription Android Administrateur d’appareil.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurer Intune pour inscrire des appareils basés sur Teams Android

les appareils basés sur Teams Android sont gérés par Intune via Android gestion de l’administrateur d’appareil (DA). Avant que les appareils puissent être inscrits dans Intune, vous devez effectuer quelques étapes de base.  Si vous gérez déjà des appareils avec Intune aujourd’hui, vous avez probablement déjà fait toutes ces choses.  Si ce n’est pas le cas, voici ce qu’il faut faire :

> [!NOTE]
> - Si les administrateurs de locataires souhaitent que les téléphones communs soient inscrits dans Intune, ils doivent ajouter une licence Intune au compte et suivre les étapes de Intune’inscription.
> - Si le compte d’utilisateur utilisé pour se connecter à un appareil Teams n’est pas sous licence pour Intune, Intune stratégies de conformité et restrictions d’inscription doivent être désactivées pour le compte.



1. Définissez Intune autorité MDM (gestion des appareils mobiles).  

   Si vous n’avez jamais utilisé Intune auparavant, vous devez définir l’autorité MDM avant de pouvoir inscrire des appareils. Pour plus d’informations, consultez [Définir l’autorité de gestion des appareils mobiles](/intune/fundamentals/mdm-authority-set).  Il s’agit d’une étape unique qui doit être effectuée lors de la création d’un locataire Intune.
1. Activez Android’inscription de l’administrateur d’appareil.
  
   les appareils Teams basés sur Android sont gérés en tant qu’appareils d’administrateur d’appareils avec Intune.  L’inscription de l’administrateur d’appareil est désactivée par défaut pour les locataires nouvellement créés. Consultez [Android’inscription de l’administrateur d’appareil](/intune/enrollment/android-enroll-device-administrator).
1. Attribuez des licences aux utilisateurs. 
 
   Une licence de Intune valide doit être attribuée aux utilisateurs d’appareils Teams qui s’inscrivent à Intune. Pour plus d’informations, consultez [Affecter des licences aux utilisateurs afin qu’ils puissent inscrire des appareils dans Intune](/intune/fundamentals/licenses-assign).
1. Attribuez des stratégies de conformité à l’administrateur d’appareils.  

   1. Créez une stratégie de conformité Android Administrateur d’appareil.

   1. Affectez-le au groupe Azure Active Directory qui contient les utilisateurs qui se connectent aux appareils Teams. Consultez [Utiliser des stratégies de conformité pour définir des règles pour les appareils que vous gérez avec Intune](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Voir aussi

[Téléphones pour Teams](phones-for-teams.md)

[Téléphones IP certifiés pour Microsoft Teams](teams-ip-phones.md)

[Teams s’affiche](teams-displays.md)

[Gérer vos périphériques dans Teams](device-management.md)

[place de marché Teams](https://office.com/teamsdevices)
