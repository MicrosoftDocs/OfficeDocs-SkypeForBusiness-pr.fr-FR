---
title: 'Configuration de réunion : création d’une réunion ou modification d’une configuration existante'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres s’appliquent uniquement aux réunions planifiées. Elles ne s’appliquent pas aux réunions ad hoc créées en cliquant sur l’option Conférence maintenant dans le client.
ms.openlocfilehash: f95e9f30ab485b80824c31e700fc7f88714a7a5b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741250"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuration de la réunion : création d’une nouvelle ou modification d’une configuration existante

Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres s’appliquent uniquement aux réunions planifiées. Elles ne s’appliquent pas aux réunions ad hoc créées en cliquant sur l’option Conférence **maintenant** dans le client.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les champs de la page.

- **Étendue** Identifie l’étendue de la configuration de réunion que vous créez ou modifiez : globale, de site ou de pool.

- **Nom** Les configurations de réunion sont nommées par défaut et le nom ne peut pas être modifié.

- **Les appelants PSTN contournent la salle d’entrée** Cochez cette case pour admettre automatiquement les utilisateurs qui appellent la conférence sur une ligne téléphonique du réseau téléphonique commuté (PSTN). Cochez cette case pour router les appelants PSTN vers la salle d’attente de la conférence, où ils sont en attente jusqu’à ce qu’un présentateur de conférence leur donne accès à la conférence.

- **Désigné comme présentateur** Sélectionnez la catégorie des utilisateurs (en plus de l’organisateur de la réunion) qui sont automatiquement désignés comme présentateurs lorsqu’ils rejoignent une conférence. Quel que soit ce paramètre, les présentateurs peuvent être explicitement désignés comme présentateurs lorsque la conférence est programmée, ou ils peuvent être promus explicitement en tant que présentateurs au cours de la conférence. Les options disponibles sont les suivantes :

  - **Aucun** Sélectionnez cette option si personne d’autre que l’organisateur n’est désigné automatiquement comme présentateur.

  - **Société** Sélectionnez cette option pour désigner automatiquement uniquement les membres de votre organisation comme présentateurs.

  - **Tout le monde** Sélectionnez cette option pour désigner automatiquement quiconque comme présentateur.

- **Type de conférence affecté par défaut** Ce paramètre contrôle si le Outlook Conferencing Addin planifiera toujours les conférences à l’aide de la conférence attribuée par l’organisateur, ce qui signifie que les conférences programmées ont toujours la même URL de rejoindre et les mêmes informations audio. Cochez cette case pour que les conférences programmées utilisent toujours la même URL de jointeur. Cochez cette case pour utiliser une URL de jointeur différente pour chaque conférence.

- **Admettre les utilisateurs anonymes par défaut** Cochez cette case si les utilisateurs anonymes (c’est-à-dire non authentifiés) sont autorisés à participer à des conférences par défaut. Cochez cette case si les utilisateurs anonymes ne sont pas autorisés à participer aux conférences par défaut.

- **URL du logo** Tapez l’URL qui possède l’image à utiliser pour les invitations aux conférences personnalisées.

- **URL de l’aide** Tapez l’URL d’un site web où les utilisateurs peuvent obtenir de l’aide pour participer à la conférence.

- **URL de texte légal** Tapez l’URL d’un site web qui possède les informations légales et les clauses d’exclusion de responsabilité pour la conférence.

- **Texte de pied de groupe personnalisé** Tapez le texte à utiliser sur les invitations aux conférences personnalisées.

Pour plus d’informations sur l’utilisation des configurations de réunion, voir [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) dans la documentation des opérations. Pour plus de détails sur la définition de configurations de réunion pour de grandes réunions, voir [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) dans la documentation de planification.