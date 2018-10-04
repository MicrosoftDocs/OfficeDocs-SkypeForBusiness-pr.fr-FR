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
description: 'Résumé : Apprenez à configurer les options de serveur de conversation permanente au niveau global, site ou au niveau du pool Skype pour Business Server 2015.'
ms.openlocfilehash: 5d8bf63332ca991117e0fbd3beddc97855617274
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375999"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configuration des options de serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à configurer les options de serveur de conversation permanente au niveau global, site ou au niveau du pool Skype pour Business Server 2015.
  
Vous pouvez spécifier plusieurs options for Persistent Chat Server qui peuvent être appliqués au niveau global, à tous les pools au sein d’un site ou à un pool spécifique au sein d’un site. Les options de serveur de conversation permanente comprennent : 
  
- Historique de conversation par défaut. Nombre de messages de conversation disponible pour chaque salle lors de la première demande. La valeur globale par défaut est de 30 messages de conversation. 
    
- Taille de fichier maximale. Taille maximale d’un fichier que vous pouvez charger sur ou télécharger d’une pièce. La valeur globale par défaut est de 20 Mo.
    
- Limite de mise à jour du participant. Nombre maximal de participants dans une salle de conversation données qui recevront des mises à jour de réunion via la conversation permanente. La valeur globale par défaut est de 75.
    
- URL de gestion de salle. URL utilisée pour personnaliser la gestion des salles de conversation. Ce paramètre permet d’utiliser une solution personnalisée de gestion des salles. 
   
> [!NOTE] 
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurer les options globales du serveur de conversation permanente

Pour configurer les options globales du serveur de conversation permanente :
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurer les options pour un pool de serveurs de conversation permanente spécifique

Pour configurer les options pour un pool de serveurs de conversation permanente spécifique.
  
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
    
   - Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vide.
    
     Si vous souhaitez personnaliser votre expérience de création de salle et inclure votre flux de travail spécifiques de l’entreprise, vous pouvez créer une solution de gestion de salle personnalisé à l’aide de la Persistent Chat Server logiciel Kit de développement (SDK), héberger quelque part et placez l’URL ici. Cette URL est envoyée au client de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    

