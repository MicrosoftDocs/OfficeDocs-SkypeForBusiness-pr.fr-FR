---
title: Stratégie de la version du client création d’un nouveau ou modification existante
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client.
ms.openlocfilehash: c08c709d4a8db20a23580c5a5bfd2ceaf823e028
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691619"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Stratégie de version du client : création d’une stratégie ou modification d’une stratégie existante

Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client. Pour tirer le meilleur parti des fonctionnalités incluses dans Skype entreprise Server et pour améliorer l’environnement utilisateur global, vous pouvez utiliser le filtre de version du client pour restreindre les versions de client utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.

> [!IMPORTANT]
> Les filtres sont répertoriés par ordre de priorité. Par exemple, si un premier filtre autorise les clients exécutant la version 1.5 à se connecter et qu’un second filtre bloque les clients exécutant une version antérieure à la version 2.0, le premier filtre est prioritaire : les clients exécutant la version 1.5 peuvent donc se connecter.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouvelle stratégie de version du client** ou **Modifier la stratégie de version du client**, vous pouvez effectuer les tâches suivantes :

- Ajout ou modification du nom ou de la description de la stratégie de version du client

- Ajout ou modification des règles de version de client pour la stratégie de version du client

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.

- **Scope** Identifie l’étendue (site, pool ou utilisateur) de la stratégie de version du client.

- **Nom** Vous pouvez ajouter ou modifier le nom de la stratégie de version du client.

- **Description** Vous pouvez ajouter une description pour faciliter l’identification de la stratégie dans la liste de la page de stratégie de version du client.

- **Nouvelle** Vous pouvez ajouter une nouvelle règle de version du client à la stratégie.

- **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’une règle de version de client.

- **Supprimer** Cette option supprime la règle de version de client sélectionnée de la stratégie.

- **Flèches haut et bas** Cette option déplace la règle de version de client sélectionnée vers le haut ou le bas dans priorité. Les règles sont traitées dans l’ordre indiqué.

Pour plus d’informations sur l’interopérabilité entre les clients et les versions de client, voir [interopérabilité client](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx). Pour plus d’informations sur l’utilisation des stratégies de version du client, reportez-vous à la rubrique[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) de la documentation des opérations.

