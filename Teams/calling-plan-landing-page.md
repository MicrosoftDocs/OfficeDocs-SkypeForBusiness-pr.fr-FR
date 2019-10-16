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
ms.reviewer: crowe
search.appverid: MET150
description: Page d’accueil de plan d’appels
appliesto:
- Microsoft Teams
ms.openlocfilehash: 998c0964239e430451a157bb6d8d0034fc7d19a7
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516998"
---
# <a name="which-calling-plan-is-right-for-you"></a>Quelle forfait d’appels vous convient le mieux ? 

Vous avez terminé la mise en [route](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Vous avez peut-être déployé des [réunions & des conférences](deploy-meetings-microsoft-teams-landing-page.md). Vous êtes maintenant prêt à ajouter des charges de travail vocaux Cloud et vous avez décidé d’utiliser le système Microsoft Phone avec un plan d’appels pour vous connecter au réseau téléphonique public commuté (RTC). 

Cet article décrit les décisions de déploiement principales pour les offres d’appel ainsi que les autres considérations que vous pouvez configurer en fonction des besoins de votre organisation. Pour plus d’informations sur les services vocaux Cloud de Microsoft, consultez également la [voix Cloud de Microsoft teams](cloud-voice-landing-page.md) .


## <a name="learn-more-about-calling-plans"></a>En savoir plus sur les offres d’appels

Les articles suivants fournissent des informations supplémentaires sur le déploiement et l’utilisation des plans d’appel Microsoft :

- [Système téléphonique dans Office 365](what-is-phone-system-in-office-365.md)
- [Forfaits d’appel dans Office 365](calling-plans-for-office-365.md)
- [Configurer des forfaits d'appels](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Pour utiliser Microsoft comme opérateur de téléphonie, vous devez obtenir les licences de plan d’appel et les affecter aux utilisateurs de votre système téléphonique. 

Il existe deux types de plans d’appel disponibles :

- Forfaits d’appels nationaux 
- Forfaits d’appels nationaux et internationaux

|Posez-vous la question|Action |
|------------|-------|
|Les offres d’appels sont-elles disponibles dans ma région ? Quels sont les emplacements des utilisateurs disposant d’un service de plan d’appels ? | Pour plus d’informations, consultez [disponibilité du pays et de la région pour les offres d’appels audio et de services d’audioconférence](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). | 
Mes utilisateurs doivent-ils utiliser les appels internationaux ? | Pour plus d’informations, consultez la section [forfaits d’appels pour Office 365](calling-plans-for-office-365.md). |
Mes utilisateurs ont-ils des licences offres d’appels ? | Pour acheter et attribuer des licences, reportez-vous à la section [étape 2 : acheter et attribuer des licences](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
Mes utilisateurs ont-ils chacun un numéro de téléphone à composer directe | Pour obtenir des numéros de téléphone, reportez-vous à l' [étape 3 : obtenir des numéros de téléphone](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Transférer les numéros de téléphone vers Office 365

Il est facile de transférer vos numéros de téléphone de votre fournisseur de services actuel vers Teams. Lorsque vous transférez vos numéros de téléphone vers Teams, Microsoft deviendra votre fournisseur de services et vous facturera ces numéros de téléphone. Pour plus d’informations, consultez la rubrique [transfert de numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).


### <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Avec les offres d’appels dans Office 365, chaque utilisateur de votre organisation doit disposer d’un numéro de téléphone unique et d’une adresse de secours validée correspondante. Vous pouvez également spécifier un emplacement d’urgence dans une adresse de secours (par exemple, un numéro de téléphone ou un numéro de téléphone). 

|Posez-vous la question|Action |
|:------------|:-------|
|Comment puis-je obtenir les informations d’adresse de secours et d’emplacement ? |Pour plus d’informations, consultez [que sont les emplacements d’urgence, les adresses de secours et le routage des appels ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)


### <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone attribué en tant qu’identité d’appel (ID d’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.

|Posez-vous la question|Action |
|:------------|:-------|
|Souhaitez-vous masquer ou désactiver l’identification de l’appelant ? | Pour modifier ou bloquer l’ID de l’appelant, voir [définir l’ID d’appelant d’un utilisateur](set-the-caller-id-for-a-user.md). |
|||




