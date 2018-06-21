---
title: Groupes de réponses créer une nouvelle ou en modifier le groupe d’agents existant
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe de réponse (appelées « agents »), ainsi que les paramètres qui s’appliquent à tous les agents du groupe.
ms.openlocfilehash: af09b13d6fc6853a43719688b0f97ab60c20990f
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988445"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>Groupes Response Group : création d’un groupe d’agents ou modification d’un groupe d’agents existant
 
Les groupes d’agents définissent les personnes qui peuvent répondre aux appels adressés à un groupe de réponse (appelées « agents »), ainsi que les paramètres qui s’appliquent à tous les agents du groupe.
  
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.
  
- **Nom** Chaque groupe d’agents requiert un nom unique. Utilisez un nom descriptif qui identifie la fonction du groupe. Par exemple, Help Desk.
    
- **Description** Ce champ est facultatif. Utilisez-le pour fournir des détails supplémentaires sur le groupe.
    
- **Stratégie de participation** Spécifier la façon dont les agents doivent se connecter dans le service response group :
    
  - Sélectionnez **Informel** pour spécifier que les agents du groupe n’ont pas besoin de se connecter et de se déconnecter. Les agents informels sont connectés automatiquement lorsqu’ils se connectent. Le paramètre par défaut est **Informel**.
    
  - Sélectionnez **formelle** pour spécifier que les agents du groupe doivent se connecter et se déconnecter. Lorsque vous sélectionnez cette option, les agents, cliquez sur un élément de menu dans le client, ouvrez un navigateur et afficher une console de page web pour la signature et se déconnecter.
    
- **Heure d’alerte (secondes)** Spécifier le nombre de secondes d’agent sonner avant d’acheminer l’appel vers l’agent disponible suivant. La valeur doit être au moins 10 et moins de 180 secondes. La valeur par défaut est 20 secondes.
    
- **Méthode de routage** Sélectionnez la méthode permettant de déterminer l’ordre dans lequel les agents reçoivent des appels :
    
  - Sélectionnez **Le plus longuement inactif** pour qu’un nouvel appel soit présenté en premier à l’agent qui a été inactif (dont la présence était **Disponible** ou **Inactif(ve)**) le plus longtemps.
    
  - Sélectionnez **Parallèle** pour qu’un nouvel appel soit présenté à tous les agents disponibles simultanément. L’appel est envoyé au premier agent qui l’accepte.
    
  - Sélectionnez **Tourniquet (round robin)** pour qu’un nouvel appel soit présenté à chaque agent, à tour de rôle.
    
  - Sélectionnez **Série** pour qu’un nouvel appel soit toujours présenté aux agents dans l’ordre dans lequel ils apparaissent dans la liste **Agent**.
    
  - Sélectionnez **standard** pour offrir un nouvel appel à tous les agents connectés et l’application Response Group en même temps, indépendamment de leur présence en cours. Standards et les utilisateurs du client qui sont configurés comme les agents peuvent voir tous les appels en attente et peuvent répondre aux appels en attente dans n’importe quel ordre. L’appel est envoyé au premier agent qui l’accepte, et les autres intendants et utilisateurs ne peuvent plus voir l’appel.
    
- **Agents** Sélectionnez les utilisateurs qui doivent être des agents pour le service response group d’une des manières suivantes :
    
  - Sélectionnez **utiliser une liste de distribution de courrier électronique existante** pour utiliser une liste de distribution Exchange. Tapez l’adresse de messagerie de la liste de distribution dans **Adresse de la liste de distribution**.
    
    > [!NOTE]
    > Vous pouvez sélectionner une seule liste de distribution pour un groupe d’agents. Si la liste de distribution inclut des listes de distribution imbriquées, ces dernières ne sont pas incluses dans le groupe d’agents. 
  
    > [!NOTE]
    > L’ordre dans lequel les agents sont répertoriés dans la liste de distribution affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet. 
  
    > [!NOTE]
    > Appartenances masquées ou les listes masquées peuvent devenir visibles pour les administrateurs de Response Group ou aux utilisateurs. Pour plus d’informations, voir [créer ou modifier un groupe d’agents dans Skype pour les entreprises](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md). 
  
  - Sélectionnez **Définir un groupe personnalisé d’agents** pour sélectionner les utilisateurs à affecter comme agents pour le groupe de réponse. Cliquez sur **Sélectionner** pour ajouter un agent à la liste. Cliquez sur **Supprimer** pour supprimer un agent sélectionné de la liste.
    
    Les flèches Haut et Bas déplacent un agent sélectionné vers le haut ou vers le bas dans la liste des agents. L’ordre des agents dans la liste affecte l’ordre dans lequel les agents reçoivent des appels pour le routage en série et de tourniquet.
    
Pour plus d’informations sur les fonctionnalités de Response Group, voir [planification de l’application Response Group dans Skype pour Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md). Pour plus d’informations sur l’utilisation des groupes d’agents, voir [Gestion des groupes d’agents](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) dans la documentation des opérations.
  

