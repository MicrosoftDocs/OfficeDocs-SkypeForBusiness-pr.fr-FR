---
title: Informations de référence sur les applets de commande PowerShell pour les standards automatiques et les files d’attente d’appels
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Phone System
- seo-marvel-apr2020
description: Consultez cet article pour les applets de commande PowerShell afin de créer et de gérer des standards automatiques et des files d’attente d’appels dans Microsoft Teams.
ms.openlocfilehash: 7970a3c8199060d73d68e5f94c28dfe836688189
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269407"
---
# <a name="powershell-cmdlet-reference-for-auto-attendants-and-call-queues"></a>Informations de référence sur les applets de commande PowerShell pour les standards automatiques et les files d’attente d’appels

Les références d’applets de commande suivantes concernent les standards automatiques Microsoft Teams et les files d’attente d’appels.

## <a name="auto-attendant-cmdlets"></a>Applets de commande de standard automatique

Les applets de commande suivantes vous permettent de gérer les standards automatiques :

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Update-CsAutoAttendant](/powershell/module/skype/update-csautoattendant)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [Nouvelle CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [Nouvelle CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [Nouvelle CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csautoattendantholidays)
- [New-CsAutoAttendantDialScope](/powershell/module/skype/New-CsAutoAttendantDialScope)
- [New-CsAutoAttendantPrompt](/powershell/module/skype/New-CsAutoAttendantPrompt)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)
- [New-CsAutoAttendantMenuOption](/powershell/module/skype/New-CsAutoAttendantMenuOption)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/powershell/module/skype/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/powershell/module/skype/Get-CsAutoAttendantTenantInformation)

Pour obtenir un guide pas à pas sur la création de standards automatiques avec PowerShell, consultez [Création de standards automatiques avec des applets de commande PowerShell](create-a-phone-system-auto-attendant-via-cmdlets.md)

## <a name="call-queue-cmdlets"></a>Cmdlets de files d’attente des appels

Les applets de commande suivantes vous permettent de gérer une file d’attente d’appels :

- [New-CsCallQueue](/powershell/module/skype/New-CsCallQueue)
- [Get-CsCallQueue](/powershell/module/skype/Get-CsCallQueue)
- [Set-CsCallQueue](/powershell/module/skype/Set-CsCallQueue)
- [Remove-CsCallQueue](/powershell/module/skype/Remove-CsCallQueue)

Pour obtenir un guide pas à pas sur la création de files d’attente d’appels avec PowerShell, consultez [Création de files d’attente d’appels avec des applets de commande PowerShell](create-a-phone-system-call-queue-via-cmdlets.md)

## <a name="common-cmdlets-used-by-both-auto-attendants-and-call-queues"></a>Applets de commande courantes utilisées par les standards automatiques et les files d’attente d’appels

Les applets de commande suivantes sont également nécessaires pour gérer les utilisateurs, les comptes de ressources, les licences Téléphonie Microsoft Teams, les numéros de téléphone, les fichiers audio et le langage pris en charge qui seront utilisés avec les standards automatiques :

### <a name="users-and-teams"></a>Utilisateurs et Teams

- Utilisateurs
  - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Équipes:
  - [Get-Team](/powershell/module/teams/Get-Team)
  - [Get-TeamChannel](/powershell/module/teams/Get-TeamChannel)

### <a name="resource-accounts"></a>Comptes de ressources

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

### <a name="teams-phone-resource-account-licenses"></a>Licences de compte de ressources de téléphone Teams

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

### <a name="phone-number-assignment"></a>Affectation de numéro de téléphone

- [Get-CsPhoneNumberAssignment](/powershell/module/teams/Get-CsPhoneNumberAssignment)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment)

### <a name="audio-files"></a>Fichiers audio

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

### <a name="support-languages-and-time-zones"></a>Langues et fuseaux horaires de prise en charge

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
