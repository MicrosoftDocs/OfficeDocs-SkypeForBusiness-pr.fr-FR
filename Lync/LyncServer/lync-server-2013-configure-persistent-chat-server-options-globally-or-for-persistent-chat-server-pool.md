---
title: 'Lync Server 2013 : Configuration des options de serveur de conversation permanente au niveau global ou pour un pool de serveurs de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fedd0d1adb4149c3dc2ea41c5321259f571524f
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>Configuration des options de serveur de conversation permanente au niveau global ou pour un pool de serveurs de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Dans Lync Server 2013 panneau de configuration, vous pouvez utiliser la section **configuration permanente** de conversation de la page de **conversation permanente** pour configurer les paramètres de conversation permanente dans le monde entier, à l’endroit où ils s’appliquent à tous les pools de serveurs de chat permanent ou à un pool de serveurs de chat permanent spécifique.

<div>


> [!NOTE]  
> Pour configurer et utiliser le serveur de chat permanent, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de chat permanent à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajouter un serveur Chat permanent à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>Pour configurer globalement les options de conversation permanente

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration de Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des cmdlets Windows PowerShell. Pour plus d’informations, reportez-vous à <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuration du serveur de chat permanent à l’aide des cmdlets Windows PowerShell</A> dans la documentation de déploiement.

    
    </div>

3.  Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.

4.  Dans la page **configuration de conversation permanente** , cliquez sur **nouveau,** puis cliquez sur **configuration de site**.
    
    <div>
    

    > [!IMPORTANT]  
    > Choisissez cette option si vous souhaitez que la configuration soit appliquée à tous les pools de serveurs de chat permanent déployés dans le site. Cliquez sur <STRONG>configuration de réserve</STRONG> si vous voulez que la configuration soit appliquée à un pool de serveurs de chat permanent spécifique.

    
    </div>

5.  Dans **Sélectionner un site**, sélectionnez le site que vous voulez configurer pour la configuration du site serveur Chat permanent.

6.  Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
      - Dans le champ **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site existe déjà.
    
      - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation traités pour chaque salle lors de la première demande. Par défaut, 30 messages seront traités. Il s’agit de la valeur par défaut globale : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
        
        <div>
        

        > [!IMPORTANT]  
        > Le serveur de conversation permanent va mettre en cache ces messages de façon à ce que, si vous augmentez ce nombre, les messages seront mis en cache. Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche. Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation.

        
        </div>
    
      - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale de fichier qui peut être téléchargée dans une salle de conversation sur le système (pour lequel les téléchargements de fichiers sont activés à l’aide du paramètre **Catégorie** correspondant).
        
        <div>
        

        > [!IMPORTANT]  
        > Ce paramètre est appliqué sur le serveur, car des applications personnalisées ou des clients de discussion de groupe antérieurs à&nbsp;l’aide d’Office Communications Server 2007 R2 Server Chat Server ou de Lync Server 2010, une discussion de groupe peut publier des fichiers dans une salle. Le client Lync 2013 ne disposant pas de la fonctionnalité de chargement et de téléchargement de fichiers, donc si vous avez un simple déploiement Lync 2013 ou un client Lync 2013, il est impossible de publier des fichiers dans une salle de conversation serveur Chat permanent.

        
        </div>
    
      - Dans **Limite de mise à jour du participant**, sélectionnez la limite pour les mises à jour de participants. Le serveur Chat permanent envoie les informations de la liste (qui est connectée à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés ait atteint ce numéro. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà du serveur de chat permanent qui cesse d’envoyer les mises à jour de la liste aux clients connectés sur les utilisateurs présents dans la salle.
    
      - (Facultatif) Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’une gestion de salle personnalisée basée sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, ne renseignez pas cette option. Une fois l’URL définie, elle est appliquée comme URL de gestion de salle interne et externe.
        
        Si vous souhaitez personnaliser l’interface de création de votre salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion des salles personnalisée à l’aide du kit de développement logiciel (SDK) serveur Chat permanent, l’héberger et placer l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie d’afficher ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Pour configurer les options de conversation permanente pour un pool de serveurs de chat permanent spécifique

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration de Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des cmdlets Windows PowerShell. Pour plus d’informations, reportez-vous à <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuration du serveur de chat permanent à l’aide des cmdlets Windows PowerShell</A> dans la documentation de déploiement.

    
    </div>

3.  Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.

4.  Dans la page **Configuration de la conversation permanente**, cliquez sur **Créer**, puis sur **Configuration du pool**.

5.  Dans **Sélectionner un service**, sélectionnez le service associé au pool de serveurs de chat permanent à configurer.

6.  Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site du pool existe déjà.
    
      - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation traités pour chaque salle lors de la première demande. Par défaut, 30 messages seront traités. Il s’agit de la valeur par défaut globale : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
        
        <div>
        

        > [!IMPORTANT]  
        > Le serveur de conversation permanent va mettre en cache ces messages de façon à ce que, si vous augmentez ce nombre, les messages seront mis en cache. Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche. Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation.

        
        </div>
    
      - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale de fichier qui peut être téléchargée dans une salle de conversation sur le système (pour lequel les téléchargements de fichiers sont activés à l’aide du paramètre **Catégorie** correspondant).
        
        <div>
        

        > [!IMPORTANT]  
        > Ce paramètre est appliqué sur le serveur, car des applications personnalisées ou des clients de discussion de groupe antérieurs (&nbsp;Office Communications Server 2007 R2 Server Chat Server ou Lync Server 2010, discussion de groupe) peuvent publier des fichiers dans une salle. Le client Lync 2013 ne disposant pas de la fonctionnalité de chargement et de téléchargement de fichiers, donc si vous avez un simple déploiement Lync 2013 ou un client Lync 2013, il est impossible de publier des fichiers dans une salle de conversation serveur Chat permanent.

        
        </div>
    
      - Dans **Limite de mise à jour du participant**, sélectionnez la limite pour les mises à jour de participants. Le serveur Chat permanent envoie les informations de la liste (qui est connectée à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés ait atteint ce numéro. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà du serveur de chat permanent qui cesse d’envoyer les mises à jour de la liste aux clients connectés sur les utilisateurs présents dans la salle.
    
      - Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, ne renseignez pas cette option.
        
        Si vous souhaitez personnaliser l’interface de création de votre salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion des salles personnalisée à l’aide du kit de développement logiciel (SDK) serveur Chat permanent, l’héberger et placer l’URL ici. Cette URL est envoyée au client de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.

7.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

