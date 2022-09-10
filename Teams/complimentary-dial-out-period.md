---
title: Période d'appel sortant gratuite
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mikedav, OscarR
ms.topic: conceptual
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: ''
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
description: Découvrez la période de numérotation gratuite pour un plan d’appel Microsoft 365 et l’audioconférence dans Microsoft Teams.
ms.openlocfilehash: 72ec36eb99a4a0eb2358195a52db00b26bb591e5
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641895"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>Période complémentaire pour la numérotation de l'audioconférence

## <a name="teams-pstn-services"></a>Services RTC Teams

Les clients peuvent utiliser un plan d’appel Ou Microsoft 365 et l’audioconférence Teams, comme l’autorisent les conditions d’utilisation des services RTC Teams et le contrat de licence en volume du client. Les conditions d’utilisation des services RTC se trouvent dans les [ressources et documents de gestion des licences](https://www.microsoft.com/licensing/docs).

### <a name="end-of-complimentary-dial-out-period"></a>Fin de la période de numérotation gratuite

La fonctionnalité de numérotation gratuite a pris fin le 1er décembre 2019. Pour plus d’informations, consultez [l’abonnement à l’audioconférence et appelez-moi à l’avantage](audio-conferencing-subscription-dial-out.md).

Cette modification n’a pas eu lieu pour les pays où l’abonnement à l’audioconférence est disponible, mais nous n’activons pas actuellement la configuration des crédits de communication. Ces pays spécifiques sont la Russie, la Corée du Sud et Taïwan.

### <a name="complimentary-dial-out-period-details"></a>Détails de la période de numérotation gratuit

Pour les clients qui adoptent notre service d’audioconférence Microsoft 365, Microsoft offre un avantage complémentaire supplémentaire lié à la déconnexion à partir de réunions organisées par les utilisateurs auxquels une licence d’abonnement à l’audioconférence Microsoft 365 est attribuée jusqu’en novembre 2019. Pendant cette période gratuite, Microsoft permet aux organisateurs de réunion ou aux participants autorisés, tels que définis dans les paramètres de stratégie de réunion, d’effectuer des appels sortants à partir de la réunion vers des numéros de téléphone non premium dans les [pays et régions de la zone A](audio-conferencing-zones.md) 44. Cet avantage s’applique aux licences d’abonnement mensuel à l’audioconférence et ne s’étend pas aux licences d’audioconférence à la minute.

En outre, il existe une limite de 900 minutes pendant la période de numérotation gratuite en tant que telle :

Les utilisateurs disposant d’un emplacement d’utilisation de licence (l’emplacement est l’emplacement du pays d’utilisateur défini dans la zone de licence de l’Centre d'administration Microsoft 365) dans _n’importe quel_ pays_ peuvent passer d’une conférence à l’un des 44 [pays et régions de la zone A](audio-conferencing-zones.md). Chaque utilisateur reçoit 900 minutes par utilisateur par mois dans _l’un_ des [pays et régions de la zone A](audio-conferencing-zones.md), qui sont regroupés au niveau du locataire. Par exemple, un client a acheté 115 licences d’abonnement à l’audioconférence et a 10 utilisateurs aux États-Unis, 100 utilisateurs au Royaume-Uni et 5 utilisateurs en Inde, le tout avec des licences d’abonnement d’audioconférence attribuées à leurs utilisateurs.

- Les 115 utilisateurs partagent un pool de (115 utilisateurs X 900 min) = 103 500 minutes de conférence rendez-vous par mois calendaire, qui peut être utilisé pour passer des appels sortants vers n’importe quel [pays et région de la zone A](audio-conferencing-zones.md).

- Tous les appels dépassant les 103 500 minutes par mois calendaire sont facturés par minute à l’aide des crédits de communication à nos tarifs publiés vers cette destination. (Remarque : le locataire doit configurer les crédits de communication et attribuer la licence Crédits de communication à l’organisateur de la réunion).

- Tous les appels sortants vers des destinations qui ne figurent pas dans la liste des [pays et régions de la zone A](audio-conferencing-zones.md) sont facturés par minute à l’aide des crédits de communication à nos tarifs publiés vers cette destination (à condition que le locataire ait configuré des crédits de communication et affecté la licence Crédits de communication à l’organisateur de la réunion).

> [!NOTE]
> Vous pouvez surveiller l’utilisation par rapport au pool de minutes de déconnexion dans le Centre d’administration Teams. Dans le Centre d’administration Microsoft Teams, accédez aux **pools de minutes PSTN** **des rapports** >  du **portail** >  hérité. Ce pool de minutes gratuit sera étiqueté dans le rapport comme « Appels sortants vers les pays et régions de la zone A ».

Email notifications seront envoyées à tous les administrateurs client d’un client donné lorsque l’utilisation du pool de minutes de déconnexion du locataire a atteint 80 % et 100 %.

Pour les appels sortants facturés par minute (appels dépassant le pool de minutes de déconnexion du locataire ou appels vers des destinations qui ne figurent pas dans la liste [des pays et régions de la zone A](audio-conferencing-zones.md) ), les appels et leurs tarifs associés sont principalement basés sur la destination de l’appel et non sur le pays ou la région de l’organisateur ou du participant à l’origine de l’appel sortant. Par exemple, un appel à un numéro de téléphone en France est facturé avec le même tarif s’il est initié par un participant à une réunion dans le États-Unis ou un en France.

Pour plus d’informations sur les crédits de communication, consultez [Crédits de communication](what-are-communications-credits.md).

## <a name="related-topics"></a>Rubriques connexes

- [Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Zones de pays et de régions pour l’audioconférence](audio-conferencing-zones.md)
