---
title: 'Stratégie de version du client : création d’une stratégie ou modification d’une stratégie existante'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités accessibles à l’un des clients peuvent être limitées par les capacités de l’autre client. Pour utiliser au mieux les fonctionnalités incluses dans Skype Entreprise Server 2015 et améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions des clients utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de plusieurs versions du client.
ms.openlocfilehash: c6674d1efcc7791511870234754876b966f492a4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389236"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Stratégie de version du client : création d’une nouvelle ou modification d’une stratégie existante

Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités accessibles à l’un des clients peuvent être limitées par les capacités de l’autre client. Pour utiliser au mieux les fonctionnalités incluses dans Skype Entreprise Server 2015 et améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions des clients utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de plusieurs versions du client.

> [!IMPORTANT]
> Les filtres sont répertoriés par ordre de priorité. Par exemple, si un premier filtre autorise les clients exécutant la version 1.5 à se connecter et qu’un second filtre bloque les clients exécutant une version antérieure à la version 2.0, le premier filtre est prioritaire : les clients exécutant la version 1.5 peuvent donc se connecter.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Nouvelle stratégie de version du client** ou **Modifier la stratégie de version du client** :

- Ajouter ou modifier le nom ou la description de la stratégie de version du client

- Ajouter ou modifier des règles de version de client pour la stratégie de version du client

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.

- **Étendue** Identifie l’étendue (site, pool ou utilisateur) de la stratégie de version du client.

- **Nom** Vous pouvez ajouter ou modifier le nom de la stratégie de version du client.

- **Description** Vous pouvez ajouter une description pour vous aider à identifier la stratégie dans la liste de la page Stratégie de version du client.

- **Nouveau** Vous pouvez ajouter une nouvelle règle de version du client à la stratégie.

- **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’une règle de version du client.

- **Supprimer** Cette option supprime la règle de version du client sélectionnée de la stratégie.

- **Flèches haut et bas** Cette option déplace la règle de version du client sélectionnée vers le haut ou vers le bas en priorité. Les règles sont traitées dans l’ordre répertorié.

Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies de version du client, voir [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) dans la documentation des opérations.