---
title: Stratégie de Version de client, créer ou modifier une existante
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client. Pour rendre l’utilisation de plus de fonctionnalités incluses dans Skype pour Business Server 2015 et d’améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de la version client pour restreindre les versions de client qui sont utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.
ms.openlocfilehash: 6c1e895dc03d094013f41a34cb21a12a24928172
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Stratégie de version du client : création d’une stratégie ou modification d’une stratégie existante
 
Vous pouvez spécifier la version des clients pris en charge dans votre environnement. Quand deux clients exécutant des versions distinctes interagissent, les fonctionnalités disponibles pour l’un des clients peuvent être restreintes par les fonctions de l’autre client. Pour rendre l’utilisation de plus de fonctionnalités incluses dans Skype pour Business Server 2015 et d’améliorer l’expérience utilisateur globale, vous pouvez utiliser le filtre de la version client pour restreindre les versions de client qui sont utilisées dans votre environnement. Le filtre de version du client vous permet également de réduire les coûts associés à la prise en charge de différentes versions du client.
  
> [!IMPORTANT]
> Les filtres sont répertoriés par ordre de priorité. Par exemple, si un premier filtre autorise les clients exécutant la version 1.5 à se connecter et qu’un second filtre bloque les clients exécutant une version antérieure à la version 2.0, le premier filtre est prioritaire : les clients exécutant la version 1.5 peuvent donc se connecter. 
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Nouvelle stratégie de version du client** ou **Modifier la stratégie de version du client**, vous pouvez effectuer les tâches suivantes :
  
- Ajout ou modification du nom ou de la description de la stratégie de version du client
    
- Ajout ou modification des règles de version de client pour la stratégie de version du client
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
- **Champ d’application** Identifie l’étendue (Site, liste ou utilisateur) de la stratégie de version de client.
    
- **Nom** Vous pouvez ajouter ou modifier le nom de la stratégie de version de client.
    
- **Description** Vous pouvez ajouter une description pour aider à identifier la stratégie dans la liste sur la page Stratégie de Version de Client.
    
- **Nouveau** Vous pouvez ajouter une nouvelle règle de la version client de la stratégie.
    
- **Afficher les détails** Cette option ouvre une boîte de dialogue dans laquelle vous pouvez modifier les options pour une règle de la version client.
    
- **Supprimer** Cette option supprime la règle de la version client sélectionné à partir de la stratégie.
    
- **Flèches haut et bas** Cette option déplace la règle de la version client sélectionné vers le haut ou vers le bas dans la zone priorité. Les règles sont traitées dans l’ordre indiqué.
    
Pour plus d’informations sur l’interopérabilité entre les clients et les versions de client, consultez [Interopérabilité du Client dans Microsoft Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies de version de client, reportez-vous à la section [spécifier le Client Versions prises en charge dans votre organisation](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) dans la documentation sur les opérations.

