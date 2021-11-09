---
title: 'Groupes Response Group : création d’un groupe d’agents ou modification d’un groupe d’agents existant'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe Response Group (appelées agents), ainsi que les paramètres qui s’appliquent à tous les agents dans le groupe.
ms.openlocfilehash: 0c0342d59896176f8d46a74cd728c301a98ff4f6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859091"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Services Response Group : création d’un nouveau ou modification d’un groupe existant

Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe Response Group (appelées agents), ainsi que les paramètres qui s’appliquent à tous les agents dans le groupe.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les champs de la page.

- **Nom** Chaque groupe d’agents requiert un nom unique. Utilisez un nom descriptif qui identifie la fonction du groupe. Par exemple, Help Desk.

- **Description** Ce champ est facultatif. Utilisez-le pour fournir des détails supplémentaires sur le groupe.

- **Stratégie de participation** Spécifiez la façon dont les agents se connectent au groupe Response Group :

  - Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter et de se sortir. Les agents informels sont automatiquement connectés lorsqu’ils se connectent. Le paramètre par défaut est **Informel**.

  - Sélectionnez **Formel** pour spécifier que les agents du groupe doivent se connecter et se sortir. Lorsque vous sélectionnez cette option, les agents cliquent sur un élément de menu dans le client pour ouvrir un navigateur et afficher une console de page web pour la signature et la sortie.

- **Temps d’alerte (secondes)** Spécifiez le nombre de secondes de sonnerie d’un agent avant d’appeler l’agent disponible suivant. La valeur doit être d’au moins 10 secondes et inférieure à 180 secondes. La valeur par défaut est 20 secondes.

- **Méthode de routage** Sélectionnez la méthode pour déterminer l’ordre dans lequel les agents reçoivent des appels :

  - Sélectionnez **Le plus longuement inactif** pour qu’un nouvel appel soit présenté en premier à l’agent qui a été inactif (dont la présence était **Disponible** ou **Inactive**) le plus longtemps.

  - Sélectionnez **Parallèle** pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément. L’appel est envoyé au premier agent qui l’accepte.

  - Sélectionnez **Tourniquet (round robin)** pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle.

  - Sélectionnez **Série** pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel il apparaît dans la liste **Agent**.

  - Sélectionnez **Attendant** pour qu’il propose un nouvel appel à tous les agents qui sont inscrits et à l’application Response Group en même temps, quelle que soit leur présence actuelle. Les attendants et les utilisateurs clients configurés en tant qu’agents peuvent voir tous les appels en attente et répondre aux appels en attente dans n’importe quel ordre. L’appel est envoyé au premier agent qui l’accepte, et les autres attendants et utilisateurs ne voient plus l’appel.

- **Agents** Sélectionnez les utilisateurs qui doivent être des agents pour le groupe Response Group de l’une des manières suivantes :

  - Sélectionnez **Utiliser une liste de distribution** de courrier électronique existante pour utiliser une liste Exchange distribution. Tapez l’adresse de messagerie de la liste de distribution dans **Adresse de la liste de distribution**.

    > [!NOTE]
    > Vous pouvez sélectionner une seule liste de distribution pour un groupe d’agents. Si la liste de distribution inclut des listes de distribution imbriquées, ces dernières ne sont pas incluses dans le groupe d’agents.

    > [!NOTE]
    > L’ordre dans lequel les agents sont répertoriés dans la liste de distribution affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.

    > [!NOTE]
    > Les appartenances masquées ou les listes masquées peuvent devenir visibles pour les administrateurs ou les utilisateurs Response Group. Pour plus d’informations, voir Créer ou modifier un groupe [d’agents Skype Entreprise 2015.](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)

  - Sélectionnez **Définir un groupe personnalisé d’agents** pour sélectionner les utilisateurs que vous voulez attribuer en tant qu’agents pour le groupe Response Group. Cliquez sur **Sélectionner** pour ajouter un agent à la liste. Cliquez sur **Supprimer** pour supprimer un agent sélectionné de la liste.

    Les flèches Haut et Bas déplacent un agent sélectionné vers le haut et vers le bas dans la liste des agents. L’ordre des agents dans la liste affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.

Pour plus d’informations sur les fonctionnalités de Response Group, voir [Plan for the Response Group application in Skype Entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation. Pour plus d’informations sur l’utilisation des groupes d’agents, voir [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) dans la documentation des opérations.