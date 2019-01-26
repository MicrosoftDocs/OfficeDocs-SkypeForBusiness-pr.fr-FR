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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Découvrez comment configurer les conférences rendez-vous ou audio pour les personnes de votre entreprise qui souhaitent participer à des téléconférences à l’aide d’un téléphone. '
ms.openlocfilehash: 5d069822bf818db63ed35545a34a0bfa2eeee672
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562667"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurer la conférence Audio pour Skype entreprise et Teams Microsoft

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Pour trouver les questions fréquemment posées à propos des audioconférences, consultez [Questions courantes concernant les audioconférences](/MicrosoftTeams/audio-conferencing-common-questions).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Étape 1 : Déterminez si les audioconférence sont disponibles dans votre pays/région
<a name="__top"> </a>


Allez à la page [Disponibilité des pays et des régions pour les audioconférences et les forfaits d’appel](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) et sélectionnez votre pays ou région pour obtenir des informations de disponibilité sur les audioconférences, ainsi que des informations sur le système téléphonique, les forfaits d’appel, les numéros payants et gratuits et les crédits de communications. 
 
## <a name="step-2-get-and-assign-licenses"></a>Étape 2 : Obtenir et attribuer des licences
 
1. For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. After you buy the Audio Conferencing licenses, you will ned to assign them to those people in your organization who are going to schedule or lead meetings. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.
    
3. We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step. To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).
    
> [!NOTE]
> You can also set up pay-per-minute Audio Conferencing. Go [here](/microsoftteams/audio-conferencing-pay-per-minute) to find out more about how to use them.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Étape 3 : Obtenir les numéros de service pour vos ponts de conférence
<a name="__top"> </a>

For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers. You can get either toll or toll-free service numbers for your conferencing bridges. There are three ways to get toll and toll-free service numbers: 
  
- **Use the Skype for Business admin center.** For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center, see [Getting service phone numbers](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Port your existing service numbers.** To port or transfer existing numbers from your current service provider or phone carrier to Office 365. You can see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.  
  
- **Use a request form for new numbers.** Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes. If so, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information. 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Étape 4 : Affecter un numéro de service pour le pont de conférence
<a name="__top"> </a>

Une fois que vous obtenez vos numéros de téléphone payants et/ou gratuits pour le pont de conférence, vous devez les assigner afin qu’ils puissent être utilisés pour les invitations aux réunions.  

Affecter un nouveau numéro de téléphone à votre pont d’audioconférence :

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

 Accéder au **Centre d’administration Office 365** > **Admin centres** > **Skype pour les entreprises** > **vocale** > de**numéros de téléphone**, sélectionnez le numéro de téléphone, puis cliquez sur **affecter**.

Pour plus d’informations, consultez la rubrique [Modifier les numéros de téléphone sur votre pont d’audioconférence](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Étape 5 : Définir les langues par défaut et alternatives pour un pont de conférence
<a name="__top"> </a>

Ensuite, vous devez [Définir les langues du standard automatique pour les audioconférences](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) que le standard automatique de la conférence utilisera pour accueillir les appelants lorsqu’ils se connecteront à un numéro de téléphone pour une audioconférence. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**

Depuis le tableau de bord, accédez à **Réunions** > **Ponts de conférence**, sélectionnez le numéro de téléphone de pont de conférence, cliquez sur **Modifier**, puis choisissez la langue par défaut.

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

Accéder au **Centre d’administration Office 365** > **Admin centres** > **Skype pour les entreprises** > **audioconférence** > **Microsoft bridge**, sélectionnez le numéro de téléphone de pont de conférence, puis cliquez sur ** Définir les langues**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Étape 6 : Définir vos paramètres de pont de conférence
<a name="__top"> </a>
    
Après avoir configuré votre pont de conférence, vérifiez que les paramètres par défaut, tels que les notifications d’entrée/sortie et la longueur du code confidentiel sont ceux que vous souhaitez utiliser. Si ce n’est pas le cas, vous pouvez les modifier. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**

From the Dashboard, go to **Meetings** > **Conference bridges** > **Bridge settings**. This will open the **Bridge settings** pane. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

Go to the **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** > **Microsoft bridge settings**. This will open the **Microsoft bridge settings** page. For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Étape 7: Attribuer des numéros de téléphone de connexion pour les utilisateurs qui animent des réunions

Après avoir créé un pont d’audioconférence, vous devez définir les numéros payants et gratuits de vos utilisateurs.

You will need to do this for all of the people in your organization who lead or schedule meetings. To do this:

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**

Dans le tableau de bord, cliquez sur **Utilisateurs**, sélectionnez l’utilisateur dans la liste, cliquez sur **Modifier**, cliquez sur **Modifier** à côté de **Audioconférence**, puis dans le volet **Audioconférence**, choisissez un numéro dans les listes de **numéros payants** et de **numéros gratuits**.

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration :**

Go to the **Office 365 admin center** > **Skype for Business** > **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**. If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Étape 8 : Configuration des invitations aux réunions (facultatif)
<a name="__top"> </a>
 
The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees. However, you can add your own help and legal links, a text message, and small company graphic if you want. See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Rubriques connexes

[Questions fréquentes à propos de l'audioconférence](/MicrosoftTeams/audio-conferencing-common-questions)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numéros de téléphone pour l'audioconférence](phone-numbers-for-audio-conferencing.md)
  
[Définition des options pour les réunions en ligne et les téléconférences](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
