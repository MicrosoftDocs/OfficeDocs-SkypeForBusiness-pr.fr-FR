---
title: Mode partage de lignes dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
description: Découvrez comment envoyer un e-mail à vos utilisateurs avec leurs informations d’audioconférence dans Microsoft Teams.
ms.openlocfilehash: 3646cf27e22f5224dc825c758f757cc04d5804fc
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794322"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Mode partage de lignes dans Microsoft Teams

L’apparence de ligne partagée fait partie de la fonctionnalité de délégation qui permet à un utilisateur de choisir un délégué pour répondre ou gérer les appels en son nom. Cette fonctionnalité est utile si un utilisateur dispose d’un assistant administratif qui gère régulièrement les appels de l’utilisateur. Dans le contexte de l’apparence de ligne partagée, un responsable est quelqu’un qui autorise un délégué à passer ou recevoir des appels en son nom, et un délégué peut passer et recevoir des appels au nom d’une autre personne.

> [!IMPORTANT]
> Cette fonctionnalité est disponible uniquement en mode de déploiement Teams Uniquement. Pour plus d’informations sur les modes de déploiement Teams, consultez [Comprendre Microsoft Teams et Skype Entreprise coexistence et interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licence requise

Un utilisateur doit disposer d’un système téléphonique avec une connectivité RTC (licence de plan d’appel ou routage direct OnlineVoiceRoutingPolicy) pour être délégué ou configurer une délégation et permettre à d’autres utilisateurs d’effectuer ou de recevoir des appels en leur nom.

Les responsables et les délégués doivent disposer d’un système téléphonique avec une connectivité RTC (soit une licence de plan d’appel, soit un routage direct OnlineVoiceRoutingPolicy). L’expérience de ligne partagée fait partie de la délégation et est incluse avec le système téléphonique. Pour plus d’informations sur le modèle de licence, consultez la [description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="configuring-delegation-and-shared-line-appearance"></a>Configuration de la délégation et de l’apparence de ligne partagée

La délégation et l’apparence de ligne partagée sont des fonctionnalités pilotées par l’utilisateur : il n’existe aucun paramètre d’administrateur à configurer. Pour plus d’informations sur l’utilisation de la fonctionnalité, consultez [Partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

L’administrateur client peut activer la délégation via le paramètre **AllowDelegation TeamsCallingPolicy** ou via le portail Teams Administration pour que cette fonctionnalité fonctionne. 

L’administrateur client peut également configurer les relations de délégation pour un utilisateur dans le Centre d’administration Teams. En outre, l’utilisateur final peut également configurer ses relations de délégation directement dans Teams. L’administrateur client ou l’utilisateur ne peuvent pas bloquer la configuration l’un par l’autre, mais le centre d’administration Teams et le client Teams doivent afficher cette relation avec précision dans les deux emplacements. 

> [!IMPORTANT]
> Lorsque l’administrateur client désactive la délégation pour un utilisateur (une fois qu’elle a été activée), il doit également nettoyer les relations de délégation pour cet utilisateur dans le Centre d’administration Teams afin d’éviter un routage d’appel incorrect.

## <a name="shared-line-appearance-feature-availability"></a>Disponibilité des fonctionnalités d’apparence de ligne partagée

L’apparence de ligne partagée est actuellement prise en charge par les applications et appareils suivants.

| Fonctionnalité | Bureau Teams | Application Mac Teams | Teams Web App (Edge) |Application mobile iOS/Android Teams | Téléphone IP Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurer la délégation | Oui | Oui | Oui | Non | Oui |
| Recevoir des appels au nom d’un autre | Oui | Oui | Oui | Oui | Oui |
| Appeler un numéro de téléphone au nom d’un autre | Oui | Oui | Oui | Oui | Oui |
| Appeler un utilisateur Teams pour le compte d’un autre | Oui | Oui | Oui | Oui | Oui |
| Voir la vue déléguée des lignes partagées | Oui | Oui | Oui | Non | Oui |
| Voir la vue déléguée des activités d’appel du responsable | Oui | Oui | Oui | Non | Oui |
| Voir la vue gestionnaire des délégués | Oui | Oui | Oui | Non | Oui |
| Le délégué ou le responsable peut conserver ou reprendre | Oui | Oui | Oui | Non | Oui |

## <a name="limitations"></a>Limites

Les gestionnaires peuvent ajouter jusqu’à 25 délégués et les délégués peuvent avoir jusqu’à 25 gestionnaires. Il n’existe aucune limite au nombre de relations de délégation qui peuvent être créées dans un locataire. 
 
Si le délégateur et le délégué ne se trouvent pas dans le même emplacement géographique, il appartient au fournisseur RTC d’autoriser l’ID d’appelant à s’afficher à partir d’un autre emplacement géographique pour un appel délégué (au nom de). 

La configuration de délégation circulaire n’est pas autorisée. Si les utilisateurs délégués ont également des délégations entre eux, ils ne pourront voir que leur délégation et non la délégation initiale.
 
## <a name="more-information"></a>Plus d’informations

[Partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)
