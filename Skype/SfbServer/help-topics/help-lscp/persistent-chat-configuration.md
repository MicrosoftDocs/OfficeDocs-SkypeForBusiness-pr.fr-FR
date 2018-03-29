---
title: Configuration d’une conversation permanente
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
description: Votre déploiement de serveur persistant de Chat peut héberger plusieurs salles de Chat persistantes simultanées. Les salles de conversation peuvent être organisées sous forme d’ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une seule catégorie et hérite de certains paramètres de cette catégorie. Cette organisation crée une structure pratique pour identifier les conversations en fonction de leur objectif professionnel et facilite la délégation de l’administration et la simplification de la gestion.
ms.openlocfilehash: c4408ebd4417d2cf825620837da018ef30f725c9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-configuration"></a>Configuration d’une conversation permanente
 
Votre déploiement de serveur persistant de Chat peut héberger plusieurs salles de Chat persistantes simultanées. Les salles de conversation peuvent être organisées sous forme d’ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une seule catégorie et hérite de certains paramètres de cette catégorie. Cette organisation crée une structure pratique pour identifier les conversations en fonction de leur objectif professionnel et facilite la délégation de l’administration et la simplification de la gestion.
  
> [!NOTE]
> Bien que la plupart des fonctionnalités de gestion de salles de conversation sont disponibles sur les ordinateurs exécutant la conversation permanent pour l’utilisateur, administrateurs de Chat persistant (dans le rôle **cspersistentchatadministrator** ) devez utiliser soit le contrôle panneau ou management shell applets de commande pour créer ou gérer des catégories.
  
Administrateurs de Chat persistant utiliser Skype pour les applets de commande de panneau de configuration de Business Server ou de Windows PowerShell créer et gérer des catégories et d’accès en conception de salles de conversation pour les utilisateurs dans leur organisation.
  
Responsables de la salle de conversation permanent, qui ont la possibilité de gérer une ou plusieurs salles de conversation, peuvent utiliser le client à lancer une application Web pour créer et gérer des salles de gestion salle (ou les clients peuvent créer des solutions personnalisées et les workflows à appeler). conversation permanente
  
Administrateurs de conversation permanents permet également le panneau de configuration ou des applets de commande Windows PowerShell pour créer et gérer des salles.
  
Les responsables de salle de conversation peuvent apporter des modifications à toutes les propriétés des salles de conversation, mais ne peuvent pas modifier la catégorie de la salle. Il n’est pas possible de les empêcher d’effectuer les actions suivantes :
  
- Désactivation d’une salle de conversation
    
- Modification du nom d’une salle de conversation
    
- Modification de la description d’une salle de conversation
    
- Modification du type de salle d’une conversation (Auditorium ou Normal)
    
- Modification de la confidentialité d’une salle (ouverte, fermée ou secrète)
    
- Ajout ou suppression de membres
    
- Ajout ou suppression de gestionnaires de salle de conversation
    
- Ajout ou suppression d’un complément
    
- Modification des paramètres, tels que des invitations (en fonction de ce qui est autorisé par la catégorie)
    
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Configuration de Chat persistant** : configurer les options de serveur de conversation persistant globalement ou pour un pool spécifique.
  
## <a name="to-configure-persistent-chat-options-globally"></a>Pour configurer les options de Chat persistant globalement

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.
    
4. Sur la page de **Configuration permanente de Chat** , cliquez sur **Nouveau** et puis cliquez sur **configuration du Site**.
    
    > [!IMPORTANT]
    > Choisissez cette option si vous souhaitez que la configuration soit appliquée à tous les pools persistant Chat Server déployés dans le site. Si vous souhaitez que la configuration soit appliquée à un pool spécifique de serveur de conversation permanent, cliquez sur **Configuration de Pool** .
  
5. Dans la zone **Sélectionnez un Site**, sélectionnez le site à configurer pour la configuration de site de serveur de conversation persistant.
    
6. Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
  - Dans le champ **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site existe déjà.
    
  - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation traités pour chaque salle lors de la première demande. Par défaut, 30 messages seront traités. Il s’agit de la valeur par défaut globale : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
    
    > [!IMPORTANT]
    > Persistant Chat Server met en cache ces messages en mémoire, donc si vous augmentez ce nombre, plus les messages sont mis en cache. Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche. Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation. 
  
  - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale de fichier qui peut être téléchargée dans une salle de conversation sur le système (pour lequel les téléchargements de fichiers sont activés à l’aide du paramètre **Catégorie** correspondant).
    
  - Dans **Limite de mise à jour du participant**, sélectionnez la limite pour les mises à jour de participants. Serveur de conversation persistant envoie des informations de liste (ce qui sont connectées à une salle de conversation) à tous les participants jusqu'à ce que le nombre d’utilisateurs connectés atteint ce nombre. Par défaut, cette limite est de 75. Cette limite est le nombre maximal de participants dans un espace donné, au-delà de laquelle persistant Chat Server cesse d’envoyer des mises à jour de la liste aux clients connectés qui est présente dans la salle.
    
  - (Facultatif). **URL de gestion d’espace**, sélectionnez l’URL de gestion d’espace. Il s’agit de l’URL pour une gestion basée sur le web un espace personnalisé. Si vous n’avez pas besoin de personnaliser la gestion de l’espace et que vous utilisez simplement le paramètre par défaut, laissez cette option vide. Une fois que l’URL est définie, elle est appliquée comme les deux URL de gestion internes et externes de salle.
    
    Si vous souhaitez personnaliser votre expérience de création de pièce et d’inclure votre flux de travail spécifiques de l’entreprise, vous pouvez générer une solution de gestion d’espace personnalisé en utilisant le persistant Chat Server logiciel Kit de développement (SDK), quelque part de l’hôte et placez l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie d’afficher ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Pour configurer les options de Chat persistants pour un pool spécifique de serveur de conversation persistant

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server, ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.
    
4. Dans la page **Configuration de la conversation permanente**, cliquez sur **Créer**, puis sur **Configuration du pool**.
    
5. Dans la zone **Sélectionnez un Service**, sélectionnez le service associé au pool persistant Chat Server à configurer.
    
6. Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
  - Dans **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site du pool existe déjà.
    
  - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation traités pour chaque salle lors de la première demande. Par défaut, 30 messages seront traités. Il s’agit de la valeur par défaut globale : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
    
    > [!IMPORTANT]
    > Persistant Chat Server met en cache ces messages en mémoire, donc si vous augmentez ce nombre, plus les messages sont mis en cache. Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche. Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation. 
  
  - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale de fichier qui peut être téléchargée dans une salle de conversation sur le système (pour lequel les téléchargements de fichiers sont activés à l’aide du paramètre **Catégorie** correspondant).
    
  - Dans **Limite de mise à jour du participant**, sélectionnez la limite pour les mises à jour de participants. Serveur de conversation persistant envoie des informations de liste (ce qui sont connectées à une salle de conversation) à tous les participants jusqu'à ce que le nombre d’utilisateurs connectés atteint ce nombre. Par défaut, cette limite est de 75. Cette limite est le nombre maximal de participants dans un espace donné, au-delà de laquelle persistant Chat Server cesse d’envoyer des mises à jour de la liste aux clients connectés qui est présente dans la salle.
    
  - (Facultatif) Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de l’espace et que vous utilisez simplement le paramètre par défaut, laissez cette option vide.
    
    Si vous souhaitez personnaliser votre expérience de création de pièce et d’inclure votre flux de travail spécifiques de l’entreprise, vous pouvez générer une solution de gestion d’espace personnalisé en utilisant le persistant Chat Server logiciel Kit de développement (SDK), quelque part de l’hôte et placez l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie d’afficher/de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    
### 

Pour plus d’informations sur les fonctionnalités de serveur de conversation persistant de, voir [planification serveur Chat persistant dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [déployer le serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [Gérer permanent Chat Server dans Skype pour Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

