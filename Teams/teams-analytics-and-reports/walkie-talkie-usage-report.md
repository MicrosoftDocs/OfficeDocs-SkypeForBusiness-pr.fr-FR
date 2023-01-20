---
title: Rapport sur l’utilisation et les performances du talkie-walkie
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: admin
ms.topic: article
ms.service: microsoft-365-frontline
ms.reviewer: prastogi
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
- tier2
description: Découvrez comment utiliser le rapport d’utilisation et de performances talkie-walkie dans le Centre d’administration Microsoft Teams pour obtenir une vue d’ensemble de l’activité d’utilisation du talkie-walkie dans votre organisation.
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 85f92e715efe2b9608691151a08d006816658095
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2023
ms.locfileid: "69846049"
---
# <a name="walkie-talkie-usage-and-performance-report"></a>Rapport sur l’utilisation et les performances du talkie-walkie

Le rapport d’utilisation et de performances talkie-walkie dans le Centre d’administration Microsoft Teams vous donne une vue d’ensemble de l’activité [talkie-walkie](../walkie-talkie.md) dans votre organisation. Le rapport fournit des informations telles que le nombre de transmissions push-to-talk (PTT) effectuées et reçues, l’activité du canal, la durée de transmission et les détails de l’appareil et du participant.

Utilisez ce rapport pour obtenir des informations sur les tendances d’utilisation et les performances de Talkie-Walkie au sein de votre organisation. Pour accéder au rapport, vous devez être administrateur général, administrateur Teams, lecteur général ou lecteur de rapport.

## <a name="download-and-view-the-report"></a>Télécharger et afficher le rapport

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, choisissez **Analytics & rapports** > **Rapports d’utilisation**. Sous l’onglet **Afficher les rapports** , sous **Rapport**, sélectionnez **Utilisation du talkie-walkie**.
1. Sous **Plage de** dates, sélectionnez une plage de dates de 7 jours ou 30 jours. Ensuite, choisissez **Exécuter le rapport**.
1. Sélectionnez **Générer un rapport**.
1. Sous l’onglet **Téléchargements** , sous **État**, choisissez **Télécharger** pour télécharger le rapport au format CSV.

## <a name="interpret-the-report"></a>Interpréter le rapport

Le rapport vous donne une répartition de chaque transmission effectuée au cours de la plage de dates que vous avez sélectionnée. Voici les informations incluses dans le rapport.

|Nom de la colonne |Description |
|---------|---------|
|TenantId|ID de locataire.|
|Userid|ID d’utilisateur.|
|DeviceId|ID de l’appareil.|
|ChannelId|Canal talkie-walkie dans lequel la communication s’effectue.|
|clientCallStatus | Indique si l’appareil a pu recevoir la transmission sans problème.|
|ConversationId|ID de chaque transmission PTT.|
|TeamId|ID de l’équipe qui correspond au canal Talkie-walkie dans lequel l’utilisateur se connecte.|
|UnreachableParticipantsCount|Nombre de participants marqués comme inaccessibles et masqués de la liste parce qu’ils n’ont pu recevoir aucune des cinq dernières transmissions.|
|TransmissionDuration|Durée (en millisecondes) entre le moment où le service reçoit la notification indiquant qu’un participant est sur le point de démarrer une transmission lorsque le service remet le dernier package de cette transmission.|
|TotalParticipantsCount|Nombre total de participants connectés au canal Talkie-walkie.|
|PacketCount|Nombre de paquets utilisés pour envoyer la transmission audio.|
|NotifiedParticipants|Participants auxquels une notification Push est envoyée lorsqu’une transmission démarre. Dans les scénarios où la connexion entre l’appareil et le service est perdue, une notification est envoyée à l’appareil pour rétablir la connexion dès que possible, car une transmission est en cours.|
|AudioDurationMillisecondes|Durée de la transmission en millisecondes.|
|Id de connexion|ID de chaque connexion à un canal Talkie-walkie établi par l’appareil.|
|TransmissionStartTime |Date et heure de réception du premier paquet audio par le service.
|TransmissionEndTime|Date et heure de réception du dernier paquet audio par le service.|
|ParticipantList|Liste délimitée par des points-virgules des ID des appareils connectés au canal au moment de l’envoi de la transmission.|
|CallTimedOut|Indique si la transmission a dépassé la limite de durée. Il s’agit d’une valeur booléenne.|
|Plateforme|Système d’exploitation de l’appareil.|
|ParticipantType|Indique si le participant était l’émetteur ou un récepteur de la transmission.|
|WebSocketState|Indique si l’état de la connexion entre l’appareil et le service était déjà établi au démarrage de la transmission.|
|AppVersion|Version de l’application Teams installée sur l’appareil.|

## <a name="related-articles"></a>Articles connexes

- [Application Talkie-walkie dans Teams](../walkie-talkie.md)
- [Prise en main du talkie-walkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)