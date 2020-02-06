---
title: Configuration d’une conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: Le déploiement de votre serveur Chat permanent peut accueillir de nombreux salles de conversation permanentes concomitantes. Les salles de conversation peuvent être organisées sous forme d’ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une seule catégorie et hérite de certains paramètres de cette catégorie. Cette organisation crée une structure pratique pour identifier les conversations en fonction de leur objectif professionnel et facilite la délégation de l’administration et la simplification de la gestion.
ms.openlocfilehash: 46d23d810b932b1295e4ad5f1c38dd3dd0990f5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822527"
---
# <a name="persistent-chat-configuration"></a>Configuration d’une conversation permanente
 
Le déploiement de votre serveur Chat permanent peut accueillir de nombreux salles de conversation permanentes concomitantes. Les salles de conversation peuvent être organisées sous forme d’ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une seule catégorie et hérite de certains paramètres de cette catégorie. Cette organisation crée une structure pratique pour identifier les conversations en fonction de leur objectif professionnel et facilite la délégation de l’administration et la simplification de la gestion.
  
> [!NOTE]
> Même si de nombreuses fonctionnalités de gestion des salles de conversation sont disponibles sur des ordinateurs exécutant une conversation permanente pour l’utilisateur, les administrateurs de chat permanent (dans le rôle **cspersistentchatadministrator** ) doivent utiliser les applets de commande du panneau de configuration ou de l’interpréteur de gestion pour créer ou gérer des catégories.
  
Les administrateurs de chat permanent utilisent le panneau de configuration Skype entreprise Server ou les applets de commande Windows PowerShell pour créer et gérer des catégories, et pour concevoir l’accès aux salles de conversation pour les utilisateurs de leur organisation.
  
Les responsables de salles de conversation permanentes qui ont la possibilité de gérer une ou plusieurs salles de conversation peuvent utiliser le client pour lancer une application Web de gestion de salle de création et de gestion des salles (ou les clients peuvent créer des solutions et des flux de travail personnalisés à appeler). conversation permanente
  
Les administrateurs de chat permanent peuvent également utiliser le panneau de configuration ou des cmdlets Windows PowerShell pour créer et gérer des salles.
  
Les responsables de salle de conversation peuvent apporter des modifications à toutes les propriétés des salles de conversation, mais ne peuvent pas modifier la catégorie de la salle. Il n’est pas possible de les empêcher d’effectuer les actions suivantes :
  
- Désactivation d’une salle de conversation
    
- Modification du nom d’une salle de conversation
    
- Modification de la description d’une salle de conversation
    
- Modification du type de salle d’une conversation (Auditorium ou Normal)
    
- Modification de la confidentialité d’une salle (ouverte, fermée ou secrète)
    
- Ajout ou suppression de membres
    
- Ajout ou suppression de gestionnaires de salle de conversation
    
- Ajout ou suppression d’un complément
    
- Modification des paramètres tels que les invitations (en fonction de ce qui est autorisé par la catégorie)
    
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **configuration de chat permanent** : configurer les options de serveur de chat permanent ou pour un pool spécifique.
  
## <a name="to-configure-persistent-chat-options-globally"></a>Pour configurer globalement les options de conversation permanente

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.
    
4. Dans la page **configuration de conversation permanente** , cliquez sur **nouveau,** puis cliquez sur **configuration de site**.
    
    > [!IMPORTANT]
    > Choisissez cette option si vous souhaitez que la configuration soit appliquée à tous les pools de serveurs de chat permanent déployés dans le site. Cliquez sur **configuration de réserve** si vous voulez que la configuration soit appliquée à un pool de serveurs de chat permanent spécifique.
  
5. Dans **Sélectionner un site**, sélectionnez le site que vous voulez configurer pour la configuration du site serveur Chat permanent.
    
6. Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
   - Dans le champ **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site existe déjà.
    
   - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation traités pour chaque salle lors de la première demande. Par défaut, 30 messages seront traités. Il s’agit de la valeur par défaut globale : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
    
     > [!IMPORTANT]
     > Le serveur de conversation permanent va mettre en cache ces messages de façon à ce que, si vous augmentez ce nombre, les messages seront mis en cache. Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche. Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation. 
  
   - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale de fichier qui peut être téléchargée dans une salle de conversation sur le système (pour lequel les téléchargements de fichiers sont activés à l’aide du paramètre **Catégorie** correspondant).
    
   - Dans **Limite de mise à jour du participant**, sélectionnez la limite pour les mises à jour de participants. Le serveur Chat permanent envoie les informations de la liste (qui est connectée à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés ait atteint ce numéro. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà du serveur de chat permanent qui cesse d’envoyer les mises à jour de la liste aux clients connectés sur les utilisateurs présents dans la salle.
    
   - (Facultatif.) Dans **URL de gestion**de la salle, sélectionnez l’URL gestion de la salle. Il s’agit de l’URL pour une gestion des salles personnalisées basée sur le Web. Si vous n’avez pas besoin de personnaliser la gestion de la salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vide. Une fois l’URL définie, elle est appliquée en tant qu’URL de gestion de la salle interne et externe.
    
     Si vous souhaitez personnaliser l’interface de création de votre salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion des salles personnalisée à l’aide du kit de développement logiciel (SDK) serveur Chat permanent, l’héberger et placer l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie d’afficher ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Pour configurer les options de conversation permanente pour un pool de serveurs de chat permanent spécifique

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server, ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.
    
4. Dans la page **Configuration de la conversation permanente**, cliquez sur **Créer**, puis sur **Configuration du pool**.
    
5. Dans **Sélectionner un service**, sélectionnez le service associé au pool de serveurs de chat permanent à configurer.
    
6. Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site du pool existe déjà.
    
   - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation traités pour chaque salle lors de la première demande. Par défaut, 30 messages seront traités. Il s’agit de la valeur par défaut globale : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
    
     > [!IMPORTANT]
     > Le serveur de conversation permanent va mettre en cache ces messages de façon à ce que, si vous augmentez ce nombre, les messages seront mis en cache. Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche. Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation. 
  
   - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale de fichier qui peut être téléchargée dans une salle de conversation sur le système (pour lequel les téléchargements de fichiers sont activés à l’aide du paramètre **Catégorie** correspondant).
    
   - Dans **Limite de mise à jour du participant**, sélectionnez la limite pour les mises à jour de participants. Le serveur Chat permanent envoie les informations de la liste (qui est connectée à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés ait atteint ce numéro. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà du serveur de chat permanent qui cesse d’envoyer les mises à jour de la liste aux clients connectés sur les utilisateurs présents dans la salle.
    
   - (Facultatif) Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de la salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vide.
    
     Si vous souhaitez personnaliser l’interface de création de votre salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion des salles personnalisée à l’aide du kit de développement logiciel (SDK) serveur Chat permanent, l’héberger et placer l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie d’afficher/de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    
## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de chat permanent, voir [planifier le serveur de chat permanent dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [déployer le serveur de conversation permanente dans skype entreprise Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [gérer le serveur de conversation permanent dans Skype entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

