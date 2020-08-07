---
title: Téléphones pour Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: kponnus
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Cet article présente la liste des téléphones certifiés pour Microsoft teams ainsi que les fonctionnalités prises en charge par les téléphones certifiés pour Microsoft Teams.
ms.openlocfilehash: b017e02b2d3d2bdc6b01886929d034abb6650384
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583953"
---
# <a name="phones-for-microsoft-teams"></a>Téléphones pour Microsoft Teams

Microsoft teams prend en charge un portefeuille de téléphones de bureau pour les utilisateurs qui ont besoin d’une interface téléphonique classique. Cet article fournit une vue d’ensemble complète des téléphones et peut vous aider à planifier, livrer et gérer des téléphones Microsoft teams dans le cadre de votre solution de système téléphonique Microsoft. 

Pour proposer une utilisation fiable de Microsoft teams sur des téléphones, nous nous efforçons de vous aider à Yealink, Crestron, Lenovo, Polycom et AudioCodes à développer et à certifier un large éventail de téléphones de bureau et de salles de conférence. Pour obtenir les dernières informations et informations à jour sur les appareils Teams, accédez à [teams Marketplace](https://office.com/teamsdevices).

## <a name="features-supported-by-teams-phones"></a>Fonctionnalités prises en charge par les téléphones teams
Les téléphones certifiés pour les équipes disposent d’une vaste gamme de fonctionnalités qui permettent à vos utilisateurs de faire leur travail et de vous aider à gérer leur utilisation. Vous trouverez ci-dessous un résumé des fonctionnalités disponibles dans les téléphones certifiés par Microsoft teams :

- **Authentification** Le téléphone utilise l’authentification moderne pour simplifier la connexion et améliorer la sécurité. Les utilisateurs peuvent se connecter en entrant leur nom d’utilisateur et leur mot de passe sur le téléphone ou en vous connectant à partir d’un autre appareil, tel que PC/smartphone.
- **Historique rapide et historique des appels** Les utilisateurs ont un accès rapide à leurs contacts, l’historique des appels et la messagerie vocale. Ils peuvent facilement gérer leurs contacts et composer des numéros abrégés directement depuis leur téléphone.
- **Réunions et appels** Les utilisateurs peuvent consulter leur planning et participer facilement à des réunions à l’aide de la fonction de participation en un clic d’équipes.
- **Groupes d’appels** Les agents de téléphone qui participent aux groupes d’appels peuvent facilement gérer leur disponibilité et accepter ou refuser les appels entrants à partir de la file d’attente d’appels.
- **Délégation utilisateur** Les administrateurs et les responsables de la direction peuvent gérer les téléphones de leurs dirigeants et intercepter les appels entrants ; passer des appels pour le compte du responsable ; Prenez les appels mis en attente par le dirigeant. et déterminez si le responsable d’un appel est en attente, etc.
- **Bureau à chaud** Les utilisateurs peuvent obtenir leurs contacts, réunions et autres préférences en vous connectant à un téléphone. Lorsqu’il a terminé, il peut se déconnecter et laisser le téléphone prêt pour l’utilisateur suivant.
- **Vidéo** Les téléphones dotés d’une prise en charge vidéo permettent aux utilisateurs de participer à des conférences téléphoniques et des conférences vidéo comme sur leur ordinateur. Les utilisateurs peuvent rester en sécurité en utilisant le obturateur de l’appareil photo du téléphone et le commutateur de coupure du micro, le cas échéant.
- **Ensemble** Les téléphones peuvent être verrouillés et déverrouillés d’une manière intégrée lorsque vous êtes connecté à un PC Windows exécutant un client de bureau 64.
- **Accessibilité** Les téléphones sont dotés de plusieurs fonctionnalités d’accessibilité, telles que du texte à contraste élevé, qui permettent à quiconque de les utiliser plus facilement.
- **Support dynamique et amélioré E911** Les utilisateurs connectés qui appellent 911 verront leur emplacement sur le téléphone. 
    > [!IMPORTANT]
    > Si votre téléphone n’est pas connecté, ou s’il ne dispose pas d’une connexion Internet, les appels 911 ne peuvent pas être placés. Si tel est le cas, une notification s’affiche sur le téléphone.

Outre les fonctionnalités ci-dessus, vous pouvez contrôler les fonctionnalités disponibles en fonction du type de licence et de la stratégie de téléphone qui sont attribuées à l’utilisateur qui se connecte au téléphone. Par exemple, les utilisateurs qui se connectent à un téléphone avec leur compte personnel peuvent accéder à la gamme complète de fonctions (appels, réunions, messages vocaux, etc.). Le compte affecté d’une licence de téléphone commune qui se connecte à un téléphone est toutefois susceptible d’avoir accès à un large éventail de fonctions. l’historique des appels et le planning des réunions ne peuvent pas être conservés (par exemple, pour protéger la confidentialité des utilisateurs).

## <a name="required-licenses"></a>Licences requises

Les licences Microsoft teams peuvent être achetées dans le cadre de leurs [abonnements microsoft 365 et Office 365](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description). Pour en savoir plus sur les licences requises pour l’utilisation de Microsoft teams sur des téléphones, voir [licences de système téléphonique](https://products.office.com/microsoft-teams/voice-calling)disponibles.

Pour plus d’informations sur l'obtention de Teams, consultez [Comment obtenir l’accès à Microsoft Teams ?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-your-phones-via-intune"></a>Déploiement de votre téléphone via Intune

### <a name="conditional-access"></a>Accès conditionnel

L’accès conditionnel est une fonctionnalité d’Azure Active Directory qui vous permet de garantir que les appareils qui accèdent à vos ressources Office 365 sont correctement gérés et sont sécurisés.  Si vous appliquez des stratégies d’accès conditionnel au service Teams, alors les appareils Android (y compris ceux d’équipes) qui accèdent à des équipes doivent être inscrits dans Intune et leurs paramètres doivent être conformes à vos stratégies.  Si l’appareil n’est pas inscrit dans Intune ou s’il est inscrit alors que ses paramètres ne sont pas conformes à vos stratégies, l’accès conditionnel empêche un utilisateur de se connecter à l’application teams sur l’appareil ou à l’aide de celle-ci.

Les stratégies de conformité définies dans Intune sont généralement affectées à des groupes d’utilisateurs.  Cela signifie que si vous attribuez une stratégie de conformité Android à user@contoso.com, celle-ci s’applique également à son smartphone Android et à tout appareil d’équipe Android sur lequel user@contoso.com se connecte.

Si vous utilisez l’accès conditionnel, qui nécessite l’inscription de Intune, au sein de votre organisation, vous devez configurer les éléments suivants pour permettre à l’inscription Intune réussie de :

- **Licence Intune** L’utilisateur qui se connecte au téléphone Microsoft teams doit être titulaire d’une licence pour Intune.  Tant que les téléphones de Microsoft teams sont connectés à un compte d’utilisateur disposant d’une licence Intune valide, le téléphone sera inscrit automatiquement dans Microsoft Intune dans le cadre du processus de connexion.
- **Configurer Intune** Un client Intune correctement configuré doit être configuré pour l’inscription de l’administrateur de l’appareil Android.

### <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Configurer Intune pour inscrire des appareils sur Android teams

Les appareils Android en équipe sont gérés par le biais de Intune via la gestion de l’administrateur de périphériques Android (DA). Pour que les appareils puissent être inscrits dans Intune, vous devez effectuer les opérations de base suivantes.  Si vous gérez déjà des appareils avec Intune dès aujourd’hui, vous avez sans doute déjà réalisé ces éléments.  Si ce n’est pas le cas, procédez comme suit :

1. Définissez le service Intune GPM (gestion des appareils mobiles).  Si vous n’avez jamais utilisé Intune auparavant, vous devez définir l’administration de la gestion des périphériques mobiles avant de pouvoir inscrire des appareils. Pour plus d’informations, reportez-vous à [la rubrique définition de l’autorité de gestion des appareils mobiles](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).  Il s’agit d’une étape ponctuelle qui doit être exécutée lors de la création d’un client Intune.
2. Activez l’inscription de l’administrateur de l’appareil Android. Les appareils d’équipe Android sont gérés en tant qu’appareils d’administration d’appareils avec Intune.  Par défaut, l’inscription de l’administrateur de l’appareil est désdésactivée pour les clients nouvellement créés.  Pour plus d’informations, reportez-vous à la rubrique inscription de l' [administrateur de périphériques Android](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).
3. Attribution de licences à des utilisateurs. Les utilisateurs des appareils d’équipe qui s’inscrivent à Intune doivent avoir reçu une licence Intune valide. Pour plus d’informations, consultez [attribuer des licences aux utilisateurs afin qu’ils puissent inscrire des appareils dans Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).
4. Attribution de stratégies de conformité de l’administrateur de périphériques.  Créez une stratégie de conformité de l’administrateur de périphériques Android et attribuez-la au groupe Azure Active Directory qui contient les utilisateurs qui se connecteront aux appareils Teams. Pour plus d’informations, reportez-vous [à utiliser des stratégies de conformité pour définir des règles pour les appareils que vous gérez avec Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).

## <a name="manage-your-phones"></a>Gérer vos téléphones

Le centre d’administration teams permet à un administrateur client de gérer et de mettre à jour tous les périphériques de ses équipes. Pour plus d’informations, voir [gérer vos appareils dans Microsoft teams](https://docs.microsoft.com/microsoftteams/devices/device-management). 

## <a name="see-also"></a>Voir aussi

[Marketplace teams](https://office.com/teamsdevices)

[Téléphones IP certifiés pour Microsoft teams](teams-ip-phones.md)
