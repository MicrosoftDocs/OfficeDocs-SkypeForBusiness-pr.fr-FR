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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Découvrez comment envoyer à vos utilisateurs un courrier électronique avec leurs informations d’audioconférence dans Microsoft Teams.
ms.openlocfilehash: e9954f85d9f5676635dc8d4616c08d0e0d3ac6be
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617170"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Mode partage de lignes dans Microsoft Teams

L’apparence de ligne partagée fait partie de la fonctionnalité de délégation qui permet à un utilisateur de choisir un délégué pour répondre ou gérer les appels en son nom. Cette fonctionnalité est utile si un utilisateur dispose d’un assistant administratif qui gère régulièrement ses appels. Dans le contexte de l’apparence de ligne partagée, un responsable est une personne qui autorise un délégué à effectuer ou recevoir des appels en son nom, et un délégué peut effectuer et recevoir des appels au nom de quelqu’un d’autre.

> [!IMPORTANT]
> Cette fonctionnalité n’est disponible qu’Teams mode déploiement uniquement. Pour plus d’informations sur Teams modes de déploiement, voir Comprendre Microsoft Teams et Skype Entreprise coexistence et [l’interopérabilité.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licence requise

Un utilisateur doit avoir un Système téléphonique avec une connectivité RSTN (soit une licence de plan d’appels, soit une licence de routage direct OnlineVoiceRoutingPolicy) pour être délégué ou configurer la délégation et permettre à d’autres utilisateurs d’effectuer ou de recevoir des appels en leur nom.

Les responsables et les délégués doivent avoir une Système téléphonique connectivité PSTN (soit une licence de plan d’appels, soit une licence routage direct OnlineVoiceRoutingPolicy). L’expérience de ligne partagée fait partie de la délégation et est incluse dans Système téléphonique. Pour plus d’informations sur le modèle de licence, voir [Microsoft Teams description du service.](/office365/servicedescriptions/teams-service-description)

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configuration de la délégation et de l’apparence de ligne partagée

La délégation et l’apparence de ligne partagée sont des fonctionnalités pilotées par l’utilisateur : il n’y a aucun paramètre d’administrateur à configurer. Pour plus d’informations sur l’utilisation de la fonctionnalité, voir [Partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

L’administrateur des locataires peut activer la délégation via le paramètre **TeamsCallingPolicy AllowDelegation** ou via Teams portail d’administration pour que cette fonctionnalité fonctionne. 

L’administrateur des clients peut également configurer des relations de délégation pour un utilisateur dans le Teams d’administration. En outre, l’utilisateur final peut également configurer ses relations de délégation directement dans Teams. L’administrateur client ou l’utilisateur ne peuvent pas bloquer la configuration l’un après l’autre, mais le Centre d’administration Teams et le client Teams doivent afficher cette relation avec précision aux deux endroits. 

> [!IMPORTANT]
> Lorsque l’administrateur des clients désactivé la délégation pour un utilisateur (après l’avoir désactivée), il doit également nettoyer les relations de délégation pour cet utilisateur dans le Centre d’administration Teams pour éviter un routage d’appel incorrect.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilité des fonctionnalités d’apparence de ligne partagée

L’apparence de ligne partagée est actuellement prise en charge par les applications et appareils suivants.

| Fonctionnalité | Teams Bureau | Teams Application Mac | Teams Web App (Edge) |Teams’application mobile iOS/Android | Teams Téléphone IP |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurer la délégation | Oui | Oui | Oui | Non | Oui |
| Recevoir des appels au nom d’un autre | Oui | Oui | Oui | Oui | Oui |
| Appeler un numéro de téléphone pour le compte d’un autre | Oui | Oui | Oui | Oui | Oui |
| Appeler un Teams de la part d’un autre utilisateur | Oui | Oui | Oui | Oui | Oui |
| Afficher l’affichage administrateur des lignes partagées | Oui | Oui | Oui | Non | Non |
| Afficher l’affichage administrateur des activités d’appels du responsable | Oui | Oui | Oui | Non | Non |
| Afficher l’affichage des délégués par le responsable | Oui | Oui | Oui | Non | Non |
| Un administrateur ou un responsable peut maintenir ou reprendre | Oui | Oui | Oui | Non | Non |

## <a name="limitations"></a>Limites

Les responsables peuvent ajouter jusqu’à 25 délégués, et les délégués peuvent avoir jusqu’à 25 responsables. Il n’y a pas de limite au nombre de relations de délégation qui peuvent être créées dans un client. 
 
Si le délégant et le délégué ne se trouvent pas dans le même emplacement géographique, c’est au fournisseur PSTN d’autoriser l’ID d’appelant à s’afficher à partir d’un emplacement géographique différent pour un appel délégué (de la part de). 
 
## <a name="more-information"></a>Plus d’informations

[Partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)