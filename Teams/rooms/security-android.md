---
title: Sécurité de Microsoft Teams pour Android
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Découvrez comment sécuriser vos appareils Microsoft Teams pour Android.
ms.openlocfilehash: 6d17cc68af8ef4a879d5de3b17d27f20b281ddf8
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532434"
---
# <a name="microsoft-teams-for-android-security"></a>Sécurité de Microsoft Teams pour Android

Cet article ne couvre pas les appareils Android configurés pour le mode d’appareil dédié par Microsoft Endpoint Manager. Les appareils Android Teams s’exécutent en mode Plein écran par conception. Pour plus d’informations sur Android Kiosk, consultez [l’inscription d’appareils dédiés Android Enterprise](/mem/intune/enrollment/android-kiosk-enroll).

Microsoft travaille avec nos partenaires OEM pour fournir une solution sécurisée par conception et personnalisable pour répondre aux besoins des clients. Cet article décrit la plupart des fonctionnalités de sécurité disponibles dans les appareils Android Teams et notre approche. Il est divisé en quatre sections clés pour faciliter la navigation.

> [!NOTE]
> Les appareils Android Microsoft Teams ne doivent pas être traités comme un appareil Android classique. Les appareils Android Teams sont des appliances spécialement conçues pour être utilisées avec Teams et leurs cas d’utilisation respectifs. Cet article s’applique uniquement aux appareils Microsoft Teams certifiés et dédiés exécutant le système d’exploitation Android. Les appareils certifiés Teams peuvent uniquement être achetés auprès de fournisseurs OEM certifiés. Pour plus d’informations sur les appareils Android certifiés Microsoft Teams, consultez [les appareils Android certifiés Microsoft Teams](/microsoftteams/devices/teams-ip-phones).

Pour plus d’informations sur la sécurité sur salles Teams pour les appareils Windows, consultez [Salles Microsoft Teams pour la sécurité Windows](security-windows.md).

## <a name="software-security"></a>Sécurité logicielle

### <a name="android-kiosk-mode"></a>Mode plein écran Android

Les appareils Android Teams sont verrouillés pour exécuter uniquement les applications approuvées en exécutant l’appareil en mode Kiosque Android. Le mode plein écran désactive l’accès à toutes les fonctionnalités du lanceur et permet de sécuriser l’appareil afin que les applications autorisées soient lancées sur l’appareil.  

| Nom de l’application            | Description de l’application                   |
|-----------------------------|-------------------------------------------|
| Application Android Microsoft Teams | Application d’appareil Microsoft Teams        |
| Agent Administration Microsoft Teams | Gestion à distance du centre d’administration Teams      |
| Portail d'entreprise Intune       | Inscription d’appareil, inscription & connexion |
| OEM Partner Agent           | OEM Partner Agent & Device Settings App   |

Par défaut, l’application Android Microsoft Teams démarre en mode Plein écran Android et ne fournit à l’utilisateur aucun accès au système d’exploitation ni accès aux composants en dehors de l’expérience utilisateur Teams désignée.

### <a name="application-code-signing"></a>Signature de code d’application

Toutes les applications Microsoft et OEM sont signées par du code. La signature de code permet de valider que le logiciel s’exécutant sur un appareil est authentique auprès de Microsoft et de nos partenaires matériels. La signature de code tente également de valider l’intégrité du logiciel en cours d’exécution sur l’appareil, de sorte que seuls les logiciels authentiques peuvent être lancés et exécutés.  

### <a name="third-party-applications"></a>Applications tierces

Les appareils certifiés Teams n’ont pas le Google Play Store, Amazon App Store ou Google Play Services, installés par conception. Cela permet de s’assurer qu’aucune application tierce ne peut être installée à partir du magasin sur un appareil.  

### <a name="android-debug-bridge"></a>Pont de débogage Android

Le pont de débogage Android (ADB) est désactivé par conception sur tous les appareils Android Teams exécutant le logiciel de mise en production. ADB est un outil en ligne de commande qui permet aux administrateurs d’effectuer des fonctions sur des appareils Android et permet l’installation d’applications, l’accès à l’interpréteur de commandes de l’appareil et d’autres fonctions d’administration.  

### <a name="file-system-encryption"></a>Chiffrement du système de fichiers

Les appareils Android Teams doivent gérer le chiffrement android et peuvent être appliqués à l’aide de stratégies de conformité Microsoft Endpoint Manager. Pour plus d’informations sur Endpoint Manager stratégies de conformité[, utilisez Endpoint Manager stratégies de conformité pour définir des règles pour les appareils que vous gérez avec Intune](/mem/intune/protect/device-compliance-get-started).

### <a name="android-os-version"></a>Version du système d’exploitation Android

Les appareils Android Teams exécutent les versions prises en charge d’Android. Le système d’exploitation Android est géré par des partenaires OEM, fusionné dans le microprogramme certifié Teams, puis envoyé (push) aux appareils à partir du Centre d’administration Teams. Pour plus d’informations sur les versions Android qui s’exécutent sur les appareils Android Teams, consultez [les appareils Android certifiés Microsoft Teams](/microsoftteams/devices/teams-ip-phones).

### <a name="android-security-updates"></a>Mises à jour de sécurité Android

Les fournisseurs OEM, dans le cadre du processus de mise à jour du microprogramme, incorporent les bases de référence de mise à jour de sécurité Android appropriées pour garantir la sécurité du système d’exploitation de base. Il est important de maintenir régulièrement à jour vos appareils pour vous assurer que les mises à jour de sécurité Android appropriées sont en cours d’exécution sur vos appareils. Pour plus d’informations, reportez-vous au fabricant de votre appareil.

### <a name="account-security"></a>Sécurité du compte

Les appareils Android Teams sont créés autour de deux types de comptes qui permettent le bon fonctionnement d’un appareil.

- Compte d’administrateur d’appareil local

- Compte d’utilisateur ou de ressource  

Les appareils Android Teams sont également compatibles avec certaines stratégies d’accès conditionnel, qui peuvent être utilisées comme couches de sécurité supplémentaires pour la connexion des appareils. Pour connaître les meilleures pratiques et les stratégies d’accès conditionnel prises en charge, consultez [Stratégies de conformité d’accès conditionnel prises en charge](/microsoftteams/rooms/supported-ca-and-compliance-policies).

### <a name="local-device-administrator-account"></a>Compte d’administrateur d’appareil local

Les appareils Android Teams incluent un compte d’administration pour accéder aux paramètres de l’appareil, le serveur web local s’il est installé et tous les paramètres spécifiques OEM.

Les éléments de configuration et de configuration de l’appareil initiaux, tels que le nom d’utilisateur et le mot de passe par défaut pour ce compte, peuvent être obtenus auprès du fabricant de l’appareil.

> [!CAUTION]
> Veillez à modifier le mot de passe de l’administrateur d’appareil local dès que possible.  

> [!TIP]
> Le Centre d’administration Teams peut être utilisé pour modifier le mot de passe d’administrateur d’appareil local d’un appareil Android Teams connecté en appliquant un profil de configuration. Nous recommandons cette approche après la connexion initiale de l’appareil pour protéger les fonctionnalités élevées d’un appareil Android. Les fonctionnalités avec élévation de privilèges peuvent inclure des paramètres d’appareil et des portails d’administration web s’ils sont pris en charge.

### <a name="user-or-resource-account"></a>Compte d’utilisateur ou de ressource

Les appareils Android Teams nécessitent l’utilisation d’un utilisateur ou d’un compte de ressources dédié pour se connecter à Microsoft 365. Nous essayons de sécuriser ces comptes de manière spécifique, selon qu’il s’agit d’un compte d’utilisateur normal pour un appareil personnel ou d’un compte de ressource pour un appareil partagé. Pour plus d’informations, consultez [Créer et configurer des comptes de ressources pour les salles et les appareils partagés](/microsoftteams/rooms/with-office-365).

### <a name="device-updates"></a>Mises à jour des appareils

Les appareils Android Teams sont configurés pour télécharger les mises à jour certifiées Microsoft à partir du Centre d’administration Teams lorsqu’elles deviennent disponibles. Ceux-ci peuvent être envoyés automatiquement ou manuellement par un administrateur. Des outils tiers de nos partenaires OEM sont également disponibles pour effectuer cette fonction si nécessaire. Les appareils Android Teams peuvent installer des mises à jour après des heures afin d’éviter l’impact sur les utilisateurs. Les planifications après heures peuvent être configurées dans le Centre d’administration Teams ou à l’aide d’outils tiers de partenaires OEM.

> [!IMPORTANT]
> Microsoft recommande la gestion du microprogramme pour tous les appareils Android Teams via le Centre d’administration Teams.

## <a name="network-security"></a>Sécurité réseau

Les appareils Android Teams ont les mêmes exigences réseau que n’importe quel client Microsoft Teams, y compris l’accès via des pare-feu et d’autres appareils de sécurité. Plus précisément, les catégories répertoriées comme **requises** pour Teams doivent être ouvertes sur votre pare-feu, ainsi que sur d’autres services de prise en charge, comme indiqué ci-dessous. Pour obtenir la liste complète des adresses IP et URL requises pour les appareils Android Teams, consultez :

- Microsoft Teams, Exchange Online, SharePoint Online, Microsoft 365 Common et Office Online [Office 365 URL et plage d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)

- points de terminaison [réseau Microsoft Intune pour Microsoft Intune](/mem/intune/fundamentals/intune-endpoints)

Les appareils Android Teams fonctionnent avec la plupart des protocoles de sécurité 802.1X et d’autres protocoles de sécurité réseau. Toutefois, nous ne pouvons pas tester les appareils Android Teams sur toutes les configurations de sécurité réseau. Par conséquent, si des problèmes de performances peuvent être suivis de problèmes de performances réseau, vous devrez peut-être désactiver ces protocoles s’ils sont configurés dans votre organisation ou contacter votre partenaire OEM pour obtenir de l’aide.

Pour optimiser les performances des supports en temps réel, nous vous recommandons vivement de configurer le trafic multimédia Teams pour contourner les serveurs proxy et d’autres appareils de sécurité réseau. Le média en temps réel est sensible à la latence du réseau, qui peut être causée par des serveurs proxy et d’autres appareils de sécurité réseau. La latence du réseau peut dégrader considérablement la qualité vidéo et audio des utilisateurs. Pour plus d’informations, consultez [Mise en réseau (vers le cloud) : point de vue d’un architecte](/microsoft-365/solutions/networking-design-principles) qui traite des recommandations réseau pour améliorer les performances des médias avec Microsoft Teams.

Les appareils Android Teams utilisent des communications chiffrées et l’authentification de point de terminaison sur Internet. Les appareils Android Teams utilisent TLS 1.2+.  

> [!IMPORTANT]
> Les appareils Android Teams ne prennent pas en charge les serveurs proxy authentifiés ou les restrictions de locataire. Contactez votre partenaire OEM pour obtenir des informations de support proxy.

Les appareils Android Teams n’ont pas besoin de se connecter à un réseau local interne. Envisagez de placer des appareils Android Teams dans un segment réseau sécurisé avec un accès Direct à Internet. Par exemple, les téléphones Teams peuvent être déployés sur un réseau local virtuel vocal. Si votre réseau local interne est compromis, les opportunités de vecteur d’attaque vers les appareils Android Teams seront réduites en implémentant cette séparation du réseau.

Nous vous recommandons vivement de connecter vos appareils Android Teams à un réseau câblé. L’utilisation de réseaux sans fil nécessite une planification et une évaluation minutieuses pour une expérience optimale.

La jointure de proximité, Better Together, Teams Cast et l’appairage des panneaux Teams reposent sur Bluetooth. L’utilisation de la technologie Bluetooth sur salles Teams pour les appareils Android est actuellement limitée aux balises publicitaires et aux connexions proximales invités. Le `ADV_NONCONN_INT` type d’unité de données de protocole (PDU) est utilisé dans la balise de publicité. Ce type PDU est destiné aux appareils non connectables qui annoncent des informations sur l’appareil d’écoute. Il n’existe aucun jumelage d’appareils Bluetooth dans le cadre de ces fonctionnalités. Pour plus d’informations sur les protocoles Bluetooth, consultez le site web bluetooth SIG.

Les téléphones et les écrans Teams offrent la possibilité de coupler bluetooth avec des casques à l’aide du profil de Hands-Free Bluetooth.

Pour plus d’informations sur la sécurité dans Microsoft Teams, consultez [Sécurité et Microsoft Teams](/microsoftteams/teams-security-guide).  
