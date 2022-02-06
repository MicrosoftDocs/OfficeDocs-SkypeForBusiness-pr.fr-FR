---
title: Configurer les options du serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Résumé : Découvrez comment configurer les options du serveur de conversation permanente au niveau global, du site ou du pool dans Skype Entreprise Server 2015.'
---

# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurer les options du serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment configurer les options du serveur de conversation permanente au niveau global, du site ou du pool dans Skype Entreprise Server 2015.
  
Vous pouvez spécifier plusieurs options pour le serveur de conversation permanente qui peuvent être appliquées globalement, à tous les pools au sein d’un site ou à un pool spécifique au sein d’un site. Les options de serveur de conversation permanente sont les suivantes : 
  
- Historique de conversation par défaut. Nombre de messages de conversation disponibles pour chaque salle de conversation lors de la première demande. La valeur globale par défaut est de 30 messages de conversation. 
    
- Taille maximale du fichier. Taille maximale d’un fichier qui peut être téléchargé à partir d’une salle. La valeur par défaut globale est 20 Mo.
    
- Limite de mise à jour des participants. Nombre maximal de participants dans une salle de conversation donnée pour lequel la conversation permanente enverra des mises à jour de listes. La valeur par défaut globale est 75.
    
- URL de gestion de salle. URL utilisée pour la gestion personnalisée des salles de conversation. Le paramètre permet l’utilisation d’une solution de gestion de salle personnalisée. 
   
> [!NOTE] 
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurer les options globales du serveur de conversation permanente

Pour configurer les options globales du serveur de conversation permanente :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer**, sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.
    
4. Dans la page **Configuration de la conversation permanente** , cliquez **sur Nouveau,** puis sur **Configuration du site**.
    
    > [!IMPORTANT]
    > Choisissez cette option si vous souhaitez que la configuration soit appliquée à tous les pools de serveurs de conversation permanente déployés sur le site. Cliquez **sur Configuration du pool** si vous souhaitez que la configuration soit appliquée à un pool de serveurs de conversation permanente spécifique.
  
5. Dans **Sélectionner un site**, sélectionnez le site à configurer pour la configuration du site serveur de conversation permanente.
    
6. Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site existe déjà
    
   - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation qui seront traités pour chaque salle lors de la première demande. Par défaut, 30 messages sont traités. Il s’agit du paramètre global par défaut : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
    
     > [!IMPORTANT]
     > Le serveur de conversation permanente met en cache ces messages en mémoire. Ainsi, si vous augmentez ce nombre, davantage de messages seront mis en cache. Vous pouvez toujours accéder au contenu historique par recherche. Le numéro par défaut détermine simplement le nombre maximal de messages que vous voyez initialement lors de la connexion à une salle de conversation. 
  
   - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale pour un fichier qui peut être téléchargée vers une salle de conversation dans le système (pour lequel les téléchargements de fichiers sont activés par le biais du paramètre **Catégorie** correspondant).
    
   - Dans **Limite de mise à jour du participant :**, sélectionnez la limite pour les mises à jour de participants. Le serveur de conversation permanente envoie des informations de liste (qui est connecté à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés atteigne ce nombre. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà duquel le serveur de conversation permanente cesse d’envoyer des mises à jour de liste aux clients connectés sur les personnes présentes dans la salle.
    
   - (Facultatif.) Dans **l’URL de gestion de** salle, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’une gestion de salle personnalisée basée sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vide. Une fois l’URL définie, elle est appliquée comme URL de gestion de salle interne et externe.
    
     Si vous souhaitez personnaliser votre expérience de création de salle et inclure votre flux de travail d’entreprise spécifique, vous pouvez créer une solution de gestion de salle personnalisée à l’aide du Kit de développement logiciel (SDK) du serveur de conversation permanente, l’héberger quelque part et placer l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurer les options pour un pool de serveurs de conversation permanente spécifique

Pour configurer les options d’un pool de serveurs de conversation permanente spécifique.
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer**, sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server, ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.
    
4. Dans la page **Configuration de la conversation permanente**, cliquez sur **Nouveau**, puis sur **Configuration du pool**.
    
5. Dans **Sélectionner un service**, sélectionnez le service associé au pool de serveurs de conversation permanente à configurer.
    
6. Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site du pool existe déjà
    
   - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation qui seront traités pour chaque salle lors de la première demande. Par défaut, 30 messages sont traités. Il s’agit du paramètre global par défaut : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
    
     > [!IMPORTANT]
     > Le serveur de conversation permanente met en cache ces messages en mémoire. Ainsi, si vous augmentez ce nombre, davantage de messages seront mis en cache. Vous pouvez toujours accéder au contenu historique par recherche. Le numéro par défaut détermine simplement le nombre maximal de messages que vous voyez initialement lors de la connexion à une salle de conversation. 
  
   - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale pour un fichier qui peut être téléchargée vers une salle de conversation dans le système (pour lequel les téléchargements de fichiers sont activés par le biais du paramètre **Catégorie** correspondant).
    
   - Dans **Limite de mise à jour du participant :**, sélectionnez la limite pour les mises à jour de participants. Le serveur de conversation permanente envoie des informations de liste (qui est connecté à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés atteigne ce nombre. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà duquel le serveur de conversation permanente cesse d’envoyer des mises à jour de liste aux clients connectés sur les personnes présentes dans la salle.
    
   - Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vide.
    
     Si vous souhaitez personnaliser votre expérience de création de salle et inclure votre flux de travail d’entreprise spécifique, vous pouvez créer une solution de gestion de salle personnalisée à l’aide du Kit de développement logiciel (SDK) du serveur de conversation permanente, l’héberger quelque part et placer l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    

