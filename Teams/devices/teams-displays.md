---
title: Microsoft Teams s’affiche
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: Cet article fournit une vue d’ensemble des fonctionnalités prises en charge par les affichages Microsoft Teams.
ms.openlocfilehash: 18b8219a3eef391170c7321ae994d79f1b73f016
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268769"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams s’affiche

Les affichages Microsoft Teams sont une catégorie d’appareils Teams dédiés tout-en-un qui disposent d’un écran tactile ambiant et d’une expérience mains libres optimisée par Cortana. Cet article fournit une vue d’ensemble des affichages Teams et peut vous aider à planifier, fournir et gérer des affichages Teams dans votre organisation.

Les affichages Teams regroupent vos fonctionnalités Teams favorites&ndash;conversation, réunions, appels, calendrier et fichiers&ndash;dans un seul appareil. Avec les affichages Teams, les utilisateurs peuvent utiliser un microphone, une caméra et des haut-parleurs (ou un casque Bluetooth) pour une expérience d’appel et de réunion fiable. Les affichages Teams s’intègrent aux PC Windows des utilisateurs pour offrir une expérience complémentaire qui permet une interaction fluide entre appareils.

Pour en savoir plus, consultez [Prise en main des affichages Teams](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Fonctionnalités prises en charge par les affichages Teams

Outre les [fonctionnalités prises en charge par les téléphones Teams](phones-for-teams.md#features-supported-by-teams-phones), les fonctionnalités suivantes sont propres aux affichages Teams :

- **Affichages dédiés pour Teams** Les utilisateurs peuvent accéder à toutes les fonctionnalités principales de Teams, notamment la conversation, les réunions, les appels, les équipes et les canaux, les fichiers, etc.
- **Expérience ambiante** Les utilisateurs peuvent facilement rester informés de leur travail avec des affichages toujours actifs et accessibles en un clin d’œil pour voir les activités et les notifications importantes sans changement de contexte sur leur appareil de travail principal. Les utilisateurs peuvent également personnaliser les affichages Teams en personnalisant l’arrière-plan via les paramètres.
- **Mains libres avec Cortana** Les utilisateurs peuvent interagir avec les affichages Teams à l’aide de leur voix pour participer facilement aux réunions et les présenter, dicter des réponses à une conversation Teams, vérifier ce qui se trouve dans le calendrier, etc.
- **Laisser une note sur l’écran de verrouillage** Les invités peuvent choisir de laisser des notes audio, vidéo et texte, et les utilisateurs peuvent vérifier les notes laissées par les invités et voir qui est arrêté par.  

## <a name="required-licenses"></a>Licences requises

Les licences Teams peuvent être achetées dans le cadre des [abonnements Microsoft 365 et Office 365](/office365/servicedescriptions/teams-service-description). Pour en savoir plus sur les licences requises pour utiliser les affichages Teams, consultez [l’appel vocal et vidéo avec Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Pour plus d’informations sur la façon d’obtenir Teams, consultez [Comment faire accéder à Microsoft Teams ?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Déployer des affichages Teams à l’aide de Intune

Pour en savoir plus sur le déploiement d’affichages Teams à l’aide de Intune, consultez [Déployer des téléphones Teams et des affichages Teams](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Gérer les affichages Teams dans votre organisation

Pour gérer vos appareils d’affichage Teams, dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **affichages Teams**. À partir de là, vous pouvez modifier le profil de configuration de l’appareil, gérer les mises à jour, redémarrer des appareils, ajouter et supprimer des balises d’appareil, etc. Pour plus d’informations, consultez [Gérer vos appareils dans Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurer le desking à chaud sur les affichages Teams

Le desking à chaud permet aux membres de votre organisation de réserver des espaces de travail temporaires à l’avance via Teams et Outlook, ou à partir de l’appareil lui-même. Lorsque le desking à chaud est activé, les utilisateurs se connectent aux affichages Teams avec leurs informations d’identification Microsoft 365 pour accéder à leurs réunions, conversations et fichiers. Lorsqu’ils se déconnectent, toutes leurs informations personnelles sont supprimées de l’appareil.

Pour commencer, vous devez acquérir des licences Salles Microsoft Teams Standard et créer des comptes de ressources pour chaque affichage Teams. Consultez [Créer des comptes de ressources pour les salles et les appareils Teams partagés](../rooms/with-office-365.md) pour créer des comptes de ressources.

Après avoir créé des comptes de ressources, vous pouvez créer et affecter une stratégie pour activer le desking à chaud. Pour en savoir plus, consultez [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) .

> [!IMPORTANT]
> Étant donné que les affichages Teams avec desking à chaud sont utilisés dans des espaces de travail partagés par plusieurs personnes, les règles d’accès conditionnel et d’autres configurations d’identité dans votre environnement, telles que Multi-Factor Authentication, peuvent avoir un impact sur ces appareils et entraîner des problèmes de connexion. Pour obtenir des conseils sur la sécurisation des appareils partagés, consultez les [meilleures pratiques d’authentification pour les appareils Android Teams partagés](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Mettre à niveau les téléphones Teams vers les affichages Teams

Les affichages Teams sont l’évolution des téléphones Teams. Vous pouvez mettre à niveau les téléphones Teams de votre organisation vers des affichages Teams à l’aide du Centre d’administration Microsoft Teams. Cette option est disponible uniquement pour les téléphones qui prennent en charge la mise à niveau vers les affichages Teams. Pour plus d’informations, consultez [Mettre à niveau les téléphones Teams vers Teams](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Voir aussi

[Présentation des affichages Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Place de marché Teams](https://office.com/teamsdevices)

[Téléphones pour Teams](phones-for-teams.md)

[Téléphones IP certifiés pour Microsoft Teams](teams-ip-phones.md)

[Mettre à niveau les téléphones IP vers les affichages Teams](upgrade-phones-to-displays.md)

[Assistance vocale Cortana dans Teams](../cortana-in-teams.md)