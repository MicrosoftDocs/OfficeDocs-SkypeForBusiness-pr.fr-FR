---
title: Créer des groupes de réponse ou les modifier groupe existant de l’Agent
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe de réponse (appelées « agents »), ainsi que les paramètres qui s’appliquent à tous les agents du groupe.
ms.openlocfilehash: 4ae2869e335bc8d7d8b774f7daf7f5915dcba462
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Groupes Response Group : création d’un groupe d’agents ou modification d’un groupe d’agents existant
 
Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe de réponse (appelées « agents »), ainsi que les paramètres qui s’appliquent à tous les agents du groupe.
  
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.
  
- **Nom** Chaque groupe d’agents requiert un nom unique. Utilisez un nom descriptif qui identifie fonction du groupe. Par exemple, service d’assistance.
    
- **Description** Ce champ est facultatif. Elle permet de fournir des détails supplémentaires sur le groupe.
    
- **Stratégie de participation** Spécifier la façon dont les agents sont à signer, dans le groupe de réponse :
    
  - Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter et de se déconnecter. Les agents informels sont connectés automatiquement lorsqu’ils se connectent. Le paramètre par défaut est **Informel**.
    
  - Sélectionnez **formel** pour spécifier que les agents du groupe doivent se connecter et l’extraction. Lorsque vous sélectionnez cette option, les agents, cliquez sur un élément de menu dans le client pour ouvrir un navigateur et afficher une console de page web pour la connexion et la déconnexion.
    
- **Heure de l’alerte (secondes)** Spécifier le nombre de secondes à l’anneau d’un agent avant l’appel à l’agent disponible suivant. La valeur doit être au moins de 10 secondes et inférieur à 180 secondes. La valeur par défaut est de 20 secondes.
    
- **Méthode de routage** Sélectionnez la méthode de détermination de l’ordre dans lequel les agents reçoivent des appels :
    
  - Sélectionnez **Le plus longuement inactif** pour qu’un nouvel appel soit présenté en premier à l’agent qui a été inactif (dont la présence était **Disponible** ou **Inactif(ve)**) le plus longtemps.
    
  - Sélectionnez **Parallèle** pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément. L’appel est envoyé au premier agent qui l’accepte.
    
  - Sélectionnez **Tourniquet (round robin)** pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle.
    
  - Sélectionnez **Série** pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils apparaissent dans la liste **Agent**.
    
  - Sélectionnez **standard** pour offrir un nouvel appel à tous les agents qui sont connectés et l’application de groupe de réponse en même temps, indépendamment de leur présence en cours. Standards et les utilisateurs du client qui sont configurés comme agents peuvent voir tous les appels qui sont en attente et peuvent répondre en attente des appels dans n’importe quel ordre. L’appel est envoyé au premier agent qui l’accepte, et les autres intendants et utilisateurs ne peuvent plus voir l’appel.
    
- **Agents** Sélectionnez les utilisateurs qui doivent être des agents pour le groupe de réponse dans une des manières suivantes :
    
  - Sélectionnez l’option **utiliser une liste de distribution de courrier électronique** à utiliser une liste de distribution Exchange. Tapez l’adresse de messagerie de la liste de distribution dans **Adresse de la liste de distribution**.
    
    > [!NOTE]
    > Vous pouvez sélectionner une seule liste de distribution pour un groupe d’agents. Si la liste de distribution inclut des listes de distribution imbriquées, ces dernières ne sont pas incluses dans le groupe d’agents. 
  
    > [!NOTE]
    > L’ordre dans lequel les agents sont répertoriés dans la liste de distribution affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet. 
  
    > [!NOTE]
    > Les membres masqués ou listes masquées risquent d’être visibles pour les administrateurs de groupe de réponse ou des utilisateurs. Pour plus d’informations, consultez [créer ou modifier un groupe d’agent dans Skype pour 2015 de Business](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md). 
  
  - Sélectionnez **Définir un groupe personnalisé d’agents** pour sélectionner les utilisateurs à affecter comme agents pour le groupe de réponse. Cliquez sur **Sélectionner** pour ajouter un agent à la liste. Cliquez sur **Supprimer** pour supprimer un agent sélectionné de la liste.
    
    Les flèches Haut et Bas déplacent un agent sélectionné vers le haut ou vers le bas dans la liste des agents. L’ordre des agents dans la liste affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.
    
Pour plus d’informations sur les fonctionnalités de groupe de la réponse de, afficher un [Plan pour l’application de groupe de réponse dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) dans la documentation de planification. Pour plus d’informations sur l’utilisation de groupes d’agents, consultez [Gestion des groupes de l’Agent](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) dans la documentation sur les opérations.
  

