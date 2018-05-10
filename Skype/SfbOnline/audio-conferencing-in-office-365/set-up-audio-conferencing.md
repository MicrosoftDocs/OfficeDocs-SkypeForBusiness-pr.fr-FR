---
title: Configurer la conférence Audio pour Skype entreprise et Teams Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Découvrez comment configurer les conférences rendez-vous ou audio pour les personnes de votre entreprise qui souhaitent participer à des téléconférences à l’aide d’un téléphone. '
ms.openlocfilehash: d91a3637a0f7d35d319368017e0f9c6611faf2a7
ms.sourcegitcommit: 4e9574c8a9eac270135684aa4a8b77621aa46403
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurer la conférence Audio pour Skype entreprise et Teams Microsoft

Parfois, les membres de votre organisation devront utiliser un téléphone pour composer le numéro de la réunion. Skype pour les entreprises et Microsoft Teams inclure la fonctionnalité de conférence audio uniquement cette situation ! Personnes peuvent appeler Skype pour les réunions Microsoft Teams ou de l’entreprise à l’aide d’un téléphone, au lieu d’utiliser le Skype pour une application Microsoft Teams ou de l’entreprise sur un appareil mobile ou un PC. 
  
Vous devez configurer la conférence Audio pour les personnes qui envisagent de planifier ou entraîner des réunions uniquement. Participants à la réunion qui se connectent n’avez pas besoin des licences affectés à leur ou un autre programme d’installation.
  
Pour des questions fréquemment posées à propos des conférences Audio, voir [questions courantes de conférence Audio](audio-conferencing-common-questions.md).
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Étape 1 : Déterminer si une conférence Audio est disponible dans votre pays/région
<a name="__top"> </a>


Accédez à la [disponibilité de pays et de région de conférence Audio et des Plans de l’appel](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) et sélectionnez votre pays ou région pour obtenir des informations de disponibilité sur la conférence Audio, ainsi que des informations sur le numéro payant système téléphonique, l’appel des Plans et numéro gratuit les numéros et crédits Communications. 
 
## <a name="step-2-get-and-assign-licenses"></a>Étape 2 : Obtenir et attribuer des licences
 
1. Pour une audioconférence, vous avez besoin d’une licence pour chaque utilisateur qui définira des réunions de rendez-vous. Pour savoir quelle licence vous devez acheter pour l’audioconférence et comment leur coût, consultez [Skype pour les licences d’entreprise et les équipes Microsoft module complémentaire](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. Une fois que vous achetez les licences de conférence Audio, vous allez ned pour les attribuer aux personnes de votre organisation qui sont sur le point de planifier ou entraîner des réunions. Voir [affecter ou supprimer des licences pour Office 365 pour entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) vous avez acheté pour les personnes de votre organisation qui sont sur le point à des réunions de planification ou responsable.
    
3. Nous vous recommandons également d’affecter des licences Communications crédits (ils ne coûtant rien) aux mêmes personnes, vous avez affecté des licences à l’étape précédente. Pour savoir comment configurer les Communications crédits, voir [configurer les Communications crédits pour votre organisation](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> Vous pouvez également configurer audioconférence salaire par minute. Accédez [ici](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md) pour en savoir plus sur la façon de les utiliser.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Étape 3 : Obtenir les numéros de service pour les ponts de conférence
<a name="__top"> </a>

Pour une audioconférence, vous ne pouvez pas utiliser les numéros de téléphone pour les utilisateurs ; Vous devez obtenir les numéros de service. Vous pouvez obtenir des numéros de service gratuit ou payant pour les ponts de conférence. Il existe trois façons de get payant et gratuit service numéros : 
  
- **Utilisez le Skype entreprise centre d’administration.** Pour certains pays/régions, vous pouvez obtenir les numéros de service pour les ponts de conférence à l’aide de la Skype entreprise centre d’administration, voir les [numéros de téléphone de mise en service](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Port vos numéros de service existante.** Port ou transférer des nombres existants à partir de votre fournisseur de services en cours ou votre opérateur mobile à Office 365. Vous pouvez voir le [transfert des numéros de téléphone vers Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) ou [Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) pour plus d’informations pour vous aider à effectuer cette opération.  
  
- **Utiliser un formulaire de demande pour les nouveaux numéros.** Parfois (en fonction de votre pays/région) vous ne pourrez pas obtenir vos nouveaux numéros de service à l’aide de la Skype entreprise centre d’administration, ou vous devez numéros de téléphone spécifiques ou les codes de zone. Dans ce cas, vous devez télécharger un formulaire et nous le renvoyer. Pour plus d’informations, voir [Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) . 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Étape 4 : Affecter un numéro de service pour le pont de conférence
<a name="__top"> </a>

Une fois que vous obtenez votre numéro payant et/ou de vos numéros de téléphone pour le pont de conférence, vous devez lui assigner les numéros afin qu’ils puissent être utilisées dans les invitations aux réunions.  

Pour affecter un nouveau numéro de téléphone à votre pont de conférence audio :

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

 Accéder au **Centre d’administration Office 365** > **Admin centres** > **Skype pour les entreprises** > **vocale** > de**numéros de téléphone**, sélectionnez le numéro de téléphone, puis cliquez sur **affecter**.

Pour plus d’informations, voir [attribuer un nouveau numéro de téléphone à votre pont de conférence audio](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Étape 5 : Définir les langues de remplacement pour un pont de conférence par défaut
<a name="__top"> </a>

Ensuite, vous souhaitez [définir des langues de standard automatique pour une audioconférence](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) par le standard automatique de conférence pour accueillir un appelant lorsqu’ils se connectent à un numéro de téléphone pour une audioconférence. 

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide de Skype les Teams Microsoft Business centre d’administration :**

Le tableau de bord, accédez à des **réunions** > **ponts de conférence**, sélectionnez le numéro de téléphone de pont de conférence, cliquez sur **Modifier**, puis choisissez la langue par défaut.

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

Accéder au **Centre d’administration Office 365** > **Admin centres** > **Skype pour les entreprises** > **audioconférence** > **paramètres du pont Microsoft**, sélectionnez le numéro de téléphone de pont de conférence, puis Cliquez sur **définir les langues**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Étape 6 : Définir les paramètres de pont de votre conférence
<a name="__top"> </a>
    
Après avoir configuré votre pont de conférence, vérifiez que les paramètres par défaut, tels que des notifications d’entrée/sortie et de la longueur du code confidentiel sont celles que vous souhaitez utiliser. Si elles ne sont pas, vous pouvez les modifier. 

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide de Skype les Teams Microsoft Business centre d’administration :**

Le tableau de bord, accédez à des **réunions** > **ponts de conférence** > **paramètres du pont**. Le volet **paramètres du pont** s’ouvre. Pour plus d’informations, voir [Modifier les paramètres d’un pont de conférence Audio](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

Accéder au **Centre d’administration Office 365** > **Admin centres** > **Skype pour les entreprises** > **audioconférence** > **paramètres de pont de Microsoft**. La page **paramètres du pont Microsoft** s’ouvre. Pour plus d’informations, voir [Modifier les paramètres d’un pont de conférence Audio](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Étape 7 : Attribuer rendez-vous numéros pour les utilisateurs qui ouvrent des réunions

Après avoir créé un pont de conférence Audio, vous devez définir la payants et gratuits pour vos utilisateurs.

Vous devez effectuer cette opération pour toutes les personnes de votre organisation qui avance ou planifier des réunions. Pour ce faire :

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide de Skype les Teams Microsoft Business centre d’administration :**

Du tableau de bord, cliquez sur **utilisateurs**, sélectionnez l’utilisateur dans la liste, cliquez sur **Modifier**, cliquez sur **Modifier** en regard de **Conférence Audio**et puis, dans le volet de **Conférence Audio** , choisissez un nombre dans le **numéro de téléphone payant** et ** Numéro gratuit** nombre de listes.

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

Accéder au **Centre d’administration Office 365** > **Skype pour les entreprises** > **audioconférence** > **les utilisateurs**, puis sélectionnez l’utilisateur dans la liste et cliquez sur **Modifier**. Si vous avez besoin de plus de détails, voir [Attribuer de Microsoft en tant que le fournisseur de services d’audioconférence](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Étape 8 : Configurer des invitations aux réunions (facultatif)
<a name="__top"> </a>
 
Les numéros de téléphone qui sont définies pour l’utilisateur seront ajoutés automatiquement pour les invitations aux réunions qui sont envoyées aux participants à une réunion. Toutefois, vous pouvez ajouter votre propre aide et des liens juridiques, un message texte et graphique de petite entreprise si vous le souhaitez. Voir [Personnaliser les invitations de réunion](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Rubriques connexes

[Questions fréquentes à propos de l'audioconférence](audio-conferencing-common-questions.md)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numéros de téléphone pour l'audioconférence](phone-numbers-for-audio-conferencing.md)
  
[Définir les options pour les réunions en ligne et les téléconférences](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
