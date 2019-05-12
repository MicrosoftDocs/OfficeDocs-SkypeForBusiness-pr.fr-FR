---
title: Stratégie de Version du client créer ou modifier une existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client. Pour utiliser plus de fonctionnalités incluses dans Skype pour Business Server 2015 et pour améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions du client qui sont utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.
ms.openlocfilehash: d77a6339cf7a84dbce81786b03fde9a550614846
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926823"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Stratégie de version du client : création d’une stratégie ou modification d’une stratégie existante

Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client. Pour utiliser plus de fonctionnalités incluses dans Skype pour Business Server 2015 et pour améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de version du client pour limiter les versions du client qui sont utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.

> [!IMPORTANT]
> Les filtres sont répertoriés par ordre de priorité. Par exemple, si un premier filtre autorise les clients exécutant la version 1.5 à se connecter et qu’un second filtre bloque les clients exécutant une version antérieure à la version 2.0, le premier filtre est prioritaire : les clients exécutant la version 1.5 peuvent donc se connecter.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouvelle stratégie de version du client** ou **Modifier la stratégie de version du client**, vous pouvez effectuer les tâches suivantes :

- Ajout ou modification du nom ou de la description de la stratégie de version du client

- Ajout ou modification des règles de version de client pour la stratégie de version du client

## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.

- **Étendue** Identifie l’étendue (Pool, Site ou utilisateur) de la stratégie de version du client.

- **Nom** Vous pouvez ajouter ou modifier le nom de la stratégie de version du client.

- **Description** Vous pouvez ajouter une description pour aider à identifier la stratégie dans la liste dans la page Stratégie de Version du Client.

- **Nouveau** Vous pouvez ajouter une nouvelle règle de version de client à la stratégie.

- **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options pour une règle de version du client.

- **Supprimer** Cette option supprime la règle de version de client sélectionnée de la stratégie.

- **Flèches haut et bas** Cette option déplace la règle de version de client sélectionnée monter ou Descendre dans la priorité. Les règles sont traitées dans l’ordre indiqué.

Pour plus d’informations sur l’interopérabilité entre les clients et les versions des clients, reportez-vous à la rubrique [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) de la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies de version du client, reportez-vous à la rubrique[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) de la documentation des opérations.

