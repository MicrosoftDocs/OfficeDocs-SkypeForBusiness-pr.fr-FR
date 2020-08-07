---
title: Mode partage de lignes dans Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: En savoir plus sur l’envoi de courriers électroniques à vos utilisateurs à l’aide de leurs informations de conférence audio dans Microsoft Teams.
ms.openlocfilehash: 7750f85e959f332832c24b60b4efafd784218f61
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583833"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Mode partage de lignes dans Microsoft Teams

L’apparence des lignes partagées fait partie de la fonctionnalité de délégation qui permet à l’utilisateur de choisir un délégué pour répondre aux appels ou gérer ses appels en son nom. Cette fonctionnalité est utile si un utilisateur dispose d’un assistant administratif qui gère régulièrement les appels de l’utilisateur. Dans le contexte de l’apparence de ligne partagée, un responsable est une personne qui autorise un délégué à passer ou recevoir des appels en son nom et un délégué peut émettre et recevoir des appels au nom d’une autre personne.

> [!IMPORTANT]
> Cette fonctionnalité n’est disponible que dans le mode déploiement d’équipes. Pour plus d’informations sur les modes de déploiement d’équipes, voir comprendre les modes de déploiement de [Microsoft Teams, ainsi que la coexistence et l’interopérabilité de Skype entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licence requise

Un utilisateur doit être doté d’un système téléphonique avec connectivité PSTN (licence de plan d’appel ou OnlineVoiceRoutingPolicy de routage directe) pour être délégué ou configuré délégation et permettre à d’autres personnes de passer ou de recevoir des appels en son nom.

Les responsables et délégués doivent disposer d’un système téléphonique avec connectivité PSTN (licence de plan d’appel ou OnlineVoiceRoutingPolicy de routage directe). L’interface de ligne partagée fait partie de la délégation et est incluse dans le système téléphonique. Pour plus d’informations sur le modèle de gestion des licences, voir [Description du service Microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configuration de la délégation et de l’apparence des lignes partagées

Les fonctionnalités de délégation et d’affichage des lignes partagées sont des fonctionnalités utilisateur : il n’y a aucun paramètre d’administration à configurer. Pour plus d’informations sur l’utilisation de la fonctionnalité, voir [partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8) .

L’administrateur client peut activer la délégation via le paramètre **TeamsCallingPolicy AllowDelegation** ou via le portail d’administration teams pour que cette fonctionnalité fonctionne. 

L’administrateur client peut également configurer des relations de délégation pour un utilisateur dans le centre d’administration Teams. Par ailleurs, l’utilisateur final peut également configurer directement ses relations de délégation dans Teams. L’administrateur client ou l’utilisateur ne peut pas bloquer la configuration entre eux, mais le centre d’administration teams et le client teams doivent afficher cette relation précisément dans les deux emplacements. 

> [!IMPORTANT]
> Lorsque l’administrateur client désactive la délégation pour un utilisateur (une fois qu’il a été activé), il doit également nettoyer les relations de délégation de cet utilisateur dans le centre d’administration teams pour éviter le routage d’appels incorrect.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilité des fonctionnalités d’apparence des lignes partagées

L’apparence des lignes partagées est actuellement prise en charge par les applications et appareils suivants.

| Fonctionnalité | Bureau teams | Application Mac teams | Team Web App (Edge) |Application mobile iOS/Android teams | Téléphone IP teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurer la délégation | Oui | Oui | Oui | Non | Oui |
| Recevoir des appels au nom d’un autre | Oui | Oui | Oui | Oui | Oui |
| Appeler un numéro de téléphone pour le compte d’une autre | Oui | Oui | Oui | Oui | Oui |
| Appeler un utilisateur de teams au nom d’un autre | Oui | Oui | Oui | Oui | Oui |
| Voir la vue d’administration des lignes partagées | Oui | Oui | Oui | Non | Non |
| Voir la vue d’administration des activités d’appel du responsable | Oui | Oui | Oui | Non | Non |
| Afficher le mode responsable des délégués | Oui | Oui | Oui | Non | Non |
| L’administrateur ou le responsable peut mettre en attente ou reprendre | Oui | Oui | Oui | Non | Non |

## <a name="limitations"></a>Conditions

Les responsables peuvent ajouter jusqu’à 25 délégués et des délégués peuvent compter jusqu’à 25 responsables. Il n’y a aucune limite au nombre de relations de délégation qui peuvent être créées dans un client. 
 
Si le délégué et la personne qui ne se trouvent pas dans le même emplacement géographique, c’est le fournisseur RTC qu’il est autorisé à afficher l’identification de l’appelant à partir d’un autre emplacement géographique pour un appel délégué (au nom de). 
 
## <a name="more-information"></a>Plus d’informations

[Partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
