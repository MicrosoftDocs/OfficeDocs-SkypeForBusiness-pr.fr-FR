---
title: Plans d’appel dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Appel de Plan de page d’accueil
appliesto:
- Microsoft Teams
ms.openlocfilehash: d85546df76b7699986d28152ff08003612df8331
ms.sourcegitcommit: d4b007b88469a820595ecdcf2a90854ecefe2809
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2019
ms.locfileid: "34108754"
---
# <a name="which-calling-plan-is-right-for-you"></a>Planifier les appel est fait pour vous ? 

Vous avez terminé la [mise en route](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Peut-être que vous avez déployé la [conférence & de réunions](deploy-meetings-microsoft-teams-landing-page.md). Vous êtes maintenant prêt à ajouter des charges de travail de voix dans le cloud, et vous avez décidé d’utiliser le système téléphonique de Microsoft avec l’appel de planifier pour se connecter à la Public téléphone réseau commuté (RTC). 

Cet article décrit les décisions de déploiement principaux pour appeler des Plans ainsi que les considérations supplémentaires que vous souhaiterez peut-être configurer, en fonction des besoins de votre organisation. Vous devez également lire [Cloud vocale dans les équipes Microsoft](cloud-voice-landing-page.md) pour plus d’informations sur les offres de voix de cloud de Microsoft.


## <a name="learn-more-about-calling-plans"></a>Pour plus d’informations sur les Plans de l’appel

Les articles suivants fournissent plus d’informations sur le déploiement et à l’aide de l’appel des Plans de Microsoft :

- [Système téléphonique dans Office 365](what-is-phone-system-in-office-365.md)
- [Forfaits d’appel dans Office 365](calling-plans-for-office-365.md)
- [Configurer des forfaits d'appels](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Pour utiliser Microsoft en tant que votre opérateur de téléphonie, vous devez obtenir des licences de l’appel de planifier et les attribuer aux utilisateurs de votre système téléphonique. 

Il existe deux types de Plans de l’appel :

- Plans d’appel interne 
- Plans d’appel nationales et internationales

|Posez-vous la question|Action |
|------------|-------|
|Sont des Plans de l’appel de disponibles dans mon domaine ? Les emplacements de l’utilisateur aura l’appel de planifier le service ? | Pour plus d’informations, voir [disponibilité pays et aux régions de conférence Audio et des Plans de l’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). | 
Les utilisateurs doivent-ils appels internationaux ? | Pour plus d’informations, voir [Appel Plans pour Office 365](calling-plans-for-office-365.md). |
Mes utilisateurs ont-ils des Plans de l’appel de licences ? | Pour acheter et affecter des licences, voir [étape 2 : acheter et attribuer des licences](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
Mes utilisateurs ont les directe à l’intérieur de numérotation de numéro de téléphone (DID) ? | Pour obtenir les numéros de téléphone, voir [étape 3 : obtenir les numéros de téléphone](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Transférer les numéros de téléphone vers Office 365

Il est facile à transférer vos numéros de téléphone de votre fournisseur de services en cours vers les équipes. Une fois que vous le port vos numéros de téléphone aux équipes, Microsoft deviendra votre fournisseur de services et vous facture pour ces numéros de téléphone. Pour plus d’informations, voir [transférer des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).


### <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Avec des Plans de l’appel dans Office 365, tous les utilisateurs de votre organisation doit disposer d’un unique SDA direct (SDA) numéro de téléphone une adresse d’urgence validée correspondante. Vous pouvez également spécifier un emplacement d’urgence au sein de l’adresse d’urgence (par exemple, un numéro de bureau ou numéro d’étage). 

|Posez-vous la question|Action |
|:------------|:-------|
|Niveau de détail voulez-vous les informations d’adresse et l’emplacement d’urgence à ? |Pour plus d’informations, voir [Quels sont les emplacements d’urgence, les adresses et le routage des appels ?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).


### <a name="calling-identity"></a>Identité de l’appelant

Par défaut, tous les appels sortants utilisent le numéro de téléphone affecté comme identité de l’appelante (ID de l’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.

|Posez-vous la question|Action |
|:------------|:-------|
|Je veux masquer ou désactiver l’ID de l’appelant | Pour modifier ou bloquer l’ID d’appelant, voir [définir l’ID d’appelant pour un utilisateur](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user). |
|||




