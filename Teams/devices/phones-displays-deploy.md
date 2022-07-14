---
title: Déployer des téléphones Teams, des écrans Teams, des panneaux Teams et des Salles Microsoft Teams sur Android à l’aide de Intune
author: CarolynRowe
ms.author: crowe
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
description: Cet article fournit une vue d’ensemble des fonctionnalités prises en charge par les appareils Android Microsoft Teams.
ms.openlocfilehash: 5522c29c74eb9679d26d13627dcb69b315dc33fd
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790309"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Déployer des téléphones Teams, des écrans Teams, des panneaux Teams et des Salles Microsoft Teams sur Android à l’aide de Intune

Cet article vous donne une vue d’ensemble du déploiement de téléphones Teams, d’affichages Teams, de panneaux Teams et de Salles Microsoft Teams sur Android à l’aide de Intune.

## <a name="conditional-access"></a>Accès conditionnel

L’accès conditionnel est une fonctionnalité Azure Active Directory (Azure AD) qui vous permet de garantir que les appareils qui accèdent à vos ressources Office 365 sont correctement gérés et sécurisés.  Si vous appliquez des stratégies d’accès conditionnel au service Teams, aux appareils Android (y compris les téléphones Teams, les écrans Teams, les panneaux Teams et Salles Microsoft Teams sur Android) qui accèdent à Teams doivent être inscrits dans Intune et leurs paramètres doivent être conformes à vos stratégies.  Si l’appareil n’est pas inscrit dans Intune, ou s’il est inscrit mais que ses paramètres ne sont pas conformes à vos stratégies, l’accès conditionnel empêche un utilisateur de se connecter à l’application Teams ou de l’utiliser sur l’appareil.

En règle générale, les stratégies de conformité définies dans Intune sont affectées à des groupes d’utilisateurs.  Cela signifie que si vous attribuez une stratégie de conformité Android à user@contoso.com, cette stratégie s’applique également à son smartphone Android et à tout appareil Teams Android dans lequel user@contoso.com se connecte.

Si vous utilisez l’accès conditionnel, qui nécessite l’application de Intune inscription, dans votre organisation, vous devez configurer quelques éléments pour permettre une inscription Intune réussie :

- **Intune licence** L’utilisateur qui se connecte à l’appareil Teams doit disposer d’une licence pour Intune.  Tant que l’appareil Teams est connecté à un compte d’utilisateur disposant d’une licence Intune valide, l’appareil est automatiquement inscrit dans Microsoft Intune dans le cadre du processus de connexion.
- **Configurez Intune** Vous devez disposer d’un locataire Intune configuré correctement pour l’inscription d’administrateur d’appareil Android.

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurer Intune pour inscrire des appareils Android Teams

Les appareils Android Teams sont gérés par Intune via la gestion de l’administrateur d’appareils Android (DA). Avant que les appareils puissent être inscrits dans Intune, vous devez effectuer quelques étapes de base.  Si vous gérez déjà des appareils avec Intune aujourd’hui, vous avez probablement déjà fait toutes ces choses.  Si ce n’est pas le cas, voici ce qu’il faut faire :

> [!NOTE]
> - Si les administrateurs de locataires souhaitent que les téléphones communs soient inscrits dans Intune, ils doivent ajouter une licence Intune au compte et suivre les étapes de Intune’inscription.
> - Si le compte d’utilisateur utilisé pour se connecter à un appareil Teams n’est pas sous licence pour Intune, Intune stratégies de conformité et les restrictions d’inscription doivent être désactivées pour le compte.



1. Définissez Intune autorité MDM (gestion des appareils mobiles).  

   Si vous n’avez jamais utilisé Intune auparavant, vous devez définir l’autorité MDM avant de pouvoir inscrire des appareils. Pour plus d’informations, consultez [Définir l’autorité de gestion des appareils mobiles](/intune/fundamentals/mdm-authority-set).  Il s’agit d’une étape unique qui doit être effectuée lors de la création d’un locataire Intune.
1. Activez l’inscription de l’administrateur d’appareils Android.
  
   Les appareils Teams android sont gérés en tant qu’appareils d’administrateur d’appareils avec Intune.  L’inscription de l’administrateur d’appareil est désactivée par défaut pour les locataires nouvellement créés. Consultez [l’inscription de l’administrateur d’appareil Android](/intune/enrollment/android-enroll-device-administrator).
1. Attribuez des licences aux utilisateurs. 
 
   Les utilisateurs d’appareils Teams qui s’inscrivent à Intune doivent se voir attribuer une licence Intune valide. Pour plus d’informations, consultez [Affecter des licences aux utilisateurs afin qu’ils puissent inscrire des appareils dans Intune](/intune/fundamentals/licenses-assign).
1. Attribuez des stratégies de conformité à l’administrateur d’appareils.  

   1. Créez une stratégie de conformité d’administrateur d’appareil Android.

   1. Affectez-le au groupe Azure Active Directory qui contient les utilisateurs qui se connectent aux appareils Teams. Consultez [Utiliser des stratégies de conformité pour définir des règles pour les appareils que vous gérez avec Intune](/mem/intune/protect/device-compliance-get-started).

## <a name="see-also"></a>Voir aussi

[Téléphones pour Teams](phones-for-teams.md)

[Téléphones IP certifiés pour Microsoft Teams](teams-ip-phones.md)

[Affichages Teams](teams-displays.md)

[Gérer vos périphériques dans Teams](device-management.md)

[Place de marché Teams](https://office.com/teamsdevices)
