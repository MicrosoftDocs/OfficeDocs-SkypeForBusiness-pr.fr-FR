---
title: Configurer la conférence Audio pour Skype pour les entreprises
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Découvrez comment configurer des rendez-vous ou de conférence Audio pour les personnes dans votre entreprise qui ont besoin d’utiliser un téléphone pour participer à des téléconférences. '
ms.openlocfilehash: d57eedec13d9bd1c01ec9365fd42c0a4dfdc2d96
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877189"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Configurer la conférence Audio pour Skype pour les entreprises

Parfois les personnes dans votre organisation vous devrez utiliser un téléphone pour appeler une réunion. Skype pour les entreprises inclut la fonctionnalité de conférence audio uniquement cette situation ! Personnes peuvent appeler Skype pour les réunions d’entreprise à l’aide d’un téléphone, au lieu d’utiliser le Skype pour l’application de gestion sur un appareil mobile ou un PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Pour trouver les questions fréquemment posées à propos des audioconférences, consultez [Questions courantes concernant les audioconférences](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Étape 1 : Déterminez si les audioconférence sont disponibles dans votre pays/région
<a name="__top"> </a>

Allez à la page [Disponibilité des pays et des régions pour les audioconférences et les forfaits d’appel](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) et sélectionnez votre pays ou région pour obtenir des informations de disponibilité sur les audioconférences, ainsi que des informations sur le système téléphonique, les forfaits d’appel, les numéros payants et gratuits et les crédits de communications. 
 
## <a name="step-2-get-and-assign-licenses"></a>Étape 2 : Obtenir et attribuer des licences
 
1. Pour une audioconférence, vous avez besoin d’une licence pour chaque utilisateur qui établira des réunions. Pour savoir quelle licence vous devez acheter pour l’audioconférence et comment leur coût, consultez [Skype pour les licences d’entreprise module complémentaire](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    >[!NOTE] 
    > Conférence audio est incluse dans les licences d’Office 365 entreprise E5 et en tant que composant additionnel.
        
2. Une fois que vous achetez les licences de conférence Audio, vous devez les assigner aux personnes de votre organisation qui sont sur le point de planifier ou entraîner des réunions. Voir [affecter ou supprimer des licences pour Office 365 pour entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) vous avez acheté pour les personnes de votre organisation qui sont sur le point à des réunions de planification ou responsable.
    
3. Nous vous recommandons également d’affecter des licences de crédits de communications (elles ne coûtent rien) aux mêmes personnes à qui vous avez attribué des licences à l’étape précédente. Pour savoir comment configurer les Crédits de communications, voir [Configurer les Crédits de communications pour votre entreprise](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> Vous pouvez également configurer [Audioconférence salaire par minute](/microsoftteams/audio-conferencing-pay-per-minute).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Étape 3 : Obtenir les numéros de service pour vos ponts de conférence
<a name="__top"> </a>

Pour les audioconférences, vous ne pouvez pas utiliser les numéros de téléphone pour les utilisateurs ; vous devez leur obtenir des numéros de service. Vous pouvez obtenir des numéros de service payants ou gratuits pour vos ponts de conférence. Il existe trois façons d’obtenir des numéros de service payants et gratuits  : 
  
- **Utiliser le Skype entreprise centre d’administration**. Pour certains pays/régions, vous pouvez obtenir les numéros de service pour les ponts de conférence à l’aide de la Skype entreprise centre d’administration. Voir les [numéros de téléphone de mise en service](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Port vos numéros de service existante**. Port ou transférer des nombres existants à partir de votre fournisseur de services en cours ou votre opérateur mobile à Office 365. Vous pouvez consulter [Transfert des numéros de téléphone vers Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) ou [Gestion des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization) pour plus d’informations pour vous aider à effectuer ces opérations.  
  
- **Utiliser un formulaire de demande pour les nouveaux numéros**. Parfois (en fonction de votre pays/région) vous ne pourrez pas obtenir vos nouveaux numéros de service à l’aide de la Skype entreprise centre d’administration, ou vous devez numéros de téléphone spécifiques ou les codes de zone. Dans ce cas, vous devez télécharger un formulaire et nous le renvoyer. Pour plus d’informations, voir [Gestion des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Étape 4 : Affecter un numéro de service pour le pont de conférence
<a name="__top"> </a>

Une fois que vous obtenez votre numéro payant et/ou de vos numéros de téléphone pour le pont de conférence, vous devez lui assigner les numéros afin qu’ils puissent être utilisées dans les invitations aux réunions.  

Affecter un nouveau numéro de téléphone à votre pont d’audioconférence :

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

 1. Accéder au **Centre d’administration Microsoft 365** > **Admin centres** > **équipes** > **portail hérité**.
 2. Sélectionnez **voix** > **numéros de téléphone**.
 3. Sélectionnez le numéro de téléphone, cliquez sur **affecter**.

Pour plus d’informations, consultez la rubrique [Modifier les numéros de téléphone sur votre pont d’audioconférence](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Étape 5 : Définir les langues par défaut et alternatives pour un pont de conférence
<a name="__top"> </a>

Ensuite, vous souhaitez [définir des langues de standard automatique pour une audioconférence](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) par le standard automatique de conférence pour accueillir les appelants lorsqu’ils se connectent à un numéro de téléphone pour une audioconférence. 

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide du centre d’administration équipes Microsoft**:

1. Le tableau de bord, accédez à des **réunions** > **ponts de conférence**.
2. Sélectionnez le numéro de téléphone de pont de conférence, cliquez sur **Modifier**, puis choisissez la langue par défaut.

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**:

1. Accéder au **Centre d’administration Office 365** > **Admin centres** > **équipes** > **portail hérité**.
2. Sélectionnez **conférence** > **Microsoft bridge**. 
3. Sélectionnez le numéro de téléphone de pont de conférence, sélectionnez **définir les langues**, puis choisissez la langue par défaut.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Étape 6 : Définir vos paramètres de pont de conférence
<a name="__top"> </a>
    
Après avoir configuré votre pont de conférence, vérifiez que les paramètres par défaut, tels que les notifications d’entrée/sortie et la longueur du code confidentiel sont ceux que vous souhaitez utiliser. Si ce n’est pas le cas, vous pouvez les modifier. 

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide du centre d’administration équipes Microsoft**:

1. Le tableau de bord, accédez à des **réunions** > **ponts de conférence**.
2. Sélectionnez **paramètres du pont**. Cela ouvrira le volet **Paramètres de pont**. 

Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

1. Accéder au **Centre d’administration Microsoft 365** > **Admin centres** > **équipes** > **portail hérité**.
2. Sélectionnez **conférence** > **paramètres de pont de Microsoft**. Cela ouvrira la page **Paramètres de pont Microsoft**. 

Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Étape 7: Attribuer des numéros de téléphone de connexion pour les utilisateurs qui animent des réunions

Après avoir créé un pont d’audioconférence, vous devez définir les numéros payants et gratuits de vos utilisateurs.

Vous devez effectuer cette opération pour toutes les personnes de votre entreprise qui animent ou qui planifient des réunions. 

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide du centre d’administration équipes Microsoft**:

1. Tableau de bord, cliquez sur **utilisateurs**, sélectionnez l’utilisateur dans la liste et sélectionnez **Modifier**.
2. Sélectionnez **Modifier** en regard de **Conférence Audio**, puis, dans le volet de **Conférence Audio** , choisissez un nombre dans les listes de numéros **numéro payant** et **numéro gratuit** .

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

1. Accéder au **Centre d’administration Microsoft 365** > **équipes** > **portail hérité**.
2. Sélectionnez **conférence** > **les utilisateurs**, puis sélectionnez l’utilisateur dans la liste et cliquez sur **Modifier**. 

Si vous avez besoin de plus de détails, consultez [Sélectionner Microsoft en tant que fournisseur d’audioconférences](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Étape 8 : Configuration des invitations aux réunions (facultatif)
<a name="__top"> </a>
 
Les numéros de téléphone qui sont définies pour l’utilisateur seront ajoutés automatiquement pour les invitations aux réunions qui sont envoyées aux participants à une réunion. Vous pouvez cependant ajouter vos propres liens d’aide et légaux, un texte et une petite image de l’entreprise si vous le souhaitez. Voir [Personnaliser les invitations de réunion](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Rubriques connexes

[Questions fréquentes à propos de l'audioconférence](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurer Skype entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numéros de téléphone pour l’audioconférence](phone-numbers-for-audio-conferencing.md)
  
[Définition des options pour les réunions en ligne et les téléconférences](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
