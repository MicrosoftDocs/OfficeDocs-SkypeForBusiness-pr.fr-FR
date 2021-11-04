---
title: Configuration d’une conversation permanente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: Votre déploiement de serveur de conversation permanente peut héberger plusieurs salles de conversation permanente simultanées. Les salles de conversation peuvent être organisées en un ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une catégorie et hérite de certains paramètres de cette catégorie. Cette organisation crée une structure utile pour l’identification des conversations en fonction de leur objectif professionnel et simplifie la délégation de l’administration ainsi que la gestion.
ms.openlocfilehash: e3b425e56b8d32c7066294c3794cad9979d832ff
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748200"
---
# <a name="persistent-chat-configuration"></a>Configuration d’une conversation permanente
 
Votre déploiement de serveur de conversation permanente peut héberger plusieurs salles de conversation permanente simultanées. Les salles de conversation peuvent être organisées en un ensemble de catégories sur le serveur. Chaque salle de conversation appartient à une catégorie et hérite de certains paramètres de cette catégorie. Cette organisation crée une structure utile pour l’identification des conversations en fonction de leur objectif professionnel et simplifie la délégation de l’administration ainsi que la gestion.
  
> [!NOTE]
> Bien que de nombreuses fonctionnalités de gestion des salles de conversation soient disponibles sur les ordinateurs exécutant la conversation permanente pour l’utilisateur, les administrateurs de conversation permanente (dans le rôle **cspersistentchatadministrator)** doivent utiliser le panneau de contrôle ou les applets de commande de l’environnement de ligne de commande Management Shell pour créer ou gérer des catégories.
  
Les administrateurs de conversation permanente utilisent le Panneau de Skype Entreprise Server ou des cmdlets Windows PowerShell pour créer et gérer des catégories et pour concevoir l’accès aux salles de conversation pour les utilisateurs de leur organisation.
  
Les responsables de salles de conversation permanente, qui ont la possibilité de gérer une ou plusieurs salles de conversation, peuvent utiliser le client pour lancer une application Web de gestion de salle pour créer et gérer des salles (ou les clients peuvent créer des solutions et des flux de travail personnalisés à appeler). Conversation permanente
  
Les administrateurs de conversation permanente peuvent également utiliser le panneau de Windows PowerShell des cmdlets pour créer et gérer des salles.
  
Les responsables de salles de conversation peuvent apporter des modifications à toutes les propriétés des salles de conversation, à l’exception de la catégorie de la salle. Il n’est pas possible de les empêcher d’effectuer les actions suivantes :
  
- Désactivation d’une salle de conversation
    
- Modification du nom d’une salle de conversation
    
- Modification de la description d’une salle de conversation
    
- Modification du type d’une salle de conversation (Auditorium ou Normal)
    
- modification de la confidentialité d’une salle (ouverte/fermée/secrète) ;
    
- Ajout ou suppression de membres
    
- Ajout ou suppression de gestionnaires de salle de conversation
    
- Ajout ou suppression d’un complément
    
- Modification des paramètres tels que les invitations (en fonction de ce qui est autorisé par la catégorie)
    
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Configuration** de la conversation permanente : configurer les options du serveur de conversation permanente globalement ou pour un pool spécifique.
  
## <a name="to-configure-persistent-chat-options-globally"></a>Pour configurer les options de conversation permanente globalement

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.
    
4. Dans la page **Configuration de la conversation permanente,** cliquez sur **Nouveau,** puis sur **Configuration du site.**
    
    > [!IMPORTANT]
    > Choisissez cette option si vous souhaitez que la configuration soit appliquée à tous les pools de serveurs de conversation permanente déployés sur le site. Cliquez **sur Configuration du pool** si vous souhaitez que la configuration soit appliquée à un pool de serveurs de conversation permanente spécifique.
  
5. Dans **Sélectionner un site,** sélectionnez le site à configurer pour la configuration du site serveur de conversation permanente.
    
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
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Pour configurer les options de conversation permanente pour un pool de serveurs de conversation permanente spécifique

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server, ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.
    
4. Dans la page **Configuration de la conversation permanente**, cliquez sur **Nouveau**, puis sur **Configuration du pool**.
    
5. Dans **Sélectionner un service,** sélectionnez le service associé au pool de serveurs de conversation permanente à configurer.
    
6. Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site du pool existe déjà
    
   - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation qui seront traités pour chaque salle lors de la première demande. Par défaut, 30 messages sont traités. Il s’agit du paramètre global par défaut : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
    
     > [!IMPORTANT]
     > Le serveur de conversation permanente met en cache ces messages en mémoire. Ainsi, si vous augmentez ce nombre, davantage de messages seront mis en cache. Vous pouvez toujours accéder au contenu historique par recherche. Le numéro par défaut détermine simplement le nombre maximal de messages que vous voyez initialement lors de la connexion à une salle de conversation. 
  
   - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale pour un fichier qui peut être téléchargée vers une salle de conversation dans le système (pour lequel les téléchargements de fichiers sont activés par le biais du paramètre **Catégorie** correspondant).
    
   - Dans **Limite de mise à jour du participant :**, sélectionnez la limite pour les mises à jour de participants. Le serveur de conversation permanente envoie des informations de liste (qui est connecté à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés atteigne ce nombre. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà duquel le serveur de conversation permanente cesse d’envoyer des mises à jour de liste aux clients connectés sur les personnes présentes dans la salle.
    
   - (Facultatif) Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vide.
    
     Si vous souhaitez personnaliser votre expérience de création de salle et inclure votre flux de travail d’entreprise spécifique, vous pouvez créer une solution de gestion de salle personnalisée à l’aide du Kit de développement logiciel (SDK) du serveur de conversation permanente, l’héberger quelque part et placer l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.
    
7. Cliquez sur **Valider**.
    
## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de conversation permanente, voir [Plan for Persistent Chat Server in Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), Deploy Persistent Chat Server in Skype Entreprise Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [Manage Persistent Chat Server in Skype Entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

