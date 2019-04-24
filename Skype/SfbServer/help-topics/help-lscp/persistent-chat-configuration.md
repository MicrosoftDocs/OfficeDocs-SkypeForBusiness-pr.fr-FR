---
title: Configuration d’une conversation permanente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: Votre déploiement Persistent Chat Server peut héberger plusieurs salles de conversation permanente simultanés. Les salles de conversation peuvent être organisées sous forme d’ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une seule catégorie et hérite de certains paramètres de cette catégorie. Cette organisation crée une structure pratique pour identifier les conversations en fonction de leur objectif professionnel et facilite la délégation de l’administration et la simplification de la gestion.
ms.openlocfilehash: 653649e765d8b912ff7090cbadcccf2cc6439c47
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200673"
---
# <a name="persistent-chat-configuration"></a>Configuration d’une conversation permanente
 
Votre déploiement Persistent Chat Server peut héberger plusieurs salles de conversation permanente simultanés. Les salles de conversation peuvent être organisées sous forme d’ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une seule catégorie et hérite de certains paramètres de cette catégorie. Cette organisation crée une structure pratique pour identifier les conversations en fonction de leur objectif professionnel et facilite la délégation de l’administration et la simplification de la gestion.
  
> [!NOTE]
> Bien que de nombreuses fonctionnalités de gestion des salles de conversation sont disponibles sur les ordinateurs exécutant la conversation permanente pour l’utilisateur, les administrateurs de conversation permanente (dans le rôle **cspersistentchatadministrator** ) doit utiliser soit le contrôle Panneau de configuration ou la gestion de shell applets de commande pour créer ou gérer les catégories.
  
Les administrateurs de conversation permanente Utilisez Skype pour les applets de commande Business Server Control Panel ou de Windows PowerShell créer et gérer les catégories et pour l’accès en création pour les salles de conversation pour les utilisateurs de leur organisation.
  
Responsables de salle de conversation permanente, qui ont la possibilité de gérer un ou plusieurs des salles de conversation, peuvent utiliser le client pour lancer une application Web pour créer et gérer des salles de gestion des salles (ou les clients peuvent créer des solutions personnalisées et des flux de travail à appeler). conversation permanente
  
Administrateurs de conversation permanentes peuvent également utiliser le panneau de configuration ou des applets de commande Windows PowerShell pour créer et gérer des salles.
  
Les responsables de salle de conversation peuvent apporter des modifications à toutes les propriétés des salles de conversation, mais ne peuvent pas modifier la catégorie de la salle. Il n’est pas possible de les empêcher d’effectuer les actions suivantes :
  
- Désactivation d’une salle de conversation
    
- Modification du nom d’une salle de conversation
    
- Modification de la description d’une salle de conversation
    
- Modification du type de salle d’une conversation (Auditorium ou Normal)
    
- Modification de la confidentialité d’une salle (ouverte, fermée ou secrète)
    
- Ajout ou suppression de membres
    
- Ajout ou suppression de gestionnaires de salle de conversation
    
- Ajout ou suppression d’un complément
    
- Modification des paramètres tels que les invitations (selon ce qui est autorisé par la catégorie)
    
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Configuration de conversation permanente** : configurer les options de serveur de conversation permanente globalement ou pour un pool spécifique.
  
## <a name="to-configure-persistent-chat-options-globally"></a>Pour configurer les options de conversation permanente au niveau global

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.
    
4. Dans la page **Configuration de conversation permanente** , cliquez sur **Nouveau** , puis sur **configuration du Site**.
    
    > [!IMPORTANT]
    > Choisissez cette option si vous souhaitez que la configuration soit appliqué à tous les pools Persistent Chat Server déployés dans le site. Si vous souhaitez que la configuration soit appliqué à un pool de serveurs de conversation permanente spécifique, cliquez sur **Configuration du Pool** .
  
5. Dans **Sélectionner un Site**, sélectionnez le site à configurer pour la configuration du site Persistent Chat Server.
    
6. Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
   - Dans le champ **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site existe déjà.
    
   - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation traités pour chaque salle lors de la première demande. Par défaut, 30 messages seront traités. Il s’agit de la valeur par défaut globale : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
    
     > [!IMPORTANT]
     > Persistent Chat Server met en cache les messages en mémoire, donc si vous augmentez ce numéro, plus de messages sont mis en cache. Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche. Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation. 
  
   - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale de fichier qui peut être téléchargée dans une salle de conversation sur le système (pour lequel les téléchargements de fichiers sont activés à l’aide du paramètre **Catégorie** correspondant).
    
   - Dans **Limite de mise à jour du participant**, sélectionnez la limite pour les mises à jour de participants. Persistent Chat Server envoie les informations de liste (qui sont connectées à une salle de conversation) à tous les participants jusqu'à ce que le nombre d’utilisateurs connectés atteint ce numéro. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà duquel Persistent Chat Server cesse d’envoyer des mises à jour de la liste des participants aux clients connectés qui est présente dans la salle.
    
   - (Facultatif). Dans l' **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL pour une gestion de salle de personnalisée basée sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vide. Une fois que l’URL est définie, elle est appliquée en tant que l’URL gestion salle internes et externes.
    
     Si vous souhaitez personnaliser votre expérience de création de salle et inclure votre flux de travail spécifiques de l’entreprise, vous pouvez créer une solution de gestion de salle personnalisé à l’aide de la Persistent Chat Server logiciel Kit de développement (SDK), héberger quelque part et placez l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie d’afficher ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Pour configurer les options de conversation permanente pour un pool de serveurs de conversation permanente spécifique

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server, ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.
    
4. Dans la page **Configuration de la conversation permanente**, cliquez sur **Créer**, puis sur **Configuration du pool**.
    
5. Dans **Sélectionner un Service**, sélectionnez le service associé au pool de serveurs de conversation permanente à configurer.
    
6. Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site du pool existe déjà.
    
   - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation traités pour chaque salle lors de la première demande. Par défaut, 30 messages seront traités. Il s’agit de la valeur par défaut globale : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
    
     > [!IMPORTANT]
     > Persistent Chat Server met en cache les messages en mémoire, donc si vous augmentez ce numéro, plus de messages sont mis en cache. Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche. Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation. 
  
   - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale de fichier qui peut être téléchargée dans une salle de conversation sur le système (pour lequel les téléchargements de fichiers sont activés à l’aide du paramètre **Catégorie** correspondant).
    
   - Dans **Limite de mise à jour du participant**, sélectionnez la limite pour les mises à jour de participants. Persistent Chat Server envoie les informations de liste (qui sont connectées à une salle de conversation) à tous les participants jusqu'à ce que le nombre d’utilisateurs connectés atteint ce numéro. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà duquel Persistent Chat Server cesse d’envoyer des mises à jour de la liste des participants aux clients connectés qui est présente dans la salle.
    
   - (Facultatif) Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vide.
    
     Si vous souhaitez personnaliser votre expérience de création de salle et inclure votre flux de travail spécifiques de l’entreprise, vous pouvez créer une solution de gestion de salle personnalisé à l’aide de la Persistent Chat Server logiciel Kit de développement (SDK), héberger quelque part et placez l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie d’afficher/de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    
## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur le serveur de conversation permanente des fonctionnalités, voir [Plan for Persistent Chat Server dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [déployer Persistent Chat Server dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [gérer le serveur de conversation permanente dans Skype pour Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

