---
title: Configuration de réunion créer ou modifier une existant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option Conférence maintenant du client.
ms.openlocfilehash: bb2b81aa860660503522783d3ed3a3aa9ec09985
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200701"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>Configuration de la réunion : création d’une réunion ou modification d’une réunion existante

Les paramètres de configuration de réunion définissent la participation des utilisateurs pour les conférences planifiées par des utilisateurs. Ces paramètres ne concernent que les réunions planifiées. Ils ne concernent pas les réunions ad hoc créées en cliquant sur l’option **Conférence maintenant** du client.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Étendue** Identifie l’étendue de la configuration de réunion que vous créez ou modifiez : globale, site ou pool.

- **Nom** Configurations de réunion sont nommées par défaut et le nom ne peut pas être modifié.

- **Les appelants PSTN de contournement salle d’attente** Activez cette case à cocher Accepter automatiquement les utilisateurs qui sont connectent à la conférence sur la ligne téléphonique public commuté (PSTN) réseau. Désactivez cette case à cocher pour les appelants PSTN d’itinéraire à la salle d’attente de conférence, où ils se trouvent sur attente jusqu'à ce que le présentateur de la conférence les autorise à accéder à la conférence.

- **Désigner en tant que présentateur** Sélectionnez la catégorie d’utilisateurs sont automatiquement désigné en tant que présentateurs lorsqu’ils rejoignent une conférence (en plus de l’organisateur de la réunion). Quel que soit ce paramètre, les présentateurs peuvent être explicitement désignés en tant que présentateurs lors de la conférence est planifiée, ou ils peuvent être promus explicitement au présentateur au cours de la conférence. Les options sont les suivants :

  - **Aucun** Sélectionnez cette option si personne d’autre que l’organisateur est automatiquement désigné en tant que présentateur.

  - **Société** Sélectionnez cette option pour désigner automatiquement uniquement les membres de votre organisation en tant que présentateurs.

  - **Tout le monde** Sélectionnez cette option pour désigner automatiquement tout le monde à être présentateur.

- **Type de conférence affecté par défaut** Ce paramètre contrôle si le complément de conférence Outlook planifie toujours les conférences à l’aide de l’organisateur affecté conférence, ce qui signifie que planifiées toujours des conférences ont le même participer à une URL et les informations audio. Activez cette case à cocher pour que les conférences planifiées à toujours utiliser la même URL jointure. Désactivez cette case à cocher pour utiliser une URL de jointure différente pour chaque conférence.

- **Autoriser les utilisateurs anonymes par défaut** Activez cette case à cocher si anonyme (c'est-à-dire, non authentifié) les utilisateurs sont autorisés à participer à des conférences par défaut. Désactivez cette case à cocher si les utilisateurs anonymes ne sont pas autorisés à participer à des conférences par défaut.

- **URL du logo** Tapez l’URL qui se trouve l’image à utiliser pour les invitations de conférence personnalisées.

- **URL de l’aide** Tapez l’URL d’un site Web où les utilisateurs peuvent obtenir une assistance pour participer à la conférence.

- **URL légales** Tapez l’URL d’un site Web qui possède les informations légales et les clauses d’exclusion pour la conférence.

- **Texte de pied de page personnalisé** Tapez le texte à utiliser sur les invitations de conférence personnalisées.

Pour plus d’informations sur l’utilisation des configurations de réunion, reportez-vous à la rubrique [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) de la documentation des opérations. Pour plus d’informations sur la définition de configurations de réunion pour des réunions importantes, reportez-vous à la rubrique [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) de la documentation de planification.


