---
title: Configurer la licence Common Area Téléphone
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
description: 'Découvrez comment configurer common area phones pour les halls d’accueil, les salles de réception et les salles de conférence '
ms.openlocfilehash: f3f3ee2c98e48a41bb12dcaa7fc461c623f49994
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045823"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Déployer des téléphones de zone commune pour Microsoft Teams

Un téléphone de zone commune est généralement placé dans une zone telle qu’une salle d’attente ou une autre zone qui est disponible pour de nombreuses personnes pour passer un appel; par exemple, une zone de réception, une salle d’attente ou un téléphone de conférence. Les téléphones de zone commune sont connectés avec des comptes liés à une licence Common Area Téléphone.

Cet article fournit une vue d’ensemble du déploiement et de la configuration Teams téléphones en tant que téléphones de zone commune pour les espaces partagés. Pour une expérience de salle de réunion plus complète, y compris l’audioconférence, envisagez d’acheter la licence Salle de réunion dédiée avec un appareil de salle de réunion.

## <a name="overview"></a>Présentation

La licence common area Téléphone prend en charge :

|                                           | Téléphone de zone commune                                 |
|-------------------------------------------|---------------------------------------------------|
| **Microsoft Teams**                       | &#x2714;                                          |
| **Teams Téléphone** &sup1;                   | &#x2714;                                          |
| **Audioconférence**                    | &#x2718; &sup2;                                   |
| **Microsoft Intune**                      | &#x2714;                                          |
| **Azure Active Directory Premium plan 1** | &#x2714;                                          |
| **Exchange Online plan 2**                | &#x2714;  &sup3;                                  |
| **Disponibilité mondiale**                | &#x2714;                                          |
| **Disponibilité du canal**                  | EA, EAS, EES, fournisseur de solutions Cloud, Web Direct, Cloud de la communauté du secteur public, Cloud de la communauté du secteur public-High, DoD |

&sup1; Anciennement appelé Système téléphonique.

&sup2; Les téléphones de zone commune peuvent participer à des conférences audio via un numéro de connexion fourni par l’organisateur de la réunion.  

&sup3; Fonctionnalités de messagerie vocale basées sur le cloud uniquement.

>[!NOTE]
> Les comptes pour les objets téléphones de zone commune créés dans Skype Entreprise Server ne peuvent pas être migrés vers Microsoft Teams. Suivez les étapes décrites dans cet article pour recréer ces comptes pour Teams et, si nécessaire, migrer votre connectivité PTSN.

## <a name="step-1---buy-the-licenses"></a>Étape 1 - Acheter les licences

Tout d’abord, vous devez acheter une licence Common Area Téléphone (CAP) et vous assurer que vous disposez d’un téléphone certifié. Pour rechercher et en savoir plus sur les téléphones certifiés, accédez à [Microsoft Teams appareils](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).

1. Dans le Centre d'administration Microsoft 365, accédez aux **services d’achat** de **facturation** > . 

2. Si la section **Affichage par catégorie** n’est pas déjà affichée, accédez à **Acheter auprès de Microsoft**, puis sélectionnez **Afficher les produits**. Sélectionnez Ensuite **Collaboration et communication**.  

3. Dans la liste des produits, **recherchez Common Area Téléphone** et sélectionnez **Détails**.

4. Entrez le nombre de licences dont vous avez besoin, puis **sélectionnez Acheter**.

>[!NOTE]
>Si vous utilisez Intune dans votre environnement et que vous avez des règles d’accès conditionnel qui nécessitent la conformité des appareils, vous devez attribuer une licence Azure Active Directory Premium Plan 1 et Intune au compte d’appareil pour le téléphone de la zone commune.
>
>Les téléphones de zone commune peuvent être affectés par des règles d’accès conditionnel et d’autres configurations d’identité, telles que Multi-Factor Authentication. Pour en savoir plus, consultez les [meilleures pratiques d’authentification pour Teams Android appareils](devices/authentication-best-practices-for-android-devices.md).

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>Étape 2 : Créer un compte d’utilisateur et attribuer des licences

### <a name="using-the-microsoft-365-admin-center"></a>Utilisation de la Centre d'administration Microsoft 365

Si vous déployez plusieurs téléphones communs à la fois, découvrez comment créer des comptes et attribuer des licences [à l’aide de PowerShell](#using-powershell).

Si vous déployez un appareil :

1. Dans le Centre d'administration Microsoft 365, accédez à **Utilisateurs** > **actifs Utilisateurs** > **Ajouter un utilisateur**.

2. Entrez un nom d’utilisateur comme « Main » pour le prénom et « Réception » pour le deuxième nom.

3. Entrez un nom d’affichage s’il n’en génére pas automatiquement un tel que « Réception principale ».

4. Entrez un nom d’utilisateur comme « MainReception » ou « Mainlobby ».

5. Définissez manuellement le mot de passe de votre téléphone de zone commune pour l’empêcher. Pour ce faire, décochez **automatiquement créer un mot de passe** et **demandez à cet utilisateur de modifier son mot de passe lors de sa première connexion**.  

    >[!Important]
    > Il est vivement recommandé de définir un mot de passe manuellement pour les téléphones de zone commune afin d’éviter les problèmes de connexion pour vos utilisateurs finaux.

6. Sélectionnez l’emplacement d’utilisation de l’appareil et affectez la licence Common Area Téléphone au compte. Si d’autres licences sont nécessaires, comme les forfaits d’appels, affectez-les.

>[!NOTE]
> Vous n’avez pas besoin d’ajouter une licence Système téléphonique. Il est inclus dans la licence Téléphone de zone commune.
>
>Si vous n’utilisez pas Téléphone Microsoft routage direct système ou Operator Connect, vous pouvez ajouter des licences forfaits d’appels. Pour plus d’informations sur les licences, consultez Microsoft Teams licences [de module](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) complémentaire.

### <a name="using-powershell"></a>Utiliser PowerShell

Utilisez PowerShell lorsque vous souhaitez créer et attribuer des licences pour plusieurs comptes d’utilisateur à la fois. Pour plus d’informations, consultez [Créer Microsoft 365 comptes d’utilisateur avec PowerShell](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true) et [attribuer des licences Microsoft 365 aux comptes d’utilisateur avec PowerShell](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

## <a name="step-3---set-policies-for-common-area-phones"></a>Étape 3 : définir des stratégies pour les téléphones de zone commune

Utilisez des stratégies pour contrôler les fonctionnalités disponibles pour les utilisateurs sur les téléphones de zone commune.

>[!NOTE]
>Après avoir affecté une stratégie, déconnectez-vous du téléphone et connectez-vous. L’application d’une affectation de stratégie peut prendre jusqu’à une heure.

### <a name="ip-phone-policies"></a>Stratégies de téléphone IP

Les téléphones connectés avec des comptes auxquels une licence Common Area Téléphone a été attribuée affichent l’expérience utilisateur de la zone commune.

Si vous souhaitez remplacer l’interface par défaut d’un téléphone, envisagez de créer une stratégie [de téléphone IP](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps&preserve-view=true). Par exemple, si un téléphone de zone commune est utilisé dans une zone publique, définissez une stratégie de téléphone IP pour restreindre la recherche dans le carnet d’adresses global de votre organisation et bloquer les appels à chaud. Pour en savoir plus, consultez [Définir Teams Android l’interface utilisateur des appareils](devices/Teams-Android-devices-user-interface.md).

### <a name="calling-policies"></a>Stratégies d’appel

Utilisez des stratégies d’appel pour activer les appels privés, l’utilisation du transfert d’appel ou l’sonnerie simultanée sur les téléphones de la zone commune. Pour en savoir plus, consultez [l’appel et le transfert d’appel dans Teams](teams-calling-policy.md).

Par défaut, le parc d’appels n’est pas activé pour les téléphones de zone commune. Vous devez créer une stratégie pour l’activer. Consultez [Parc d’appels et récupérez-le dans Microsoft Teams](call-park-and-retrieve.md) pour en savoir plus.

## <a name="step-4---acquire-and-assign-phone-numbers"></a>Étape 4 : Acquérir et attribuer des numéros de téléphone

Consultez [Gérer les numéros de téléphone de votre organisation](manage-phone-numbers-landing-page.md) pour savoir comment acquérir et attribuer des numéros de téléphone en fonction de votre option de connectivité RTC.

## <a name="step-5---sign-in"></a>Étape 5 : se connecter

Une fois que vous avez créé et configuré un compte d’utilisateur, vous pouvez vous connecter à un téléphone. Selon le nombre de téléphones que vous déployez, vous disposez de trois options de connexion :

- [Connexion locale](#local-sign-in)
- [Se connecter à partir d’un autre appareil](#sign-in-from-another-device)
- [Se connecter à l’aide du centre d’administration Teams](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>Connexion locale

Pour vous connecter localement avec un nom d’utilisateur et un mot de passe : 

1. Activer le téléphone de la zone commune

2. Sélectionnez **Se connecter sur cet appareil**

3. Suivez les instructions de connexion sur l’appareil. Une fois connecté, le téléphone affiche l’expérience utilisateur du téléphone de la zone commune.

> [!NOTE]
> Si vous utilisez une stratégie d’installation personnalisée qui désépinglait l’application appelante, le pavé de numérotation n’apparaît pas sur le Téléphone de la zone commune. Pour plus d’informations sur Teams stratégies d’installation, consultez [Gérer les stratégies d’installation d’application dans Microsoft Teams](/microsoftteams/teams-app-setup-policies).

### <a name="sign-in-from-another-device"></a>Se connecter à partir d’un autre appareil

Vous pouvez également vous connecter à un téléphone de zone commune à partir d’un autre appareil à l’aide d’un code. Lorsque vous vous connectez de cette façon, vous entrez le nom d’utilisateur et le mot de passe sur un autre appareil, plutôt que sur le téléphone lui-même.

1. Tout d’abord, sur votre téléphone de zone commune, recherchez le code affiché sur l’écran de connexion.

2. Sur un autre appareil, accédez à https://www.microsoft.com/devicelogin.

3. Entrez le code et suivez les instructions pour terminer la connexion.

### <a name="sign-in-using-the-teams-admin-center"></a>Se connecter à l’aide du centre d’administration Teams

En tant qu’administrateur, vous pouvez approvisionner et vous connecter à distance aux téléphones de la zone commune à partir du centre d’administration Teams. Il s’agit de la méthode de connexion la plus efficace lorsque vous déployez un grand nombre de téléphones à la fois. Pour en savoir plus, consultez [l’approvisionnement à distance et connectez-vous aux appareils Teams Android](devices/remote-provision-remote-login.md).

## <a name="next-steps"></a>Étapes suivantes

Maintenant que vous avez configuré et connecté des téléphones de zone commune pour votre organisation, vous pouvez les gérer dans le centre d’administration Teams. Consultez [Microsoft Teams : Gestion de vos appareils](devices/device-management.md) pour en savoir plus.

## <a name="related-topics"></a>Voir aussi

- [Mettre à jour des appareils Microsoft Teams à distance](devices/remote-update.md)
- [Gérer Microsoft Teams balises d’appareil](devices/manage-device-tags.md)
- [Microsoft Teams surveillance de l’intégrité des appareils](alerts/device-health-status.md)
