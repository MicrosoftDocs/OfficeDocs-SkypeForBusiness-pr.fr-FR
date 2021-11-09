---
title: Stratégie de version du client
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités accessibles à l’un des clients peuvent être limitées par les capacités de l’autre client.
ms.openlocfilehash: 1a32329574b95ed4b918d5b323bc63f86331f617
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841846"
---
# <a name="client-version-policy"></a>Stratégie de version du client

Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités accessibles à l’un des clients peuvent être limitées par les capacités de l’autre client. Pour utiliser au mieux les fonctionnalités incluses dans Skype Entreprise Server et améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions des clients utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de plusieurs versions du client.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Stratégie de version du client** :

- Modifiez la **stratégie** de version du client par défaut ( globale).

- Créer des stratégies de version du client pour un site ou un pool particulier.

- Créer des stratégies de version du client qui peuvent être attribuées à des utilisateurs individuels.

> [!NOTE]
> Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifique, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.

- **Nouveau** Vous pouvez créer une ou plusieurs des stratégies de version des clients suivantes :

  - Stratégie de site

  - Stratégie de pool

  - Stratégie de l’utilisateur

- **Modifier** Vous pouvez modifier les options de n’importe quelle stratégie de version du client. À l’aide de cette option, vous pouvez effectuer les opérations suivantes :

  - **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options d’une stratégie de version du client.

  - **Sélectionner tout** Cette option sélectionne toutes les stratégies de version des clients dans la liste.

  - **Supprimer** Cette option supprime toutes les stratégies de version des clients sélectionnées.

- **Actualiser** Vous pouvez actualiser la liste des stratégies de version des clients pour vérifier l’état des options de toutes les stratégies de version des clients.

Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, voir [Interopérabilité](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) du client dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies de version du client, voir [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) dans la documentation des opérations.