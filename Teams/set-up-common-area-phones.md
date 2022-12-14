---
title: Configurer les téléphones de zone commune pour Microsoft Teams
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
- admindeeplinkMAC
- admindeeplinkTEAMS
description: Découvrez comment configurer des téléphones d’espace commun pour les halls d’entrée, les zones de réception et les salles de conférence.
ms.openlocfilehash: 06005f853ac125478ae1fd99dba2d022c5eb0100
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392154"
---
# <a name="set-up-common-area-phones-for-microsoft-teams"></a>Configurer des téléphones de zone commune pour Microsoft Teams

Un téléphone de zone commune est généralement placé dans une zone comme un hall ou une autre zone qui est disponible pour de nombreuses personnes pour passer un appel : une zone de réception, une salle d’attente ou un téléphone de conférence. Les téléphones de zone commune sont connectés avec des comptes liés à une licence **d’appareils partagés Microsoft Teams**.

Cet article fournit une vue d’ensemble de la façon de déployer et de configurer des appareils téléphoniques Teams en tant que téléphones de zone commune pour les espaces partagés. Pour une expérience de salle de réunion plus complète, y compris l’audioconférence, envisagez plutôt d’acheter une licence **salles Teams** dédiée avec un appareil salles Teams. Pour plus d’informations sur salles Teams, consultez [Salles Microsoft Teams](rooms/index.md).

> [!NOTE]
> Les comptes pour les objets de téléphones de zone commune créés dans Skype Entreprise Server ne peuvent pas être migrés vers Microsoft Teams. Suivez les étapes décrites dans cet article pour recréer ces comptes pour Teams et, si nécessaire, migrer votre connectivité RTC (Public Switched Telephone Network).

## <a name="step-1---buy-the-licenses"></a>Étape 1 - Acheter les licences

Tout d’abord, vous devez acheter une licence **Appareils partagés Teams** et vérifier que vous disposez d’un téléphone certifié. Pour rechercher et en savoir plus sur les téléphones certifiés, accédez à [Microsoft appareils Teams](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. Dans la [Centre d'administration Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), accédez à **Facturation** > **Acheter des services**.

2. Si la section **Afficher par catégorie** n’est pas déjà affichée, accédez à **Acheter à partir de Microsoft**, puis sélectionnez **Afficher les produits**. Sélectionnez ensuite **Collaboration et communication**.  

3. Dans la liste des produits, **recherchez Microsoft Appareils partagés Teams**, puis sélectionnez **Détails**.

4. Entrez le nombre de licences dont vous avez besoin, puis sélectionnez **Acheter**.

> [!NOTE]
> Si vous utilisez Intune dans votre environnement et que vous avez des règles d’accès conditionnel qui nécessitent la conformité de l’appareil, vous devez attribuer une **Azure Active Directory Premium Plan 1** et **Intune** licence au compte d’appareil pour le téléphone de zone commune.
>
> Les téléphones de zone commune peuvent être affectés par des règles d’accès conditionnel et d’autres configurations d’identité, telles que Multi-Factor Authentication. Pour en savoir plus, consultez [Bonnes pratiques d’authentification pour les appareils Android Teams](devices/authentication-best-practices-for-android-devices.md) .

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Étape 2 : Créer un compte d’utilisateur et attribuer des licences

### <a name="using-the-microsoft-365-admin-center"></a>Utilisation du Centre d'administration Microsoft 365

Si vous déployez plusieurs téléphones de zone commune à la fois, découvrez comment créer des comptes et attribuer des licences à [l’aide de PowerShell](#using-powershell).

Si vous déployez un appareil :

1. Dans la [Centre d'administration Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339), accédez à **Utilisateurs** > **utilisateurs actifs** > **Ajouter un utilisateur**.

2. Entrez un nom d’utilisateur comme `Main` pour le prénom et `Reception` pour le deuxième nom.

3. Entrez un nom d’affichage s’il n’en génère pas automatiquement un comme `Main Reception`.

4. Entrez un nom d’utilisateur comme `MainReception` ou `Mainlobby`.

5. Définissez manuellement le mot de passe de votre téléphone de zone commune. Pour définir le mot de passe, décochez **créer automatiquement un mot de passe** et **demandez à cet utilisateur de modifier son mot de passe lors de sa première connexion**.  

    > [!IMPORTANT]
    > Il est vivement recommandé de définir manuellement un mot de passe pour les téléphones de zone commune afin d’éviter les problèmes de connexion pour vos utilisateurs finaux.

6. Sélectionnez l’emplacement d’utilisation de l’appareil et attribuez la licence **Appareils partagés Teams** au compte. Si d’autres licences sont nécessaires, telles que les forfaits d’appels, affectez-les.

> [!NOTE]
> Vous n’avez pas besoin d’ajouter une licence avec les fonctionnalités du système téléphonique. Il est inclus avec la licence **Appareils partagés Teams** .
>
> Si vous n’utilisez pas Microsoft système téléphonique avec routage direct ou connexion d’opérateur, vous pouvez ajouter des licences **forfaits d’appels**. Pour plus d’informations sur les licences, consultez [Microsoft licences de module complémentaire Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez PowerShell lorsque vous souhaitez créer et attribuer des licences pour plusieurs comptes d’utilisateur à la fois. Pour plus d’informations, consultez [Créer Microsoft 365 comptes d’utilisateur avec PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) et [Attribuer des licences Microsoft 365 à des comptes d’utilisateur avec PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

## <a name="step-3---set-policies-for-common-area-phones"></a>Étape 3 : Définir des stratégies pour les téléphones de zone commune

Utilisez des stratégies pour contrôler les fonctionnalités disponibles pour les utilisateurs sur les téléphones de zone commune.

### <a name="ip-phone-policies"></a>Stratégies de téléphone IP

La stratégie Téléphone IP Teams ne peut être modifiée que si le compte qui se connecte au téléphone dispose d’une licence autre qu’une licence **Appareils partagés Teams** .  En cas de licence avec un abonnement Microsoft 365 E3 ou E5, ou un abonnement Office 365 Entreprise E1, E3 ou E5, vous pouvez modifier la stratégie de téléphone IP.  Si vous utilisez une licence **salles Teams** sur votre compte de téléphone de zone commune, elle vous permet uniquement d’utiliser `MeetingRoomSignIn` le mode. `MeetingRoomSignIn` le mode n’est pas disponible sur la plupart des téléphones de zone commune. Pour plus d’informations sur les remplacements pris en charge pour l’interface téléphonique, consultez [Définir Microsoft l’interface utilisateur des appareils Android Teams](/microsoftteams/devices/teams-android-devices-user-interface#override-automatic-user-interface-detection).

À l’aide de la stratégie Téléphone IP Teams, définissez le [paramètre SignInMode](/powershell/module/skype/new-csteamsipphonepolicy#parameters) sur `CommonAreaPhoneSignIn` pour activer l’expérience téléphonique de la zone commune sur l’appareil téléphonique Teams.

Pour configurer d’autres paramètres, envisagez de créer une stratégie de [téléphone IP](/powershell/module/skype/new-csteamsipphonepolicy). Par exemple, si un téléphone de zone commune est utilisé dans une zone publique, définissez une stratégie de téléphone IP pour restreindre la recherche dans le carnet d’adresses global de votre organisation et bloquer la duplication à chaud. Pour plus d’informations, consultez [Définir l’interface utilisateur des appareils Android Teams](/microsoftteams/devices/Teams-Android-devices-user-interface).

### <a name="calling-policies"></a>Stratégies d’appel

Utilisez des stratégies d’appel pour activer les appels privés, à l’aide du transfert d’appel ou de la sonnerie simultanée sur les téléphones de zone commune. Pour plus d’informations, consultez [Appel et transfert d’appel dans Teams](teams-calling-policy.md).

Par défaut, le parcage d’appels n’est pas activé pour les téléphones de zone commune. Vous devez créer une stratégie pour l’activer. Pour plus d’informations, consultez [Parcage d’appel et récupération dans Microsoft Teams](call-park-and-retrieve.md).

> [!NOTE]
> Après avoir affecté une stratégie, déconnectez-vous du téléphone et reconnectez-vous. L’application d’une attribution de stratégie peut prendre jusqu’à une heure.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Étape 4 : Acquérir et attribuer des numéros de téléphone

Consultez [Gérer les numéros de téléphone de votre organisation pour](manage-phone-numbers-landing-page.md) savoir comment acquérir et attribuer des numéros de téléphone en fonction de votre option de connectivité RTC.

## <a name="step-5---sign-in"></a>Étape 5 : Se connecter

Une fois que vous avez créé et configuré un compte d’utilisateur, vous pouvez vous connecter à un téléphone. Selon le nombre de téléphones que vous déployez, vous disposez de trois options de connexion :

- [Connexion locale](#local-sign-in).
- [Connectez-vous à partir d’un autre appareil](#sign-in-from-another-device).
- [Connectez-vous à l’aide du Centre d’administration Teams](#sign-in-using-the-teams-admin-center).

### <a name="local-sign-in"></a>Connexion locale

Pour vous connecter localement avec un nom d’utilisateur et un mot de passe :

1. Activez le téléphone de la zone commune.
2. Sélectionnez **Se connecter sur cet appareil**.
3. Suivez les instructions de connexion sur l’appareil. Une fois connecté, le téléphone affiche l’expérience utilisateur du téléphone de la zone commune.

> [!NOTE]
> Si vous utilisez une stratégie d’installation personnalisée qui désépinglera l’application appelante, le pavé de numérotation n’apparaît pas sur le téléphone de la zone commune. Pour plus d’informations sur les stratégies d’installation de Teams, consultez [Gérer les stratégies de configuration des applications dans Microsoft Teams](teams-app-setup-policies.md).

### <a name="sign-in-from-another-device"></a>Se connecter à partir d’un autre appareil

Vous pouvez également vous connecter à un téléphone de zone commune à partir d’un autre appareil à l’aide d’un code. Lorsque vous vous connectez de cette façon, vous entrez le nom d’utilisateur et le mot de passe sur un autre appareil, plutôt que sur le téléphone lui-même.

1. Sur votre téléphone de zone commune, recherchez le code affiché sur l’écran de connexion.
2. Sur un autre appareil, accédez à [https://www.microsoft.com/devicelogin](https://www.microsoft.com/devicelogin).
3. Entrez le code et suivez les instructions pour terminer la connexion.

### <a name="sign-in-using-the-teams-admin-center"></a>Se connecter à l’aide du Centre d’administration Teams

En tant qu’administrateur, vous pouvez approvisionner et vous connecter à distance des téléphones de zone commune à partir du [Centre d’administration Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851). Cette méthode est la méthode de connexion la plus efficace lorsque vous déployez un grand nombre de téléphones à la fois. Pour plus [d’informations, consultez Provisionnement à distance et connexion pour les appareils Android Teams](devices/remote-provision-remote-login.md) .

## <a name="step-6---set-up-advanced-calling-on-common-area-phones-optional"></a>Étape 6 : Configurer l’appel avancé sur les téléphones de zone commune (facultatif)

Par défaut, l’expérience d’appel de base est sur l’écran d’accueil du téléphone de la zone commune, mais vous pouvez activer une expérience d’appel avancée.

Les fonctionnalités d’appel avancées suivantes sont disponibles pour les modèles d’appareils téléphoniques Teams pris en charge avec une licence **Appareils partagés Teams** et les dernières mises à jour Teams (version minimale : 1449/1.0.94.20222061702) :

- [Appelez le parcage et récupérez](call-park-and-retrieve.md).
- [Messagerie vocale basée sur le cloud via Exchange Online Plan 2](set-up-phone-system-voicemail.md).
  - Pour désactiver la messagerie vocale basée sur le cloud, consultez [Paramètres utilisateur de la messagerie vocale à l’aide de PowerShell](/powershell/module/skype/set-csonlinevoicemailusersettings).
- [Files d’attente d’appels](create-a-phone-system-call-queue.md).
- [Standards automatiques](create-a-phone-system-auto-attendant.md).
- [Prise en charge de l’appel de groupe](call-sharing-and-group-call-pickup.md).
- [Règles de transfert](teams-calling-policy.md).

Pour utiliser ces fonctionnalités d’appel avancées sur les modèles d’appareils téléphoniques Teams pris en charge, vous pouvez activer le bouton bascule **Appels avancés** dans le [Centre d’administration Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851) ou sur votre appareil téléphonique Teams connecté à votre compte Appareils partagés Teams.

L’activation des fonctionnalités d’appel avancées vous oblige à acheter des modèles matériels capables de prendre en charge toutes les fonctionnalités requises.

### <a name="turn-on-advanced-calling-in-teams-admin-center"></a>Activer les appels avancés dans le Centre d’administration Teams

1. Connectez-vous au [Centre d’administration Teams](https://admin.teams.microsoft.com/dashboard) avec un compte d’administrateur Microsoft 365.
1. Dans le menu de gauche, accédez à **Appareils** >  Teams **Téléphones** > et sélectionnez l’onglet **Profils de configuration**.
1. Dans la liste, sélectionnez le profil de configuration affecté à votre téléphone de zone commune.
1. Sous la section **Paramètres d’appel** , recherchez le bouton bascule **Appels avancés** .
1. Activez le bouton bascule.
1. En bas de la page, sélectionnez le bouton **Enregistrer** .

### <a name="turn-on-advanced-calling-from-a-teams-phone-device"></a>Activer les appels avancés à partir d’un appareil téléphonique Teams

1. Après vous être connecté à votre appareil téléphonique Teams, accédez à **Paramètres Paramètres** >  de **l’appareil** >  **Administration Appel uniquement** > .
1. Recherchez le bouton bascule **Appel avancé** et activez-le.

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez configuré et connecté des téléphones de zone commune pour votre organisation, vous pouvez les gérer dans le Centre d’administration Teams. Consultez [Microsoft Teams : Gestion de vos appareils](devices/device-management.md) pour en savoir plus.

## <a name="related-articles"></a>Articles connexes

- [Mettez à jour Microsoft appareils Teams à distance](devices/remote-update.md).
- [Gérer Microsoft étiquettes d’appareil Teams](devices/manage-device-tags.md).
- [Microsoft surveillance de l’intégrité des appareils Teams](alerts/device-health-status.md).
