---
title: Configurer l’audioconférence pour Microsoft Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
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
- LIL_Placement
description: 'Découvrez comment configurer la Conférence rendez-vous ou l’Audioconférence pour les membres de votre entreprise qui doivent utiliser un téléphone pour participer à des téléconférences. '
ms.openlocfilehash: 742393413ccf1a9e8a9d715f4ddfa199a4c4e35c
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055154"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Configurer l’audioconférence pour Microsoft Teams

Il arrive que des membres de votre organisation aient besoin d'utiliser un téléphone pour participer à une réunion. Microsoft Teams inclut la fonction d'audioconférence pour cette situation ! Les personnes peuvent participer aux réunions Teams en utilisant un téléphone, au lieu d'utiliser l'application Teams sur un appareil mobile ou un PC.
  
Il vous suffit de configurer la fonctionnalité de conférence audio pour les utilisateurs qui comptent planifier ou organiser des réunions. Les participants à la réunion qui se connectent n’ont pas besoin de licence ou de configuration particulière.
  
Pour trouver les questions fréquemment posées à propos des audioconférences, consultez [Questions courantes concernant les audioconférences](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Étape 1 : Déterminez si les audioconférence sont disponibles dans votre pays/région

Allez à la page [Disponibilité des pays et des régions pour les audioconférences et les forfaits d’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) et sélectionnez votre pays ou région pour obtenir des informations de disponibilité sur les audioconférences, ainsi que des informations sur le système téléphonique, les forfaits d’appel, les numéros payants et gratuits et les crédits de communications.

## <a name="step-2-get-and-assign-licenses"></a>Étape 2 : Obtenir et attribuer des licences

1. Pour une audioconférence, vous avez besoin d’une licence pour chaque utilisateur qui établira des réunions. Pour savoir quels contrats de licences vous devez acheter pour une audioconférence et connaître leurs prix, consultez [Licences de module complémentaire Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE]
    > La fonctionnalité audioconférence est incluse dans les licences Office 365 Entreprise E5 et en tant que composant additionnel.

2. Une fois que vous avez acheté les licences d’audioconférence, vous devez les attribuer aux personnes qui vont planifier ou animer des réunions. Voir [Attribuer ou supprimer des licences pour Microsoft 365 ou Office 365 Entreprise](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que vous avez achetées aux collègues qui vont planifier ou animer des réunions.

3. Nous vous recommandons également d’affecter des licences de crédits de communications (elles ne coûtent rien) aux mêmes personnes à qui vous avez attribué des licences à l’étape précédente. Pour savoir comment configurer les Crédits de communications, voir [Configurer les Crédits de communications pour votre entreprise](set-up-communications-credits-for-your-organization.md).

   > [!NOTE]
   > Vous pouvez également configurer les [audioconférences en mode « payer à la minute »](audio-conferencing-pay-per-minute.md).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Étape 3 : Obtenir les numéros de service pour vos ponts de conférence

Pour les audioconférences, vous ne pouvez pas utiliser les numéros de téléphone pour les utilisateurs ; vous devez leur obtenir des numéros de service. Vous pouvez obtenir des numéros de service payants ou gratuits pour vos ponts de conférence. Il existe trois façons d’obtenir des numéros de service payants et gratuits  :
  
- **Utiliser le Centre d’administration Microsoft Teams**. Pour certains pays/régions, vous pouvez obtenir les numéros de service pour les ponts de conférence à l’aide du centre d’administration Microsoft Teams. Voir [Obtention de numéros de téléphone de service](./getting-service-phone-numbers.md).

- **Portage de vos numéros de service existants**. Pour porter ou transférer des numéros existants de votre fournisseur de service ou de votre téléphone actuel vers Microsoft 365 ou Office 365. Vous pouvez consulter [Transfert des numéros de téléphone vers Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou [Gestion des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) pour plus d’informations pour vous aider à effectuer ces opérations.  
  
- **Utiliser un formulaire de demande pour de nouveaux numéros**. Il peut arriver (en fonction votre pays ou région) que vous ne puissiez pas obtenir vos nouveaux numéros de service de téléphone à l’aide du centre d’administration de Microsoft Teams, ou que vous ayez besoin de numéros de téléphone ou indicatifs spécifiques. Si c'est le cas, vous devrez télécharger un formulaire et nous le renvoyer. Pour plus d’informations, voir [Gestion des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Étape 4 : Affecter un numéro de service pour le pont de conférence

Une fois que vous obtenez vos numéros de téléphone payants et/ou gratuits pour le pont de conférence, vous devez les assigner afin qu’ils puissent être utilisés pour les invitations aux réunions.  

Suivez ces étapes pour affecter un nouveau numéro de téléphone à votre pont d’audioconférence.

 **Utiliser le Centre d’administration Microsoft Teams**

 1. À partir de l’accueil, allez dans **Numéros** >  **de téléphone vocaux**.
 2. Sélectionnez le numéro de téléphone, puis cliquez sur **Affecter**.

Pour plus d’informations, consultez la rubrique [Modifier les numéros de téléphone sur votre pont d’audioconférence](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Étape 5 : définition des langues par défaut et autres langues de remplacement pour un pont de conférence

Ensuite, vous devez [Définir les langues du standard automatique pour les audioconférences dans Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que le standard automatique de la conférence utilisera pour accueillir les appelants lorsqu’ils se connecteront à un numéro de téléphone pour une audioconférence.

 **Utiliser le Centre d’administration Microsoft Teams**

1. Dans le tableau de bord, accédez à **Réunions** > **Ponts de conférence**.
2. Sélectionnez le numéro de téléphone de pont de conférence, cliquez sur **Modifier**, puis choisissez la langue par défaut.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Étape 6 : Définir vos paramètres de pont de conférence

Après avoir configuré votre pont de conférence, vérifiez que les paramètres par défaut, tels que les notifications d’entrée/sortie et la longueur du code confidentiel sont ceux que vous souhaitez utiliser. Si ce n’est pas le cas, vous pouvez les modifier.

 **Utiliser le Centre d’administration Microsoft Teams**

1. Dans le tableau de bord, accédez à **Réunions** > **Ponts de conférence**.
2. Sélectionnez **Paramètres de la passerelle**. Cela ouvre le volet des **paramètres de la passerelle**.

Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Étape 7: Attribuer des numéros de téléphone de connexion pour les utilisateurs qui animent des réunions

Après avoir créé un pont d’audioconférence, vous devez définir les numéros payants et gratuits de vos utilisateurs.

Vous devez effectuer cette opération pour toutes les personnes de votre entreprise qui animent ou qui planifient des réunions.

 **Utiliser le Centre d’administration Microsoft Teams**

1. À partir de la page d'accueil, cliquez sur **Utilisateurs**, sélectionnez l'utilisateur dans la liste, puis sélectionnez **Modifier**.
2. Sélectionnez **Modifier** à côté de **Audioconférence**, puis dans le volet **Audioconférence**, choisissez un numéro dans les listes de **numéros payants** et de **numéros gratuits**.

Si vous avez besoin de plus de détails, consultez [Sélectionner Microsoft en tant que fournisseur d’audioconférences](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="step-8-set-up-meeting-invitations-optional"></a>Étape 8 : Configuration des invitations aux réunions (facultatif)

Les numéros de connexion définis pour l'utilisateur seront ajoutés automatiquement aux invitations envoyées aux participants à la réunion. Vous pouvez cependant ajouter vos propres liens d’aide et légaux, un texte et une petite image de l’entreprise si vous le souhaitez. Voir [Personnaliser les invitations aux réunions](meeting-settings-in-teams.md#customize-meeting-invitations).

## <a name="related-topics"></a>Sujets associés

[Questions fréquentes à propos de l’audioconférence](audio-conferencing-common-questions.md)
  
[Numéros de téléphone pour l’audioconférence dans Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Définition des options pour les réunions en ligne et les téléconférences](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
