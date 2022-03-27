---
title: Configurer la licence zone Téléphone commun
ms.author: czawideh
author: cazawideh
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
description: 'Découvrez comment configurer des téléphones communs pour les centres d’accueil, les zones d’accueil et les salles de conférence '
ms.openlocfilehash: 313a17d1829c8f3584ec5fb7f37e5f1ec49231d0
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456937"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Déployer des téléphones de zone commune pour Microsoft Teams

Un téléphone commun est généralement placé dans une zone telle qu’une salle d’accueil ou une autre zone accessible à de nombreuses personnes pour appeler. par exemple, une zone de réception, une salle d’accueil ou un téléphone de conférence. Les téléphones de zone commune sont signés avec des comptes liés à une licence zone Téléphone commun.

Cet article donne une vue d’ensemble de la façon de déployer et de configurer Teams téléphones en tant que téléphones à zone commune pour les espaces partagés. Pour une expérience de salle de réunion plus complète, y compris les audioconférences, envisagez d’acheter la licence de salle Salle de réunion dédiée avec un appareil de salle de réunion.

## <a name="overview"></a>Présentation

La licence domaine commun prend Téléphone charge : 


| &nbsp;  |  Téléphone de zone commune  |
|---------|---------|
|Skype Entreprise |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|Système téléphonique |    &#x2714; |
|Audioconférence |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|Disponibilité mondiale |       &#x2718; &sup2;  |
|Disponibilité des canaux |    EA, EAS, CSP, Cloud de la communauté du secteur public, EES, Web Direct  |
|      |         |

&sup1; Les téléphones de la zone commune peuvent participer à des audioconférences via un numéro d’accès fourni par l’organisateur de la réunion

&sup2; Non disponible dans des nuages souverains  

>[!NOTE]
> Les comptes des objets de téléphones en zone commune créés dans Skype Entreprise Server ne peuvent pas être migrés vers Microsoft Teams. Suivez les étapes de cet article pour recréer ces comptes pour Teams et, si nécessaire, migrer votre connectivité PTSN.

## <a name="step-1---buy-the-licenses"></a>Étape 1 - Acheter les licences

Tout d’abord, vous devez acheter une licence zone Téléphone (CAP) et vous assurer que vous avez un téléphone certifié. Pour rechercher et en savoir plus sur les téléphones certifiés, voir [Microsoft Teams appareils mobiles](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. Dans le Centre d'administration Microsoft 365, allez aux **services BillingPurchase** > . 

2. Si la section **Afficher par** catégorie n’est pas déjà affichée, sélectionnez Acheter auprès de **Microsoft**, puis **Afficher les produits**. Sélectionnez ensuite **Collaboration et communication**.  

3. Dans la liste de produits, **recherchez la zone Téléphone** et **sélectionnez Détails**.

4. Entrez le nombre de licences dont vous avez besoin, puis sélectionnez **Acheter**.

>[!NOTE]
>Si vous utilisez Intune dans votre environnement et que vous avez des règles d’accès conditionnel qui nécessitent la conformité de l’appareil, vous devez affecter une licence Azure Active Directory Premium Plan 1 et Intune au compte d’appareil pour le téléphone de zone commune.
>
>Les téléphones de zone commune peuvent être impactés par les règles d’accès conditionnel et d’autres configurations d’identité, telles que l’authentification multifacteur. Pour [en savoir plus, consultez les meilleures pratiques Teams’authentification pour les appareils Android](devices/authentication-best-practices-for-android-devices.md).

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Étape 2 : créer un compte d’utilisateur et attribuer des licences

### <a name="using-the-microsoft-365-admin-center"></a>Utilisation de la Centre d'administration Microsoft 365

Si vous déployez plusieurs téléphones de zone communs en même temps, découvrez comment créer des comptes et attribuer des licences à l’aide [de PowerShell](#using-powershell).

Si vous déployez un appareil :

1. Dans le Centre d'administration Microsoft 365, allez à **UsersActive** >  **UsersAdd** >  **un utilisateur**.

2. Entrez un nom d’utilisateur tel que « Principal » pour le prénom et « Réception » pour le deuxième nom.

3. Entrez un nom d’affichage s’il ne prend pas en main un nom tel que « Réception principale ».

4. Entrez un nom d’utilisateur tel que « MainReception » ou « Mainlobby ».

5. Pour éviter cela, définissez manuellement le mot de passe de votre téléphone de zone commune. Pour ce faire, décochez Créer automatiquement un **mot** de passe et demander à cet utilisateur de modifier son mot de passe **lors de sa première se connectant**.  

    >[!Important]
    > Il est vivement recommandé de définir manuellement un mot de passe pour les téléphones de zone commune afin d’éviter les problèmes de sign-in pour vos utilisateurs finaux.

6. Sélectionnez l’emplacement d’utilisation de l’appareil et attribuez la licence Zone Téléphone au compte. Si d’autres licences sont nécessaires, comme les forfaits d’appels, affectez-les.

>[!NOTE]
> Vous n’avez pas besoin d’ajouter Système téléphonique licence. Il est inclus dans la licence Téléphone de zone commune.
>
>Si vous n’utilisez pas d’Téléphone Microsoft routage direct système ou d’Connecter, vous pouvez ajouter des licences de forfaits d’appels. Pour plus d’informations sur les licences, voir [Microsoft Teams licences de module complémentaire](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez PowerShell lorsque vous voulez créer et attribuer des licences pour plusieurs comptes d’utilisateurs à la fois. Pour [plus d Microsoft 365,](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) voir Créer des comptes d’utilisateurs avec PowerShell Microsoft 365 attribuer des [licences utilisateur à](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide) des comptes d’utilisateurs avec PowerShell.

## <a name="step-3---set-policies-for-common-area-phones"></a>Étape 3 : définir des stratégies pour les téléphones en zone commune

Utilisez des stratégies pour contrôler les fonctionnalités disponibles pour les utilisateurs sur les téléphones en zone commune.

>[!NOTE]
>Après avoir attribué une stratégie, connectez-vous, puis connectez-vous de nouveau. L’application d’une affectation de stratégie peut prendre jusqu’à une heure.

### <a name="ip-phone-policies"></a>Stratégies de téléphone IP

Les téléphones qui se sont inscrits avec des comptes pour Téléphone licence zone commune affichent l’expérience utilisateur en la matière.

Si vous souhaitez remplacer l’interface par défaut d’un téléphone, envisagez de créer une [stratégie de téléphone IP](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps). Par exemple, si un téléphone de zone commune est utilisé dans une zone publique, définissez une stratégie de téléphone IP pour restreindre la recherche dans le carnet d’adresses global de votre organisation et bloquer l’accès par accès à l’eau. Pour [en savoir plus, Teams l’interface utilisateur](devices/Teams-Android-devices-user-interface.md) des appareils Android.

### <a name="calling-policies"></a>Stratégies d’appel

Utilisez des stratégies d’appel pour activer les appels privés, l’utilisation du forwarding d’appel ou la sonnerie simultanée sur les téléphones communs. Pour [en savoir plus,](teams-calling-policy.md) consultez Les appels et le Teams d’autres informations.

Par défaut, le parc d’appels n’est pas activé pour les téléphones en zone commune. Vous devez créer une stratégie pour l’activer. Pour [en savoir plus, voir Parc d’appel Microsoft Teams](call-park-and-retrieve.md) récupérer.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Étape 4 : acheter et attribuer des numéros de téléphone

[Consultez gérer les numéros de téléphone](manage-phone-numbers-landing-page.md) pour votre organisation pour découvrir comment acquérir et attribuer des numéros de téléphone en fonction de votre option de connectivité PSTN.

## <a name="step-5---sign-in"></a>Étape 5 : se connectez

Une fois que vous avez créé et configuré un compte d’utilisateur, vous pouvez vous connectez à un téléphone. Selon le nombre de téléphones que vous déployez, vous avez trois options de connectez-vous :

- [Inscription locale](#local-sign-in)
- [Se connectez à partir d’un autre appareil](#sign-in-from-another-device)
- [Se connectez-vous à l’aide Teams centre d’administration](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>Inscription locale

Pour vous connectez localement avec un nom d’utilisateur et un mot de passe : 

1. Activer le téléphone en zone commune

2. **Sélectionnez Se connectez sur cet appareil**

3. Suivez les instructions de la connectez-vous sur l’appareil. Une fois que vous vous serez inscrit, le téléphone affichera l’expérience utilisateur commune sur le téléphone.

> [!NOTE]
> Si vous utilisez une stratégie de configuration personnalisée qui désépine l’application d’appel, le pavé de numérotation n’apparaît pas dans la zone Téléphone. Pour plus d’informations sur Teams de configuration, voir [Gérer les stratégies de configuration d’application dans Microsoft Teams](/microsoftteams/teams-app-setup-policies).

### <a name="sign-in-from-another-device"></a>Se connectez à partir d’un autre appareil

Vous pouvez également vous connectez à un téléphone de zone commune à partir d’un autre appareil à l’aide d’un code. Lorsque vous vous connectez de cette façon, vous entrez le nom d’utilisateur et le mot de passe sur un autre appareil, plutôt que sur le téléphone lui-même.

1. Tout d’abord, sur votre téléphone commun, recherchez le code affiché sur l’écran de inscription.

2. Sur un autre appareil, allez à https://www.microsoft.com/devicelogin.

3. Entrez le code et en suivant les instructions pour terminer la connectez-vous.

### <a name="sign-in-using-the-teams-admin-center"></a>Se connectez-vous à l’aide Teams centre d’administration

En tant qu’administrateur, vous pouvez mettre en service à distance des téléphones communs et vous y connectez à partir du centre Teams’administration. Il s’agit de la méthode de sign-in la plus efficace lorsque vous déployez un grand nombre de téléphones à la fois. [Consultez la mise en service à distance et connectez-vous Teams appareils Android](devices/remote-provision-remote-login.md) pour en savoir plus.

## <a name="next-steps"></a>Étapes suivantes

À présent que vous avez installé et inscrit des téléphones en zone commune pour votre organisation, vous pouvez les gérer dans le Teams d’administration. Voir [Microsoft Teams : Gestion de vos appareils pour](devices/device-management.md) en savoir plus.

## <a name="related-topics"></a>Sujets associés

- [Mettre à jour Microsoft Teams appareils à distance](devices/remote-update.md)
- [Gérer Microsoft Teams balises d’appareil](devices/manage-device-tags.md)
- [Microsoft Teams d’état des appareils](alerts/device-health-status.md)
