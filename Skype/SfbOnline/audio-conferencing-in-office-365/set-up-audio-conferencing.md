---
title: Configurer l’audioconférence pour Skype Entreprise
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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
- O365P_DialInConfDesc
description: 'Découvrez comment configurer la Conférence rendez-vous ou l’Audioconférence pour les membres de votre entreprise qui doivent utiliser un téléphone pour participer à des téléconférences. '
ms.openlocfilehash: 55edb015df6e0faf77eb644246677f637b7bace7
ms.sourcegitcommit: cf2f96dbd485ac4cc822c5a591ccce6b47f12cc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456554"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a>Configurer l’audioconférence pour Skype Entreprise

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Parfois, des personnes de votre organisation devront utiliser un téléphone pour rejoindre une réunion. Skype Entreprise inclut uniquement la fonction d’audioconférence pour cette situation ! Les personnes peuvent se rendre par téléphone Skype Entreprise réunions à l’aide d’un téléphone, au lieu d’utiliser l’application Skype Entreprise sur un appareil mobile ou un PC. 
  
Il vous suffit de configurer la fonctionnalité de conférence audio pour les utilisateurs qui comptent planifier ou organiser des réunions. Les participants à la réunion qui se connectent n’ont pas besoin de licence ou de configuration particulière.
  
Pour trouver les questions fréquemment posées à propos des audioconférences, consultez [Questions courantes concernant les audioconférences](/MicrosoftTeams/audio-conferencing-common-questions).

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Étape 1 : Déterminez si les audioconférence sont disponibles dans votre pays/région
<a name="__top"> </a>

Allez à la page [Disponibilité des pays et des régions pour les audioconférences et les forfaits d’appel](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) et sélectionnez votre pays ou région pour obtenir des informations de disponibilité sur les audioconférences, ainsi que des informations sur le système téléphonique, les forfaits d’appel, les numéros payants et gratuits et les crédits de communications. 
 
## <a name="step-2-get-and-assign-licenses"></a>Étape 2 : Obtenir et attribuer des licences
 
1. Pour une audioconférence, vous avez besoin d’une licence pour chaque utilisateur qui établira des réunions. Pour connaître les licences que vous devez acheter pour AudioConférence et leurs prix, consultez la Skype Entreprise [de modules supplémentaires.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

    >[!NOTE] 
    > La fonctionnalité audioconférence est incluse dans les licences Office 365 Entreprise E5 et en tant que composant additionnel.
        
2. Une fois que vous avez acheté les licences d’audioconférence, vous devez les attribuer aux personnes qui vont planifier ou animer des réunions. Pour [plus d’Applications Microsoft 365 pour les PME,](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) voir Attribuer ou supprimer des licences pour les personnes de votre organisation qui vont planifier ou diriger des réunions.
    
3. Nous vous recommandons également d’affecter des licences de crédits de communications (elles ne coûtent rien) aux mêmes personnes à qui vous avez attribué des licences à l’étape précédente. Pour savoir comment configurer les Crédits de communications, voir [Configurer les Crédits de communications pour votre entreprise](/microsoftteams/set-up-communications-credits-for-your-organization).
    
   > [!NOTE]
   > Vous pouvez également configurer les [audioconférences en mode « payer à la minute »](/microsoftteams/audio-conferencing-pay-per-minute).

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Étape 3 : Obtenir les numéros de service pour vos ponts de conférence
<a name="__top"> </a>

Pour les audioconférences, vous ne pouvez pas utiliser les numéros de téléphone pour les utilisateurs ; vous devez leur obtenir des numéros de service. Vous pouvez obtenir des numéros de service payants ou gratuits pour vos ponts de conférence. Il existe trois façons d’obtenir des numéros de service payants et gratuits  : 
  
- **Utilisez le centre Skype Entreprise d’administration de l’utilisateur.** Pour certains pays ou certaines régions, vous pouvez obtenir des numéros de service pour vos ponts de conférence à l’aide du Skype Entreprise d’administration. Voir [Obtention de numéros de téléphone de service](/microsoftteams/getting-service-phone-numbers).
    
- **Portage de vos numéros de service existants**. Pour porter ou transférer des numéros existants de votre fournisseur de service ou de votre téléphone actuel vers Microsoft 365 ou Office 365. Vous pouvez consulter [Transfert des numéros de téléphone vers Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) ou [Gestion des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization) pour plus d’informations pour vous aider à effectuer ces opérations.  
  
- **Utiliser un formulaire de demande pour de nouveaux numéros**. Parfois (selon votre pays/région) vous ne pourrez pas obtenir vos nouveaux numéros de service à l’aide du Centre d’administration Skype Entreprise ou vous aurez besoin de numéros de téléphone ou indicatifs régionaux spécifiques. Si c'est le cas, vous devrez télécharger un formulaire et nous le renvoyer. Pour plus d’informations, voir [Gestion des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Étape 4 : Affecter un numéro de service pour le pont de conférence
<a name="__top"> </a>

Une fois que vous obtenez vos numéros de téléphone payants et/ou gratuits pour le pont de conférence, vous devez les assigner afin qu’ils puissent être utilisés pour les invitations aux réunions.  

Affecter un nouveau numéro de téléphone à votre pont d’audioconférence :

![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) **À l’aide Skype Entreprise centre d’administration :**

 1. Accédez au **Centre d’administration Microsoft 365** > **Centres d’administration** > **Teams** > **Portail de l'héritage**.
 2. Sélectionnez **Voice** > **Numéros de téléphone**.
 3. Sélectionnez le numéro de téléphone, puis cliquez sur **Affecter**.

Pour plus d’informations, consultez la rubrique [Modifier les numéros de téléphone sur votre pont d’audioconférence](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Étape 5 : Définir les langues par défaut et alternatives pour un pont de conférence
<a name="__top"> </a>

Vous pouvez ensuite définir les [langues](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) du attendant automatique pour l’audioconférence que le attendant de conférence utilise pour accueillir les appelants lorsqu’ils appellent un numéro de téléphone pour l’audioconférence. 

![Icône représentant le Microsoft Teams logo.](../images/teams-logo-30x30.png) **À l’aide Microsoft Teams centre d’administration :**

1. Depuis votre domicile, vers des **ponts de conférence**  >  **Réunions.**
2. Sélectionnez le numéro de téléphone de pont de conférence, cliquez sur **Modifier**, puis choisissez la langue par défaut.

![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) **À l’aide Skype Entreprise centre d’administration :**

1. Allez dans le Centre d’administration > **centres d’administration**  >  **Teams**  >  **portail hérité.**
2. Sélectionnez **Audioconférences**  >  **Pont Microsoft.** 
3. Sélectionnez le numéro de téléphone du pont de conférence, sélectionnez Définir les **langues,** puis choisissez la langue par défaut.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Étape 6 : Définir vos paramètres de pont de conférence
<a name="__top"> </a>
    
Après avoir configuré votre pont de conférence, vérifiez que les paramètres par défaut, tels que les notifications d’entrée/sortie et la longueur du code confidentiel sont ceux que vous souhaitez utiliser. Si ce n’est pas le cas, vous pouvez les modifier. 

![Icône représentant le Microsoft Teams logo.](../images/teams-logo-30x30.png) **À l’aide Microsoft Teams centre d’administration :**

1. Depuis votre domicile, vers des **ponts de conférence**  >  **Réunions.**
2. Sélectionnez **Paramètres de Bridge**. Cela ouvrira le volet **Paramètres de pont**. 

Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) **À l’aide Skype Entreprise centre d’administration :**

1. Accédez au **Centre d’administration Microsoft 365** > **Centres d’administration** > **Teams** > **Portail de l'héritage**.
2. Sélectionnez **Les paramètres du pont** Microsoft de  >  **l’audioconférence.** Cela ouvrira la page **Paramètres de pont Microsoft**. 

Pour plus d’informations, voir [Changement des paramètres de pont d’audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Étape 7: Attribuer des numéros de téléphone de connexion pour les utilisateurs qui animent des réunions

Après avoir créé un pont d’audioconférence, vous devez définir les numéros payants et gratuits de vos utilisateurs.

Vous devez effectuer cette opération pour toutes les personnes de votre entreprise qui animent ou qui planifient des réunions. 

![Icône représentant le Microsoft Teams logo.](../images/teams-logo-30x30.png) **À l’aide Microsoft Teams centre d’administration :**

1. À partir de la page **d’accueil,** cliquez sur Utilisateurs, sélectionnez l’utilisateur dans la liste, puis sélectionnez **Modifier.**
2. Sélectionnez **Modifier** à côté de **Audioconférence**, puis dans le volet **Audioconférence**, choisissez un numéro dans les listes de **numéros payants** et de **numéros gratuits**.

![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) **À l’aide Skype Entreprise centre d’administration :**

1. Go to the **Centre d'administration Microsoft 365**  >  **Teams**  >  **legacy portal.**
2. Sélectionnez **Utilisateurs de l’audioconférence,** sélectionnez l’utilisateur dans la liste  >  et cliquez sur **Modifier.** 

Si vous avez besoin de plus de détails, consultez [Sélectionner Microsoft en tant que fournisseur d’audioconférences](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Étape 8 : Configuration des invitations aux réunions (facultatif)
<a name="__top"> </a>
 
Les numéros de connexion définis pour l'utilisateur seront ajoutés automatiquement aux invitations envoyées aux participants à la réunion. Vous pouvez cependant ajouter vos propres liens d’aide et légaux, un texte et une petite image de l’entreprise si vous le souhaitez. Voir [Personnaliser les invitations aux réunions](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Sujets associés

[Questions fréquentes à propos de l’audioconférence](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurer Skype entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numéros de téléphone pour l’audioconférence](phone-numbers-for-audio-conferencing.md)
  
[Définition des options pour les réunions en ligne et les téléconférences](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
