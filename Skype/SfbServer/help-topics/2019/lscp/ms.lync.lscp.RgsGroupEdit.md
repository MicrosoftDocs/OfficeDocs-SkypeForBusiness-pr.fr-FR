---
title: Response Groups créer ou modifier un groupe d’agents existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe de réponse (appelées « agents »), ainsi que les paramètres qui s’appliquent à tous les agents du groupe.
ms.openlocfilehash: cde6175c6a4820ce1d2e354c6c322af05467c139
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797525"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Groupes Response Group : création d’un groupe d’agents ou modification d’un groupe d’agents existant

Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe de réponse (appelées « agents »), ainsi que les paramètres qui s’appliquent à tous les agents du groupe.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Nom** Chaque groupe d’agents nécessite un nom unique. Utilisez un nom descriptif qui identifie la fonction du groupe. Par exemple, le support technique.

- **Description** Ce champ est facultatif. Vous pouvez l’utiliser pour fournir des informations supplémentaires sur le groupe.

- **Politique de participation** Spécifiez la façon dont les agents doivent se connecter au groupe réponse :

  - Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter et de se déconnecter. Les agents informels sont connectés automatiquement lorsqu’ils se connectent. Le paramètre par défaut est **Informel**.

  - Sélectionnez **formel** pour spécifier que les agents du groupe doivent se connecter et se déconnecter. Lorsque vous sélectionnez cette option, l’agent clique sur un élément de menu dans le client pour ouvrir un navigateur et afficher une console de page Web pour se connecter et se déconnecter.

- **Durée de l’alerte (secondes)** Spécifiez le nombre de secondes qui doivent sonner un agent avant de proposer l’appel vers le prochain agent disponible. La valeur doit être au moins 10 secondes et inférieure à 180 secondes. La valeur par défaut est 20 secondes.

- **Méthode de routage** Sélectionnez la méthode permettant de déterminer l’ordre dans lequel les agents reçoivent des appels :

  - Sélectionnez **Le plus longuement inactif** pour qu’un nouvel appel soit présenté en premier à l’agent qui a été inactif (dont la présence était **Disponible** ou **Inactif(ve)**) le plus longtemps.

  - Sélectionnez **Parallèle** pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément. L’appel est envoyé au premier agent qui l’accepte.

  - Sélectionnez **Tourniquet (round robin)** pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle.

  - Sélectionnez **Série** pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils apparaissent dans la liste **Agent**.

  - Sélectionnez **surveillant** pour vous permettre d’effectuer un nouvel appel vers tous les agents connectés et l’application de groupe de réponse en même temps, quelle que soit leur présence actuelle. Les personnes et les utilisateurs qui sont configurés en tant qu’agents peuvent voir tous les appels en attente et peuvent répondre aux appels en attente dans n’importe quel ordre. L’appel est envoyé au premier agent qui l’accepte, et les autres intendants et utilisateurs ne peuvent plus voir l’appel.

- **Agent** Dans l’une des manières suivantes, sélectionnez les utilisateurs qui doivent être des agents pour le groupe de réponse :

  - Sélectionnez **utiliser une liste de distribution de courrier existante** pour utiliser une liste de distribution Exchange. Tapez l’adresse de messagerie de la liste de distribution dans **Adresse de la liste de distribution**.

    > [!NOTE]
    > Vous pouvez sélectionner une seule liste de distribution pour un groupe d’agents. Si la liste de distribution inclut des listes de distribution imbriquées, ces dernières ne sont pas incluses dans le groupe d’agents.

    > [!NOTE]
    > L’ordre dans lequel les agents sont répertoriés dans la liste de distribution affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.

    > [!NOTE]
    > Les appartenances ou listes masquées masquées peuvent être visibles par les administrateurs ou les utilisateurs du groupe réponse. Pour plus d’informations, reportez-vous à [créer ou modifier un groupe d’agents dans Skype entreprise](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).

  - Sélectionnez **Définir un groupe personnalisé d’agents** pour sélectionner les utilisateurs à affecter comme agents pour le groupe de réponse. Cliquez sur **Sélectionner** pour ajouter un agent à la liste. Cliquez sur **Supprimer** pour supprimer un agent sélectionné de la liste.

    Les flèches Haut et Bas déplacent un agent sélectionné vers le haut ou vers le bas dans la liste des agents. L’ordre des agents dans la liste affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.

Pour plus d’informations sur les fonctionnalités et les fonctionnalités des groupes de réponse, voir [planifier l’application Response Group dans Skype entreprise Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation des groupes d’agents, reportez-vous à la rubrique [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) de la documentation des opérations.


