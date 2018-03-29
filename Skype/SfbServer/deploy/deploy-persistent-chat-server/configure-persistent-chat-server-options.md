---
title: Configuration des options de serveur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Résumé : Apprenez à configurer les options de serveur de conversation persistant au niveau global, du site ou au niveau du pool dans Skype pour Business Server 2015.'
ms.openlocfilehash: 6fe06b6a5383178f0a9465624f7a0e739c2a32e6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configuration des options de serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à configurer les options de serveur de conversation persistant au niveau global, du site ou au niveau du pool dans Skype pour Business Server 2015.
  
Vous pouvez spécifier plusieurs options pour le serveur Chat persistant qui peuvent être appliquées globalement à tous les pools au sein d’un site ou à un pool spécifique au sein d’un site. Les options de serveur de conversation permanente comprennent : 
  
- Historique de conversation par défaut. Nombre de messages de conversation disponible pour chaque salle lors de la première demande. La valeur globale par défaut est de 30 messages de conversation. 
    
- Taille de fichier maximale. Taille maximale d’un fichier que vous pouvez charger sur ou télécharger d’une pièce. La valeur globale par défaut est de 20 Mo.
    
- Limite de mise à jour du participant. Nombre maximal de participants dans une salle de conversation données qui recevront des mises à jour de réunion via la conversation permanente. La valeur globale par défaut est de 75.
    
- URL de gestion d’espace. URL utilisée pour personnaliser la gestion des salles de conversation. Ce paramètre permet d’utiliser une solution personnalisée de gestion des salles. 
    
## <a name="configure-persistent-chat-server-global-options"></a>Configurer les options globales persistantes Chat Server

Pour configurer les options globales persistantes Chat Server :
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurer les options pour un pool spécifique de serveur de conversation persistant

Pour configurer les options pour un pool spécifique de serveur de conversation persistant.
  
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
    
   - Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de l’espace et que vous utilisez simplement le paramètre par défaut, laissez cette option vide.
    
    Si vous souhaitez personnaliser votre expérience de création de pièce et d’inclure votre flux de travail spécifiques de l’entreprise, vous pouvez générer une solution de gestion d’espace personnalisé en utilisant le persistant Chat Server logiciel Kit de développement (SDK), quelque part de l’hôte et placez l’URL ici. Cette URL est envoyée au client de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    

