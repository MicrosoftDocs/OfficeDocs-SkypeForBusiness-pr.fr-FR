---
title: Configuration de la réunion création d’un nouveau ou modification existante
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.
ms.openlocfilehash: e7b3ac1858ed012d99af32c8910b6f9e6d69f6a2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822687"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuration de la réunion : création d’une réunion ou modification d’une réunion existante

Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option **Conférence maintenant** du client.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Scope** Identifie l’étendue de la configuration de réunion que vous créez ou modifiez : global, site ou pool.

- **Nom** Les configurations de réunion sont nommées par défaut et le nom ne peut pas être modifié.

- **Appel RTC-salle d’attente** Activez cette case à cocher pour admettre automatiquement les utilisateurs qui se connectent à la Conférence par le biais d’une ligne téléphonique PSTN (réseau téléphonique commuté). Désactivez cette case à cocher pour acheminer les appelants PSTN vers la salle d’attente, où ils sont en attente jusqu’à ce qu’un présentateur de conférence leur accorde l’accès à la Conférence.

- **Désigner comme présentateur** Sélectionnez la catégorie d’utilisateurs (en plus de l’organisateur de la réunion) qui sont automatiquement désignés comme présentateurs lorsqu’ils rejoignent une conférence. Quels que soient les paramètres de ce paramètre, les présentateurs peuvent être désignés explicitement comme présentateurs lorsque la Conférence est planifiée, ou être promues explicitement au présentateur lors de la Conférence. Les options disponibles sont les suivantes :

  - **Aucun** Sélectionnez cette option si personne autre que l’organisateur n’est désigné automatiquement comme présentateur.

  - **Société** Sélectionnez cette option pour désigner automatiquement seuls les membres de votre organisation comme présentateurs.

  - **Tout le monde** Sélectionnez cette option pour désigner automatiquement tout le monde devant être présentateur.

- **Type de conférence affecté par défaut** Ce paramètre détermine si le complément de conférence Outlook planifie toujours des conférences à l’aide de la Conférence affectée à l’organisateur, ce qui signifie que les conférences planifiées ont toujours les mêmes URL et informations audio. Activez cette case à cocher pour que les conférences planifiées utilisent toujours la même URL de jointure. Désactivez cette case à cocher pour utiliser une autre URL de jointure pour chaque conférence.

- **Admettre les utilisateurs anonymes par défaut** Activez cette case à cocher si les utilisateurs anonymes (non authentifiés) peuvent participer par défaut aux conférences. Désactivez cette case à cocher si les utilisateurs anonymes ne peuvent pas participer par défaut aux conférences.

- **URL du logo** Tapez l’URL contenant l’image à utiliser pour les invitations aux conférences personnalisées.

- **URL de l’aide** Tapez l’URL d’un site Web dans lequel les utilisateurs peuvent obtenir de l’aide pour joindre la Conférence.

- **URL de texte légal** Tapez l’URL d’un site Web contenant les informations juridiques et les exclusions de responsabilité pour la Conférence.

- **Texte de pied de page personnalisé** Entrez le texte à utiliser pour les invitations aux conférences personnalisées.

Pour plus d’informations sur l’utilisation des configurations de réunion, reportez-vous à la rubrique [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) de la documentation des opérations. Pour plus d’informations sur la définition de configurations de réunion pour des réunions importantes, reportez-vous à la rubrique [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) de la documentation de planification.


