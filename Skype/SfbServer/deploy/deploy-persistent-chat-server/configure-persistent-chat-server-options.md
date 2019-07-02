---
title: Configuration des options de serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Résumé: Découvrez comment configurer les options de serveur de chat permanent sur le niveau global, de site ou de pool dans Skype entreprise Server 2015.'
ms.openlocfilehash: 3140689190900bee1633210a455c7af475bb8fa0
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418127"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configuration des options de serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé:** Apprenez à configurer les options de serveur de chat permanent sur le niveau global, de site ou de regroupement dans Skype entreprise Server 2015.
  
Vous pouvez spécifier plusieurs options pour le serveur de chat permanent qui peuvent être appliquées globalement, à tous les pools au sein d’un site ou à un pool spécifique au sein d’un site. Les options de serveur de conversation permanente comprennent : 
  
- Historique de conversation par défaut. Nombre de messages de conversation disponible pour chaque salle lors de la première demande. La valeur globale par défaut est de 30 messages de conversation. 
    
- Taille de fichier maximale. Taille maximale d’un fichier que vous pouvez charger sur ou télécharger d’une pièce. La valeur globale par défaut est de 20 Mo.
    
- Limite de mise à jour du participant. Nombre maximal de participants dans une salle de conversation données qui recevront des mises à jour de réunion via la conversation permanente. La valeur globale par défaut est de 75.
    
- URL de gestion de la salle. URL utilisée pour personnaliser la gestion des salles de conversation. Ce paramètre permet d’utiliser une solution personnalisée de gestion des salles. 
   
> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurer les options globales de chat permanent du serveur de conversation

Pour configurer les options globales de chat permanent du serveur, procédez comme suit:
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurer les options pour un pool de serveurs de chat permanent spécifique

Pour configurer les options pour un pool de serveurs de chat permanent spécifique.
  
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
    
   - Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de la salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vide.
    
     Si vous souhaitez personnaliser l’interface de création de votre salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion des salles personnalisée à l’aide du kit de développement logiciel (SDK) serveur Chat permanent, l’héberger et placer l’URL ici. Cette URL est envoyée au client de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    

