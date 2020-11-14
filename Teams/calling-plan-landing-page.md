---
title: Plans d’appel dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Déterminez le forfait d’appels du système Microsoft Phone qui fera le meilleur parti de votre organisation sur la voix Cloud dans Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71fe92646a3a2976e9a4d393e54ea56a7669b400
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031850"
---
# <a name="which-calling-plan-is-right-for-you"></a>Quelle forfait d’appels vous convient le mieux ? 

Vous avez terminé la mise en [route](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Vous avez peut-être déployé des [réunions & des conférences](deploy-meetings-microsoft-teams-landing-page.md). Vous êtes maintenant prêt à ajouter des charges de travail vocaux Cloud et vous avez décidé d’utiliser le système Microsoft Phone avec un plan d’appels pour vous connecter au réseau téléphonique public commuté (RTC). 

Cet article décrit les décisions de déploiement principales pour les offres d’appel ainsi que les autres considérations que vous pouvez configurer en fonction des besoins de votre organisation. Pour plus d’informations sur les services vocaux Cloud de Microsoft, consultez également la [voix Cloud de Microsoft teams](cloud-voice-landing-page.md) .


## <a name="learn-more-about-calling-plans"></a>En savoir plus sur les offres d’appels

Les articles suivants fournissent des informations supplémentaires sur le déploiement et l’utilisation des plans d’appel Microsoft :

- [Système téléphonique dans Microsoft 365 ou Office 365](what-is-phone-system-in-office-365.md)
- [Forfaits d’appels pour Microsoft 365 ou Office 365](calling-plans-for-office-365.md)
- [Configurer des forfaits d'appels](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Pour utiliser Microsoft comme opérateur de téléphonie, vous devez obtenir les licences de plan d’appel et les affecter aux utilisateurs de votre système téléphonique. 

Il existe deux types de plans d’appel disponibles :

- Forfaits d’appels nationaux 
- Forfaits d’appels nationaux et internationaux

|Posez-vous la question|Action |
|------------|-------|
|Les offres d’appels sont-elles disponibles dans ma région ? Quels sont les emplacements des utilisateurs disposant d’un service de plan d’appels ? | Pour plus d’informations, consultez [disponibilité du pays et de la région pour les offres d’appels audio et de services d’audioconférence](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). | 
Mes utilisateurs doivent-ils utiliser les appels internationaux ? | Pour plus d’informations, consultez la section [forfaits d’appels pour Microsoft 365 ou Office 365](calling-plans-for-office-365.md). |
Mes utilisateurs ont-ils des licences offres d’appels ? | Pour acheter et attribuer des licences, reportez-vous à la section [étape 2 : acheter et attribuer des licences](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
Mes utilisateurs ont-ils chacun un numéro de téléphone à composer directe | Pour obtenir des numéros de téléphone, reportez-vous à l' [étape 3 : obtenir des numéros de téléphone](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Transférer des numéros de téléphone vers Microsoft 365 ou Office 365

Il est facile de transférer vos numéros de téléphone de votre fournisseur de services actuel vers Teams. Lorsque vous transférez vos numéros de téléphone vers Teams, Microsoft deviendra votre fournisseur de services et vous facturera ces numéros de téléphone. Pour plus d’informations, consultez la section [transférer des numéros de téléphone vers teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


### <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Avec les offres d’appels dans Microsoft 365 ou Office 365, tous les utilisateurs de votre organisation doivent disposer d’un numéro de téléphone unique et d’une adresse de secours validée correspondante. Vous pouvez également spécifier un emplacement d’urgence dans une adresse de secours (par exemple, un numéro de téléphone ou un numéro de téléphone). 

|Posez-vous la question|Action |
|:------------|:-------|
|Comment puis-je obtenir les informations d’adresse de secours et d’emplacement ? |Pour plus d’informations, consultez [que sont les emplacements d’urgence, les adresses de secours et le routage des appels ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)


### <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone attribué en tant qu’identité d’appel (ID d’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.

|Posez-vous la question|Action |
|:------------|:-------|
|Souhaitez-vous masquer ou désactiver l’identification de l’appelant ? | Pour modifier ou bloquer l’ID de l’appelant, voir [définir l’ID d’appelant d’un utilisateur](set-the-caller-id-for-a-user.md). |
|||




