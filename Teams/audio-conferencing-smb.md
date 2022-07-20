---
title: Configurer l’audioconférence pour les petites et moyennes entreprises
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Découvrez comment définir l’audioconférence dans votre petite ou moyenne entreprise pour les personnes qui doivent utiliser un téléphone pour se connecter à des réunions. '
ms.openlocfilehash: b7b5fbc958c67aa966619c961e011cda9450faf3
ms.sourcegitcommit: 312ff79ecab91412918793ec882bfc6e0143d30a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66884823"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Configurer l’audioconférence pour les petites et moyennes entreprises

Avec l’audioconférence, les utilisateurs peuvent appeler des réunions Teams à l’aide d’un téléphone au lieu d’utiliser l’application Teams sur leur appareil mobile ou à partir de leur ordinateur.  

Si vous êtes une petite ou moyenne entreprise avec jusqu’à 300 utilisateurs et que vous n’avez actuellement pas de licences d’audioconférence, vous pouvez obtenir l’audioconférence gratuitement pendant un an. Cette offre gratuite est disponible à partir du 1er octobre 2020.

La licence de module complémentaire d’audioconférence peut être appliquée aux utilisateurs disposant de licences Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 ou Enterprise E3. Pour en savoir plus, consultez les [licences de module complémentaire Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Si vous avez Enterprise E5 ou Microsoft 365 Business Voice, vous ne pourrez pas utiliser l’offre d’audioconférence gratuite, car ces licences incluent déjà l’audioconférence.

Dans cet article, nous allons vous guider dans la configuration de l’audioconférence. Il vous suffit de configurer la fonctionnalité de conférence audio pour les utilisateurs qui comptent planifier ou organiser des réunions. Les participants aux réunions qui appellent des réunions n’ont pas besoin de licences ou d’une autre configuration. Pour plus d’informations, consultez [Audioconférence](audio-conferencing-in-office-365.md).

## <a name="set-up-audio-conferencing"></a>Configurer l'audioconférence

Lorsque vous configurez l’audioconférence, un numéro de téléphone est automatiquement affecté à votre pont de conférence afin qu’il puisse être utilisé dans les invitations à une réunion. Le numéro de téléphone affecté en tant que numéro par défaut de votre pont de conférence est un numéro du pays ou de la région de votre organisation. Ce numéro de téléphone est un numéro de téléphone, dans lequel des frais de longue distance peuvent s’appliquer.

> [!NOTE]
> Vous pouvez également utiliser un numéro gratuit, ce qui nécessite quelques étapes supplémentaires. Pour en savoir plus sur les numéros de téléphone de votre pont de conférence, consultez les [numéros de téléphone d’audioconférence](#audio-conferencing-phone-numbers) plus loin dans cet article.

### <a name="step-1-get-audio-conferencing-licenses"></a>Étape 1 : Obtenir des licences d’audioconférence

Obtenez une licence d’audioconférence pour chaque personne qui dirigera des réunions. Utilisez la Centre d'administration Microsoft 365 pour ce faire.

1. Dans le Centre d'administration Microsoft 365, accédez aux **services d’achat** de **facturation** > , puis, en bas de la page, sélectionnez **Modules complémentaires**.
2. Sélectionnez **Microsoft 365 Audio Conferencing Adoption Promo** > **Details**, puis **sélectionnez Obtenir maintenant**.
3. Entrez le nombre de licences dont vous avez besoin pour les organisateurs de votre réunion, puis complétez votre commande.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Capture d’écran de la licence Promo d’adoption de l’audioconférence.":::

    > [!NOTE]
    > Désactivez ou sélectionnez **l’affectation automatique à tous vos utilisateurs sans licence**, selon que vous souhaitez attribuer automatiquement une licence d’audioconférence à tous les utilisateurs qui n’ont pas cette licence.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Étape 2 : Attribuer une licence d’audioconférence aux utilisateurs qui dirigent des réunions

Attribuez une licence à chaque personne qui dirigera des réunions. Utilisez la Centre d'administration Microsoft 365 pour ce faire.

#### <a name="assign-a-license-to-one-user"></a>Attribuer une licence à un utilisateur

1. Dans le Centre d'administration Microsoft 365, accédez à **Utilisateurs** > **actifs**.  
2. Sélectionnez la ligne de l’utilisateur auquel vous souhaitez attribuer la licence, puis, dans le volet, sélectionnez **Licences et applications**.
3. Activez la case à cocher **Audioconférence Microsoft 365** , puis **sélectionnez Enregistrer les modifications**.

#### <a name="assign-a-license-to-multiple-users"></a>Attribuer une licence à plusieurs utilisateurs

1. Dans le Centre d'administration Microsoft 365, accédez à **Utilisateurs** > **actifs**.  
2. Sélectionnez les cercles en regard des utilisateurs auxquels vous souhaitez attribuer la licence, puis sélectionnez **Gérer les licences de produit**.
3. Dans le volet **Gérer les licences de produit** , sélectionnez **Affecter plus**.
4. Activez la case à cocher **Audioconférence Microsoft 365** , puis **sélectionnez Enregistrer les modifications**.  

> [!IMPORTANT]
> Jusqu’à 24 heures peuvent être nécessaires pour que les numéros de téléphone attribués s’affichent sur votre invitation à la réunion. Si vous ne voyez pas les numéros mis à jour s’afficher, patientez au moins 24 heures avant de contacter le support technique.

## <a name="schedule-teams-meetings-in-outlook"></a>Planifier des réunions Teams dans Outlook

Les organisateurs de vos réunions peuvent désormais planifier des réunions dans Outlook. Dans Outlook, accédez au **calendrier**, puis sélectionnez le bouton **Nouvelle réunion Teams** . Les numéros d’accès à la réunion et l’ID de conférence sont automatiquement ajoutés à l’invitation à la réunion envoyée aux participants à la réunion. Pour plus d’informations, consultez [Planifier une réunion Teams dans Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).

> [!NOTE]
> Si vous le souhaitez, vous pouvez personnaliser les invitations aux réunions pour ajouter le logo de votre entreprise, les liens vers votre site web de support et la clause d’exclusion de responsabilité légale, ainsi qu’un pied de page de texte uniquement. Pour plus d’informations, consultez [Personnaliser les invitations aux réunions](meeting-settings-in-teams.md#customize-meeting-invitations).

## <a name="audio-conferencing-phone-numbers"></a>Numéros de téléphone d’audioconférence

Il existe deux types de nombres que vous pouvez utiliser pour votre pont de conférence. Vous pouvez utiliser **des numéros partagés** (comme dans la section [Configurer l’audioconférence](#set-up-audio-conferencing) plus haut dans cet article) ou **des numéros dédiés**. Voici plus d’informations sur chacune d’elles.

### <a name="shared-numbers"></a>Nombres partagés

Un nombre partagé est un nombre partagé entre toutes les organisations. Les numéros partagés sont des numéros payants et sont automatiquement attribués lorsque vous configurez l’audioconférence.

Pour afficher le numéro par défaut affecté à votre pont de conférence, dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **ponts de conférence** **Réunions** > , puis recherchez le numéro correspondant à l’emplacement le plus proche de vous.

### <a name="dedicated-numbers"></a>Nombres dédiés

Un numéro dédié est un nombre disponible uniquement pour vos utilisateurs. Un numéro dédié peut être un numéro payant ou un numéro gratuit. Pour utiliser un numéro dédié, vous devez d’abord obtenir le numéro, l’affecter à votre pont de conférence, puis attribuer le numéro à chaque personne qui dirigera les réunions.

Il existe deux façons d’obtenir un nombre dédié. Vous pouvez obtenir un numéro de Microsoft ou transférer (port) un numéro existant de votre fournisseur de services actuel vers Microsoft. Pour en savoir plus sur la façon de procéder, consultez [Obtenir les numéros de service](getting-service-phone-numbers.md).

Gardez à l’esprit que si vous utilisez un numéro gratuit, vous devez d’abord attribuer une licence de crédits de communication à chaque personne qui dirigera des réunions. Pour plus d’informations, consultez [Configurer les crédits de communication pour votre organisation](set-up-communications-credits-for-your-organization.md).

Une fois que vous avez votre numéro, attribuez-le à votre pont de conférence. Pour ce faire, utilisez le Centre d’administration Microsoft Teams.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **ponts de conférence** **Réunions** > .
2. Sélectionnez **Ajouter**, puis **sélectionnez Numéro payant** ou **Numéro gratuit**.
3. Dans le volet **Ajouter un numéro de téléphone** , sélectionnez le numéro, puis **sélectionnez Appliquer**.

#### <a name="assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Attribuer des numéros de téléphone rendez-vous pour les utilisateurs qui dirigent des réunions

Reportez-vous à [Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> Vous pouvez également définir des numéros de téléphone en les ajoutant à *TeamsAudioconferencingpolicy et en affectant* la stratégie à vos utilisateurs. Les numéros de téléphone payants et gratuits ajoutés à la stratégie sont prioritaires sur les numéros de téléphone définis individuellement pour les utilisateurs via le volet des paramètres d’audioconférence. Si aucun numéro de téléphone n’est ajouté à *teamsaudioconferencingpolicy*, le numéro de téléphone défini individuellement pour les utilisateurs via le volet des paramètres d’audioconférence s’affiche dans les demandes de réunion Microsoft Teams. [Les paramètres de stratégie d’audioconférence pour les numéros payants et gratuits](audio-conferencing-toll-free-numbers-policy.md) contiennent plus d’informations.

## <a name="related-topics"></a>Sujets associés

- [Audioconférence](audio-conferencing-in-office-365.md)
- [Configurer l’audioconférence pour Teams](set-up-audio-conferencing-in-teams.md)
- [Numéros de téléphone pour l’audioconférence](phone-numbers-for-audio-conferencing-in-teams.md)
- [Questions fréquentes à propos de l’audioconférence](audio-conferencing-common-questions.md)
- [Obtention des numéros de service](getting-service-phone-numbers.md)
- [Licences de module complémentaire Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Attribuer des licences aux utilisateurs](/microsoft-365/admin/manage/assign-licenses-to-users)
