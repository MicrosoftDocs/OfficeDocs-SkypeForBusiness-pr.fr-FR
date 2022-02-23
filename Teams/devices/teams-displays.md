---
title: Microsoft Teams s’affiche
ms.author: czawideh
author: cazawideh
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
description: Cet article fournit une vue d’ensemble des fonctionnalités qui sont Microsoft Teams aux affichages.
ms.openlocfilehash: 8c8004edd12042ca27e77e545f23b8770f8d1899
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926327"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams s’affiche

Microsoft Teams’affichage sont une catégorie d’appareils Teams dédiés tout-en-un qui offrent un écran tactile connecté et une expérience mains libres optimisée par Cortana. Cet article donne une vue d’Teams présentation des affichages et peut vous aider à planifier, livrer et gérer Teams présentations dans votre organisation.

Teams affiche tous vos fichiers préférés Teams FeaturesChat&ndash;, vos réunions, vos appels,&ndash; votre calendrier et vos fichiers sur un seul appareil. Avec Teams' affichages, les utilisateurs peuvent utiliser un microphone, une caméra et des haut-parleurs (ou un casque Bluetooth) pour appeler et rencontrer des utilisateurs de manière fiable. Teams s’intègre aux pc Windows des utilisateurs pour apporter une expérience compagne qui permet une interaction transparente entre les appareils.

Pour en savoir plus, consultez la [mise en Teams les affichages](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Fonctionnalités prise en charge par Teams’affichage

En plus des [fonctionnalités pris en charge par Teams](phones-for-teams.md#features-supported-by-teams-phones), les fonctionnalités suivantes sont propres aux Teams’affichage :

- **Les écrans dédiés pour Teams** les utilisateurs peuvent accéder à toutes les fonctionnalités essentielles Teams y compris la conversation, les réunions, les appels, les équipes et les canaux, les fichiers et plus encore.
- **Expérience ambiant** Les utilisateurs peuvent facilement garder le fil de leur travail grâce à des affichages toujours actifs et coup d’œil pour voir les activités et notifications importantes sans basculement vers le contexte sur leur appareil professionnel principal. Les utilisateurs peuvent également personnaliser Teams’affichage en personnalisant l’arrière-plan à l’aide des paramètres.
- Mains **libres avec Cortana** Les utilisateurs peuvent interagir avec les Teams s’affichent à l’aide de leur voix pour rejoindre et présenter facilement des réunions, dicter des réponses à une conversation Teams, consulter les informations du calendrier, etc.
- **Laisser une note sur l’écran de verrouillage** Les invités peuvent choisir de laisser des notes audio, vidéo et textuelles, et les utilisateurs peuvent consulter les notes laissés par les invités et voir qui est là.  

## <a name="required-licenses"></a>Licences requises

Teams licences peuvent être achetées dans le cadre d Microsoft 365 [et Office 365 abonnements](/office365/servicedescriptions/teams-service-description). Pour en savoir plus sur les licences requises pour utiliser Teams des écrans, consultez les appels vocaux et [vidéo avec Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Pour plus d’informations sur la façon de Teams, consultez [comment accéder à Microsoft Teams ?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Déploiement et Teams’affichage à l’aide d’Intune

Pour en savoir plus sur le déploiement d Teams’affichages à l’aide d’Intune, voir Déployer Teams [téléphones et Teams’affichages](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Gérer Teams les affichages dans votre organisation

Pour gérer vos Teams d’affichage, dans le panneau de navigation gauche du Centre Microsoft Teams d’administration, Teams **affiche.** À partir de cet écran, vous pouvez modifier le profil de configuration de l’appareil, gérer les mises à jour, redémarrer des appareils, ajouter et supprimer des balises d’appareil, et bien plus encore. Pour plus d’informations, [voir Gérer vos appareils dans Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurer la fonction de desking hot sur Teams’écran

Les utilisateurs de votre organisation peuvent réserver des espaces de travail temporaires à l’avance dans les Teams d’Outlook, ou à partir de l’appareil proprement dit. Lorsque la reconnaissance des informations d’identification est activée, les utilisateurs se connectent à Teams s’affichent avec leurs informations d’Microsoft 365 pour accéder à leurs réunions, conversations et fichiers. Lorsqu’il se dé connecte, toutes ses informations personnelles sont supprimées de l’appareil.

Pour commencer, vous devez acquérir des licences Salles Microsoft Teams Standard et créer des comptes de ressources pour chaque Teams affichée. [Consultez Déployer Salles Microsoft Teams avec d Office 365](../rooms/with-office-365.md) pour créer des comptes de ressources.

Après avoir créé des comptes de ressources, vous pouvez créer et affecter une stratégie pour activer l’accès au desserrage. Pour [en savoir plus, consultez New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) .

> [!IMPORTANT]
> Étant donné que Teams s’affiche avec la procédure de desserrage rapide dans les espaces de travail partagés par plusieurs personnes, les règles d’accès conditionnel et d’autres configurations d’identité, telles que l’authentification multifacteur, peuvent avoir un impact sur ces appareils et entraîner des problèmes de authentification. Pour obtenir des instructions sur la sécurisation des appareils partagés, voir Les meilleures pratiques [d’authentification pour Teams appareils Android partagés](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Mettre à niveau Teams téléphones portables vers Teams’affichage

Teams’affiche est l’évolution des Teams téléphones mobiles. Vous pouvez mettre à niveau Teams téléphones de votre organisation vers Teams’affichage à l’aide du Microsoft Teams d’administration. Cette option est disponible uniquement pour les téléphones qui supportent la mise à niveau vers Teams’affichages. Pour en savoir plus, voir [Mettre à Teams niveau vers Teams’affichage.](upgrade-phones-to-displays.md)

## <a name="see-also"></a>Voir aussi

[Présentation des Microsoft Teams présentation](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Téléphones pour Teams](phones-for-teams.md)

[Téléphones IP certifiés pour Microsoft Teams](teams-ip-phones.md)

[Mise à niveau de téléphones IP vers Teams’affichages](upgrade-phones-to-displays.md)

[Cortana’assistance vocale dans Teams](../cortana-in-teams.md)