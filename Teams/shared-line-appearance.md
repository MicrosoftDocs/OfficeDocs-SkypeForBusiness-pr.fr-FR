---
title: Mode partage de lignes dans Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Apparence de la ligne partagé permet à un utilisateur de choisir un délégué à répondre ou gérer les appels en son nom.
ms.openlocfilehash: 0a110e18cb8a939870528d2700ec54103cf91a6e
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541695"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Mode partage de lignes dans Microsoft Teams

Apparence de la ligne partagé fait partie de la fonctionnalité de délégation qui permet à un utilisateur de choisir un délégué à répondre ou gérer les appels en son nom. Cette fonctionnalité est utile si l’utilisateur a un assistant administratif régulièrement gère les appels de l’utilisateur. Dans le contexte de l’apparence de la ligne partagée, un gestionnaire est une personne qui autorise un délégué d’émettre ou recevoir des appels en son nom, et un délégué peut émettre et recevoir des appels de la part de quelqu'un d’autre.

> [!IMPORTANT]
> Cette fonctionnalité est uniquement disponible en mode de déploiement équipes uniquement. Pour plus d’informations sur les modes de déploiement d’équipes, voir [comprendre les équipes Microsoft et Skype pour l’interopérabilité et coexistence d’entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licence requise

Un utilisateur doit être un utilisateur de voix entreprise un délégué ou configurer la délégation et permettre aux autres d’émettre ou recevoir des appels en son nom.

Les responsables et les délégués doivent être enterprise voice est activé. L’expérience de ligne partagé fait partie de la délégation et ne requiert aucune licence supplémentaire. Pour plus d’informations sur le modèle de licence, voir [Gestion des licences Office 365 pour les équipes Microsoft](office-365-licensing.md).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configuration de la délégation et l’apparence de la ligne partagé

Délégation et l’apparence de la ligne partagé sont effectuées par les utilisateurs des fonctionnalités : aucun paramètre d’administration pour configurer. Pour plus d’informations sur la façon d’utiliser la fonctionnalité, voir [partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

L’administrateur du client doit activer la délégation via le paramètre **TeamsCallingPolicy AllowDelegation** de cette fonctionnalité pour travailler.

## <a name="shared-line-appearance-feature-availability"></a>Partage de disponibilité des fonctionnalités ligne apparence

Apparence de la ligne partagé est actuellement pris en charge par les périphériques et les applications suivantes.

| Fonctionnalité | Bureau des équipes | Les équipes Mac application | Les équipes Web App (périmètre) |Les équipes mobile iOS/Android application | Téléphone IP d’équipes |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurer la délégation | Oui  | Oui  | Oui | Non | Non |
| Recevoir des appels de la part d’une autre | Oui  | Oui  | Oui  | Oui  | Oui |
| Appeler un numéro de téléphone au nom d’une autre | Oui  | Oui  | Oui  | Oui  | Oui |
| Appelez un utilisateur équipes part d’une autre | Oui  | Oui  | Oui  | Oui  | Oui |
| Vue d’administration de lignes partagés | Oui  | Oui  | Oui | Non | Non |
| Vue d’administration des activités d’appel du responsable | Oui  | Oui  | Oui | Non | Non |
| Voir la vue du Gestionnaire de délégués | Oui  | Oui  | Oui | Non | Non |
| Admin ou gestionnaire peut contenir ou reprendre | Oui  | Oui  | Oui | Non | Non |

## <a name="limitations"></a>Limitations

Les responsables peuvent ajouter jusqu'à 25 délégués et les délégués peuvent avoir jusqu'à 25 responsables. Il n’existe aucune limite au nombre de niveaux de délégation qui peuvent être créés dans un client. 
 
Si la personne qui a délégué et un délégué ne se trouvent pas dans le même emplacement géographique, il est le fournisseur PSTN pour autoriser l’ID de l’appelant s’affiche à partir d’un autre emplacement géographique d’un appel de délégué (de la part de). 
 
## <a name="more-information"></a>Plus d’informations

[Partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
