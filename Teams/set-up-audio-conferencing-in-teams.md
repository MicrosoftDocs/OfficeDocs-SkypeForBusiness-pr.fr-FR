---
title: Configurer l’audioconférence pour Microsoft teams
ms.author: tonysmit
author: tonysmit
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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Découvrez comment configurer des conférences rendez-vous ou audio pour les personnes de votre entreprise qui ont besoin d’utiliser un téléphone pour participer à des conférences téléphoniques. '
ms.openlocfilehash: 0a483dba984799a3c9e0f1a63ed908dde9a9ca08
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693949"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a>Configurer l’audioconférence pour Microsoft teams

Parfois, les membres de votre organisation doivent utiliser un téléphone pour appeler une réunion. Microsoft teams inclut la fonction de conférence rendez-vous pour cette situation. Les personnes peuvent appeler des réunions teams à l’aide d’un téléphone, au lieu d’utiliser l’application teams sur un appareil mobile ou un PC. 
  
Il vous suffit de configurer la fonctionnalité de conférence audio pour les utilisateurs qui comptent planifier ou organiser des réunions. Les participants à la réunion qui se connectent n’ont pas besoin de licence ou de configuration particulière.
  
Pour trouver les questions fréquemment posées à propos des audioconférences, consultez [Questions courantes concernant les audioconférences](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Étape 1 : Déterminez si les audioconférence sont disponibles dans votre pays/région
<a name="__top"> </a>

Allez à la page [Disponibilité des pays et des régions pour les audioconférences et les forfaits d’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) et sélectionnez votre pays ou région pour obtenir des informations de disponibilité sur les audioconférences, ainsi que des informations sur le système téléphonique, les forfaits d’appel, les numéros payants et gratuits et les crédits de communications. 
 
## <a name="step-2-get-and-assign-licenses"></a>Étape 2 : Obtenir et attribuer des licences
 
1. Pour une audioconférence, vous avez besoin d’une licence pour chaque utilisateur qui établira des réunions. Pour connaître les licences que vous devez acheter pour l’audioconférence et leurs coûts, voir [licences de module complémentaire Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > L’audioconférence est incluse dans les licences Office 365 entreprise E5 et en tant que composant additionnel.
        
2. Une fois que vous avez acheté les licences de conférence audio, vous devez les affecter aux personnes de votre organisation qui vont planifier ou animer des réunions. Voir [attribuer des licences aux utilisateurs dans Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) que vous avez acheté aux personnes de votre organisation qui vont planifier ou animer des réunions.
    
3. Nous vous recommandons également d’affecter des licences de crédits de communications (elles ne coûtent rien) aux mêmes personnes à qui vous avez attribué des licences à l’étape précédente. Pour savoir comment configurer les Crédits de communications, voir [Configurer les Crédits de communications pour votre entreprise](set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> Vous pouvez également configurer [le service de conférence](audio-conferencing-pay-per-minute.md)rendez-vous en fonction du son.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Étape 3 : Obtenir les numéros de service pour vos ponts de conférence
<a name="__top"> </a>

Pour les audioconférences, vous ne pouvez pas utiliser les numéros de téléphone pour les utilisateurs ; vous devez leur obtenir des numéros de service. Vous pouvez obtenir des numéros de service payants ou gratuits pour vos ponts de conférence. Il existe trois façons d’obtenir des numéros de service payants et gratuits  : 
  
- **Utiliser le centre d’administration Microsoft teams**. Dans certains pays ou régions, vous pouvez obtenir des numéros de service pour vos ponts de conférence à l’aide du centre d’administration Microsoft Teams. Voir [réception des numéros de téléphone de service](/microsoftteams/getting-service-phone-numbers).
    
- **Transférez vos numéros de service existants**. Pour porter ou transférer des numéros existants de votre fournisseur de services ou de l’opérateur de téléphonie actuel vers Office 365. Pour plus d’informations sur la façon de procéder, voir [transférer des numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou [gérer des numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) .  
  
- **Utiliser un formulaire de demande pour de nouveaux numéros**. Parfois (en fonction de votre pays ou région) vous ne serez pas en mesure d’obtenir vos nouveaux numéros de service à l’aide du centre d’administration Microsoft teams ou vous aurez besoin de numéros de téléphone spécifiques ou d’indicatifs régionaux. Dans ce cas, vous devez télécharger un formulaire et nous le renvoyer. Pour plus d’informations, voir [Gestion des numéros de téléphone pour votre entreprise](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Étape 4 : Affecter un numéro de service pour le pont de conférence
<a name="__top"> </a>

Une fois que vous obtenez les numéros de téléphone payants et/ou gratuits pour votre pont de conférence, vous devez les affecter pour les invitations aux réunions.  

Pour attribuer un nouveau numéro de téléphone à votre pont de conférence audio, procédez comme suit.

![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise à l' **aide du centre d’administration Skype entreprise :**

 1. Accédez au**portail**d'**administration** > **** > du centre > d' **administration Microsoft 365**.
 2. Sélectionnez **Voice** > **Numéros de téléphone**.
 3. Sélectionnez le numéro de téléphone et cliquez sur **affecter**.

Pour plus d’informations, reportez-vous à [la rubrique Modification des numéros de téléphone de votre pont de conférence audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Étape 5 : Définir les langues par défaut et alternatives pour un pont de conférence
<a name="__top"></a> Ensuite, vous pouvez [définir des langues de standard automatique pour les conférences audio dans Microsoft teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que le standard automatique de conférence utilise pour appeler les appelants quand ils se connectent à un numéro de téléphone pour les conférences audio. 

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams **à l’aide du centre d’administration Microsoft teams**:

1. Dans le tableau de bord, accédez à **meetings** > **Conference ponts**.
2. Sélectionnez le numéro de téléphone du pont de conférence, cliquez sur **modifier**, puis sélectionnez la langue par défaut.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Étape 6 : Définir vos paramètres de pont de conférence
<a name="__top"> </a>
    
Après avoir configuré votre pont de conférence, vérifiez que les paramètres par défaut, tels que les notifications d’entrée/sortie et la longueur du code confidentiel sont ceux que vous souhaitez utiliser. Si ce n’est pas le cas, vous pouvez les modifier. 

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams **à l’aide du centre d’administration Microsoft teams**:

1. Dans le tableau de bord, accédez à **meetings** > **Conference ponts**.
2. Sélectionnez **paramètres du pont**. Cela ouvrira le volet **Paramètres de pont**. 

Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Étape 7: Attribuer des numéros de téléphone de connexion pour les utilisateurs qui animent des réunions

Après avoir créé un pont d’audioconférence, vous devez définir les numéros payants et gratuits de vos utilisateurs.

Vous devez effectuer cette opération pour toutes les personnes de votre entreprise qui animent ou qui planifient des réunions. 

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams **à l’aide du centre d’administration Microsoft teams**:

1. Dans le tableau de bord, cliquez sur **utilisateurs**, sélectionnez l’utilisateur dans la liste, puis sélectionnez **modifier**.
2. Sélectionnez **modifier** en regard de **audioconférence**, puis dans le volet **audioconférence** , sélectionnez un numéro dans les listes **numéro payant** et numéro **gratuit** .

Si vous avez besoin de plus de détails, consultez [Sélectionner Microsoft en tant que fournisseur d’audioconférences](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Étape 8 : Configuration des invitations aux réunions (facultatif)
<a name="__top"> </a>
 
Les numéros d’accès définis pour l’utilisateur sont automatiquement ajoutés aux invitations aux réunions envoyées aux participants à la réunion. Vous pouvez cependant ajouter vos propres liens d’aide et légaux, un texte et une petite image de l’entreprise si vous le souhaitez. Voir [personnaliser les invitations aux réunions](meeting-settings-in-teams.md#customize-meeting-invitations).
   
## <a name="related-topics"></a>Rubriques connexes

[Questions fréquentes à propos de l'audioconférence](audio-conferencing-common-questions.md)
  
[Numéros de téléphone pour l’audioconférence dans Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md)
  
[Définition des options pour les réunions en ligne et les téléconférences](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
