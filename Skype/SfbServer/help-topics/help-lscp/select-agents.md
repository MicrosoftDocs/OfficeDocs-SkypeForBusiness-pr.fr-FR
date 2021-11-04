---
title: Sélection des agents
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: Les agents sont des utilisateurs désignés pour répondre aux appels Response Group. Les groupes Response Group doivent avoir un groupe d’agents affecté qui identifie les agents qui peuvent recevoir des appels pour le groupe Response Group. Pour créer un groupe d’agents, vous pouvez définir un groupe personnalisé en sélectionnant des utilisateurs éligibles. Les utilisateurs éligibles sont activés pour Skype Entreprise Server et Voix Entreprise.
ms.openlocfilehash: 2b73848c05be89f08940139ee2f988493b1d1794
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737980"
---
# <a name="select-agents"></a>Sélection des agents

Les agents sont des utilisateurs désignés pour répondre aux appels Response Group. Les groupes Response Group doivent avoir un groupe d’agents affecté qui identifie les agents qui peuvent recevoir des appels pour le groupe Response Group. Pour créer un groupe d’agents, vous pouvez définir un groupe personnalisé en sélectionnant des utilisateurs éligibles. Les utilisateurs éligibles sont activés pour Skype Entreprise Server et Voix Entreprise.

La boîte de dialogue **Sélectionner des agents** permet de sélectionner les utilisateurs à ajouter à un groupe d’agents.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les contrôles de la boîte de dialogue Sélectionner des **agents.**

- **Rechercher** Recherche l’adresse SIP ou le nom complet d’un utilisateur. Entrez tout ou partie de l’adresse ou du nom. Laissez la zone de recherche vide pour afficher tous les utilisateurs activés pour Skype Entreprise Server et Voix Entreprise.

- **Nombre maximal d’utilisateurs à afficher** Modifie le nombre de résultats renvoyés qui sont affichés. Utilisez ce compteur pour limiter la recherche si vous attendez de nombreux résultats.

La liste suivante décrit les champs de la boîte de dialogue Sélectionner des **agents.**

- **Agent** Affiche les noms d’utilisateur renvoyés par la recherche.

- **Adresse SIP** Affiche les adresses SIP de l’utilisateur renvoyées par la recherche.

- **Téléphonie** Affiche la valeur du champ **Téléphonie** défini pour les utilisateurs.

- **Activé** Affiche la valeur du **champ Activé pour Lync Server** défini pour les utilisateurs.

Pour plus d’informations sur l’utilisation des groupes d’agents, voir [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) dans la documentation des opérations.