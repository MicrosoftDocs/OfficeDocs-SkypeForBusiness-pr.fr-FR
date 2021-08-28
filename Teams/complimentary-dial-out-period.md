---
title: Période d'appel sortant gratuite
ms.author: tonysmit
author: tonysmit
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
- Skype for Business
- Microsoft Teams
ms.localizationpriority: ''
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
description: Découvrez la période d’appels sortants complémentaire pour un plan d’appels Microsoft 365 ou Office 365 et la Office 365 d’audioconférence dans Microsoft Teams.
ms.openlocfilehash: fa571a355f4eb9a546c2c231e9a06f83d4374029
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619600"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>Période complémentaire pour la numérotation de l'audioconférence

## <a name="skype-for-business-pstn-services"></a>Services RTC Skype Entreprise

Les clients peuvent utiliser Microsoft 365 ou Office 365 Calling Plan et l’Audioconférence Office 365 selon les autorisations des conditions d’utilisation des services PSTN d’Skype Entreprise Online et du contrat de licence en volume du client. Les termes d’utilisation des services RTC peuvent être trouvés dans [Conditions de licence et documentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=2&amp;Keyword=PSTN).
  
### <a name="end-of-complimentary-dial-out-period"></a>Fin d’une période d’appel sortant complémentaire

La fonctionnalité complémentaire d’appel sortant a pris fin le 1er décembre 2019. Pour plus d’informations, [consultez l’abonnement à l’audioconférence et appelez-moi à l’avantage.](audio-conferencing-subscription-dial-out.md) 

Cette modification n’a pas eu lieu pour les pays où l’abonnement Audioconférence est disponible, mais nous n’avons pas activé la configuration des crédits de communication pour le moment. Ces pays spécifiques sont la Russie, la Corée du Sud et Taïwan.

### <a name="complimentary-dial-out-period-details"></a>Détails complémentaires de la période d’appel sortant

Pour les clients qui adoptent notre service d’audioconférence Microsoft 365 ou Office 365, Microsoft fournit un autre avantage complémentaire lié à l’appel sortant de réunions organisées par des utilisateurs 2019 à qui une licence d’abonnement Microsoft 365 ou audioconférence Office 365 est attribuée jusqu’en novembre 2019. Pendant cette période complémentaire, Microsoft autorise les organisateurs de réunion ou les participants autorisés, tels que définis dans les paramètres de stratégie de réunion, à effectuer des appels sortants depuis la réunion vers des numéros de téléphone non premium dans les pays et régions de la zone 44 [Zone A.](audio-conferencing-zones.md) Cet avantage s’applique aux licences d’abonnement mensuel à l’audioconférence et ne s’applique pas aux licences de paiement à la minute d’Audioconférence.

Il existe en outre une limite de 900 minutes pendant la période d’appel sortant complémentaire comme telles :

Les utilisateurs avec un emplacement d’utilisation des licences (l’emplacement est l’emplacement du pays d’utilisateur défini dans la zone de licence du Centre d’administration Microsoft 365) dans n’importe quel _pays_ ou région peuvent appeler depuis une conférence vers l’un des pays et régions de la zone 44 Zone [A.](audio-conferencing-zones.md) Chaque utilisateur reçoit 900 minutes  par utilisateur et par mois pour tous les pays et régions de la [zone A,](audio-conferencing-zones.md)qui sont poolés au niveau du client. Par exemple, un client a acheté 115 licences d’abonnement à Audioconférence et a 10 utilisateurs aux États-Unis, 100 utilisateurs au Royaume-Uni et 5 utilisateurs en Inde, tous avec des licences d’abonnement Audioconférence attribuées à leurs utilisateurs.

- Tous les 115 utilisateurs partagent un pool de (115 utilisateurs X 900 min) = 103 500 minutes d’appels sortants par mois calendaire, qui peut être utilisé pour placer des appels sortants vers les pays et régions de la [zone A.](audio-conferencing-zones.md)

- Tous les appels supérieurs à 103 500 minutes par mois calendaire sont facturés par minute à l’aide des crédits de communication aux tarifs publiés vers cette destination. (Remarque : le client doit configurer les crédits de communication et affecter la licence Crédits de communication à l’organisateur de la réunion).

- Tous les appels sortants vers des destinations ne faisant pas partir de la liste pays et régions de la zone [A](audio-conferencing-zones.md) sont facturés par minute à l’aide des crédits de communication à nos tarifs publiés vers cette destination (à condition que le client ait installé les crédits de communication et attribué la licence Crédits de communication à l’organisateur de la réunion).

> [!NOTE]
> Vous pouvez surveiller l’utilisation du pool de minutes d’appels sortants dans le Skype Entreprise d’administration. Dans le centre Microsoft Teams & Skype d’administration, allez aux pools de minutes   >    >  **PSTN** Rapports du portail hérité. Ce pool de minutes complémentaire sera étiqueté dans le rapport comme « Appels sortants vers les pays et régions de la zone A ».

Les notifications par courrier électronique seront envoyées à tous les administrateurs client d’un client donné lorsque l’utilisation du pool de minutes d’appels sortants du client atteint les 80 % et 100 %.

Pour les appels sortants facturés par minute (appels dépassant le pool de minutes d’appels sortants du client ou appels vers des destinations ne se tenant pas dans la liste pays ou région de la zone [A),](audio-conferencing-zones.md) les appels et leurs tarifs associés sont principalement basés sur la destination de l’appel et non sur le pays ou la région de l’organisateur ou du participant à l’origine de l’appel sortant. Par exemple, un appel vers un numéro de téléphone en France sera facturé avec le même tarif si un participant à la réunion est lancé par un participant à la réunion aux États-Unis ou en France.

Pour plus d’informations sur les crédits de communication, voir [Crédits de communication.](what-are-communications-credits.md)
     
## <a name="related-topics"></a>Rubriques connexes

- [Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Zones de pays et de région pour l’audioconférence](audio-conferencing-zones.md)
