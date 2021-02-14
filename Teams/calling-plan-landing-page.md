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
description: Déterminez quel plan d’appel système Microsoft Phone sera le plus efficace pour votre organisation sur Cloud Voice dans Teams.
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

Vous avez terminé la [mise en place.](get-started-with-teams-quick-start.md) Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Vous avez peut-être déployé [des réunions & conférences.](deploy-meetings-microsoft-teams-landing-page.md) Vous êtes maintenant prêt à ajouter des charges de travail vocales dans le cloud et vous avez décidé d’utiliser Microsoft Phone System avec le plan d’appel pour vous connecter au réseau téléphonique commuté (PSTN). 

Cet article décrit les principales décisions de déploiement pour les plans d’appels, ainsi que des considérations supplémentaires que vous pouvez configurer en fonction des besoins de votre organisation. Pour plus d’informations sur les offres vocales cloud de Microsoft, vous devez également lire cloud Voice dans [Microsoft Teams.](cloud-voice-landing-page.md)


## <a name="learn-more-about-calling-plans"></a>En savoir plus sur les forfaits d’appels

Les articles suivants fournissent des informations supplémentaires sur le déploiement et l’utilisation des plans d’appel Microsoft :

- [Système téléphonique dans Microsoft 365 ou Office 365](what-is-phone-system-in-office-365.md)
- [Forfaits d’appels pour Microsoft 365 ou Office 365](calling-plans-for-office-365.md)
- [Configurer des forfaits d'appels](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Pour utiliser Microsoft comme opérateur de téléphonie, vous devez obtenir des licences Forfait d’appels et les affecter à vos utilisateurs Phone System. 

Deux types de forfaits d’appels sont disponibles :

- Forfaits d’appels nationaux 
- Forfaits d’appels nationaux et internationaux

|Posez-vous la question|Action |
|------------|-------|
|Des forfaits d’appels sont-ils disponibles dans ma région ? Quels emplacements utilisateur auront le service Forfait d’appels ? | Pour plus d’informations, consultez la disponibilité des pays et régions pour les plans [d’audioconférence et d’appel.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) | 
Mes utilisateurs ont-ils besoin d’appels internationaux ? | Pour plus d’informations, [voir Forfaits d’appels pour Microsoft 365 ou Office 365.](calling-plans-for-office-365.md) |
Mes utilisateurs ont-ils des licences Forfaits d’appels ? | Pour acheter et attribuer des licences, voir [l’étape 2 : acheter et attribuer des licences.](set-up-calling-plans.md#step-2-buy-and-assign-licenses) |
Mes utilisateurs ont-ils chacun un numéro de téléphone directement vers l’intérieur ? | Pour obtenir des numéros de téléphone, voir [l’étape 3 : obtenir des numéros de téléphone.](set-up-calling-plans.md#step-3-get-phone-numbers) |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Transférer des numéros de téléphone vers Microsoft 365 ou Office 365

Il est facile de transférer vos numéros de téléphone de votre fournisseur de services actuel vers Teams. Une fois vos numéros de téléphone portés vers Teams, Microsoft devient votre fournisseur de services et vous facture pour ces numéros de téléphone. Pour plus d’informations, voir [Transférer des numéros de téléphone dans Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)


### <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Avec les forfaits d’appels dans Microsoft 365 ou Office 365, chaque utilisateur de votre organisation doit avoir un numéro de téléphone à composer directement vers l’intérieur et une adresse de secours validée correspondante. Vous pouvez également spécifier un emplacement d’urgence à l’intérieur de l’adresse de secours (par exemple, un numéro de bureau ou un numéro d’étage). 

|Posez-vous la question|Action |
|:------------|:-------|
|Comment puis-je obtenir les informations détaillées sur l’adresse d’urgence et l’emplacement ? |Pour plus d’informations, voir Que sont les [emplacements d’urgence,](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)les adresses de secours et le routage des appels ?


### <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone affecté comme identité d’appel (ID de l’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.

|Posez-vous la question|Action |
|:------------|:-------|
|Dois-je masquer ou désactiver l’ID de l’appelant ? | Pour modifier ou bloquer l’ID d’appelant, consultez définir l’ID d’appelant [d’un utilisateur.](set-the-caller-id-for-a-user.md) |
|||




