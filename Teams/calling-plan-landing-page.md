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
description: Déterminez le plan d’appel du système téléphonique Microsoft qui servira le mieux votre organisation sur Cloud Voice dans Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e11c6f6cbb53808ba259afd90420ac9855c9731d
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682473"
---
# <a name="which-calling-plan-is-right-for-you"></a>Quelle forfait d’appels vous convient le mieux ?

Vous avez terminé la prise [en main](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Vous avez peut-être déployé [des réunions & conférence](deploy-meetings-microsoft-teams-landing-page.md). Vous êtes maintenant prêt à ajouter des charges de travail de voix cloud et vous avez décidé d’utiliser Microsoft Phone System avec forfait d’appels pour vous connecter au réseau téléphonique commuté (RTC).

Cet article décrit les principales décisions de déploiement pour les forfaits d’appels, ainsi que des considérations supplémentaires que vous pouvez configurer, en fonction des besoins de votre organisation. Vous devez également lire [Cloud Voice dans Microsoft Teams](cloud-voice-landing-page.md) pour plus d’informations sur les offres de voix cloud de Microsoft.

## <a name="learn-more-about-calling-plans"></a>En savoir plus sur les forfaits d’appels

Les articles suivants fournissent plus d’informations sur le déploiement et l’utilisation des plans d’appel Microsoft :

- [Système téléphonique dans Microsoft 365 ou Office 365](what-is-phone-system-in-office-365.md)
- [Forfaits d’appels pour Microsoft 365 ou Office 365](calling-plans-for-office-365.md)
- [Configurer des forfaits d'appels](set-up-calling-plans.md)

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Pour utiliser Microsoft comme opérateur de téléphonie, vous devez obtenir des licences de forfait d’appels et les attribuer à vos utilisateurs du système téléphonique.

Deux types de forfaits d’appels sont disponibles :

- Forfaits d’appels nationaux
- Forfaits d’appels internationaux

|Posez-vous la question|Action |
|------------|-------|
|Les forfaits d’appels sont-ils disponibles dans ma région ? Quels emplacements d’utilisateur disposeront du service Forfait d’appels ? | Pour plus d’informations, consultez [La disponibilité des pays et des régions pour les forfaits d’audioconférence et d’appel](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). |
Mes utilisateurs ont-ils besoin d’appels internationaux ? | Pour plus d’informations, consultez [Forfaits d’appels pour Microsoft 365 ou Office 365](calling-plans-for-office-365.md). |
Mes utilisateurs disposent-ils de licences forfaits d’appels ? | Pour acheter et attribuer des licences, consultez [l’étape 2 : Acheter et attribuer des licences](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
Mes utilisateurs ont-ils chacun un numéro de téléphone direct entrant (DID) ? | Pour obtenir des numéros de téléphone, consultez [l’étape 3 : Obtenir des numéros de téléphone](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Transférer des numéros de téléphone vers Microsoft 365 ou Office 365

Il est facile de transférer vos numéros de téléphone de votre fournisseur de services actuel vers Teams. Une fois que vous avez transféré vos numéros de téléphone vers Teams, Microsoft devient votre fournisseur de services et vous facture ces numéros de téléphone. Pour plus d’informations, consultez [Transférer des numéros de téléphone vers Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

### <a name="phone-numbers-and-emergency-locations"></a>Numéros de téléphone et emplacements d'urgence

Avec les forfaits d’appels dans Microsoft 365 ou Office 365, chaque utilisateur de votre organisation doit disposer d’un numéro de téléphone direct (DID) et d’une adresse d’urgence validée correspondante. Vous pouvez également spécifier un emplacement d’urgence dans l’adresse d’urgence (par exemple, un numéro de bureau ou un numéro de plancher).

|Posez-vous la question|Action |
|:------------|:-------|
|Comment puis-je obtenir des informations détaillées sur l’adresse et l’emplacement de l’urgence ? |Pour plus d’informations, voir [Que sont les emplacements d’urgence, les adresses et le routage des appels ?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)

### <a name="calling-identity"></a>Identité d’appel

Par défaut, tous les appels sortants utilisent le numéro de téléphone affecté comme identité d’appel (ID d’appelant). Le destinataire de l'appel peut rapidement identifier l'appelant et décider d'accepter ou de refuser l'appel.

|Posez-vous la question|Action |
|:------------|:-------|
|Dois-je masquer ou désactiver l’ID de l’appelant ? | Pour modifier ou bloquer l’ID de l’appelant, consultez [Définir l’ID de l’appelant pour un utilisateur](set-the-caller-id-for-a-user.md). |
|||
