---
title: Numéros de téléphone pour l'Audioconférence dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: Apprenez quels pays et quelles régions ont des numéros d'appel de conférence, et comment ils sont automatiquement affectés.
ms.openlocfilehash: daa2312350be038153db168517a1d0f5bd7023cf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299115"
---
# <a name="phone-numbers-for-audio-conferencing-in-skype-for-business-online"></a>Numéros de téléphone pour l'Audioconférence dans Skype Entreprise Online

> [!NOTE]
> Pour plus d’informations sur les numéros de téléphone dans Microsoft Teams, voir [Numéros de téléphone pour l'Audioconférence dans Microsoft Teams](/MicrosoftTeams/phone-numbers-for-audio-conferencing-in-teams).

When you are setting up **Audio Conferencing** for Skype for Business, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use the lists for **Country/Region**, **State/Region**, and **City** to filter your search. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>Couverture et tarification de l'audioconférence

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans). For pricing information, see [Pricing for Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>Numéros de téléphone d'accès à composer figurant dans l'invitation à la réunion

When a Skype for Business Online user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
Les autres numéros de connexion sont affichés en cliquant sur le lien **Rechercher un numéro local** dans l'invitation à la réunion.
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>Numéros de téléphone d’accès définis sur un pont de conférence audio

There are two types of audio conferencing phone numbers that can be assigned to your conferencing bridge: **Shared** and **Dedicated**. Both types of these numbers can be used by any caller to join audio meetings that are being held in your organization.
  
 Les **numéros de téléphone dédiés** sont les numéros disponibles uniquement pour les utilisateurs au sein de votre organisation. Vous pouvez modifier les langues utilisées lorsque quelqu'un appelle l'un de ces numéros.
  
 Les **numéros de téléphone partagés** sont des numéros qui peuvent être partagés avec d'autres organisations Office 365. Vous ne pouvez pas modifier les langues utilisées lorsque quelqu'un appelle l'un de ces numéros.
  
While the default audio conferencing number that is assigned to an organizer is only included in the meeting invite, a caller can use any of the phone numbers that are assigned to your conferencing bridge to join a meeting. The list of phone numbers that can be used to join a meeting is available using the **Find a local number** link that is included on every meeting invite.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>Numéros de téléphone de l’audioconférence assignés automatiquement

Shared audio conferencing phone numbers are automatically assigned to organizations when they're enabled for audio conferencing. When the phone numbers are assigned, a phone number is assigned as the default phone number of the conferencing bridge. The phone number assigned as the default number of the bridge will be one from the country/region of the organization.
  
> [!NOTE]
> Le pays ou la région de votre organisation est disponible en vous connectant au **Centre d’administration Office 365** et en regardant sous profil de l' **organisation**. 
  
> [!CAUTION]
> Due to limited availability of toll phone numbers in Venezuela, Indonesia, and United Arab Emirates (UAE), organizations from these countries/regions won't have an Audio Conferencing toll number automatically assigned to them. Toll-free numbers from these locations are available depending on available inventory. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers).
  
Pour voir une liste des pays/régions qui ont des numéros de téléphone automatiquement affectés aux organisations, voir [Disponibilité par pays et par région de l'Audioconférence et des Plans d’appels](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).
  
## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Pour consulter la liste des langues prises en charge pour les conférences audio, voir [langues prises en charge](/MicrosoftTeams/audio-conferencing-supported-languages)par l’audioconférence.
    
- Vous pouvez utiliser l’applet de passe [Get-csonlinedialinconferencingservicenumberhttp](https://go.microsoft.com/fwlink/?LinkId=617691) pour afficher les numéros de téléphone dédiés aux conférences audio pour votre organisation.
    
- L'applet de commande [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) permet d'afficher la liste des langues qui peuvent être définies sur un numéro de téléphone à composer dédié.
    
- You can set up to four languages for each audio conferencing phone number - one primary and three secondary. And you can also set languages on a dedicated audio conferencing phone number.
    
- Pour définir le numéro de téléphone à composer pour un utilisateur, reportez-vous à [la rubrique définition des numéros de téléphone inclus dans](set-the-phone-numbers-included-on-invites.md)les invitations.
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Voir aussi

[Tester ou acheter l’audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
