---
title: 'Lync Server 2013 : configuration des options de serveur de conversation permanente globalement ou pour le pool de serveurs de conversation permanente'
description: 'Lync Server 2013 : configurez les options de serveur de conversation permanente globalement ou pour le pool de serveurs de conversation permanente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0e26fc8719f9aa5f153a7962df70ee7237b980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564990"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>Configuration des options de serveur de conversation permanente globalement ou pour le pool de serveurs de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la section Configuration de la **conversation permanente** de la page **conversation permanente** pour configurer les paramètres de conversation permanente de manière globale lorsqu’elle s’applique à tous les pools de serveurs de conversation permanente, ou pour un pool de serveurs de conversation permanente spécifique.

<div>


> [!NOTE]  
> Pour configurer et utiliser le serveur de conversation permanente, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>Pour configurer les options de conversation permanente globalement

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent Chat Server by Using Windows PowerShell Cmdlets</A> dans la documentation de déploiement.

    
    </div>

3.  Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.

4.  Dans la page Configuration de la **conversation permanente** , cliquez sur **nouveau,** puis sur **configuration du site**.
    
    <div>
    

    > [!IMPORTANT]  
    > Choisissez cette option si vous souhaitez que la configuration soit appliquée à tous les pools de serveurs de conversation permanente déployés sur le site. Cliquez sur <STRONG>configuration du pool</STRONG> si vous souhaitez que la configuration soit appliquée à un pool de serveurs de conversation permanente spécifique.

    
    </div>

5.  Dans **Sélectionner un site**, sélectionnez le site à configurer pour la configuration du site de serveur de conversation permanente.

6.  Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site existe déjà
    
      - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation qui seront traités pour chaque salle lors de la première demande. Par défaut, 30 messages sont traités. Il s’agit du paramètre global par défaut : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
        
        <div>
        

        > [!IMPORTANT]  
        > Le serveur de conversation permanente mettra en cache ces messages en mémoire, de sorte que si vous augmentez ce nombre, d’autres messages seront mis en cache. Vous pouvez toujours accéder au contenu historique par recherche. Le nombre par défaut détermine simplement le nombre maximal de messages que vous avez initialement affiché lors de la connexion à une salle de conversation.

        
        </div>
    
      - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale pour un fichier qui peut être téléchargée vers une salle de conversation dans le système (pour lequel les téléchargements de fichiers sont activés par le biais du paramètre **Catégorie** correspondant).
        
        <div>
        

        > [!IMPORTANT]  
        > Ce paramètre est appliqué sur le serveur car les applications personnalisées ou les clients de conversation de groupe précédents utilisant le serveur de conversation de groupe Office Communications Server 2007 R2 &nbsp; ou Lync server 2010, Group chat peuvent publier des fichiers dans une salle. Le client Lync 2013 ne dispose pas de la fonctionnalité de chargement/téléchargement de fichiers, de sorte que si vous avez un déploiement Lync 2013 pur ou un client Lync 2013, il n’est pas possible de publier des fichiers dans une salle de conversation de serveur de conversation permanente.

        
        </div>
    
      - Dans **Limite de mise à jour du participant :**, sélectionnez la limite pour les mises à jour de participants. Le serveur de conversation permanente envoie des informations sur la liste (qui est connectée à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés atteigne ce numéro. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà duquel le serveur de conversation permanente cesse d’envoyer des mises à jour de la liste aux clients connectés sur les personnes présentes dans la salle.
    
      - (Facultatif.) Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’une gestion de salle personnalisée basée sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vierge. Une fois l’URL définie, elle est appliquée comme URL de gestion de salle interne et externe.
        
        Si vous souhaitez personnaliser l’expérience de création de votre salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion des salles personnalisée à l’aide du kit de développement logiciel (SDK) de serveur de conversation permanente, l’héberger quelque part et placer l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.

7.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Pour configurer les options de conversation permanente pour un pool de serveurs de conversation permanente spécifique

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent Chat Server by Using Windows PowerShell Cmdlets</A> dans la documentation de déploiement.

    
    </div>

3.  Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.

4.  Dans la page **Configuration de la conversation permanente**, cliquez sur **Nouveau**, puis sur **Configuration du pool**.

5.  Dans **Sélectionner un service**, sélectionnez le service associé au pool de serveurs de conversation permanente à configurer.

6.  Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site du pool existe déjà
    
      - Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation qui seront traités pour chaque salle lors de la première demande. Par défaut, 30 messages sont traités. Il s’agit du paramètre global par défaut : les administrateurs peuvent désactiver l’historique de conversation par catégorie.
        
        <div>
        

        > [!IMPORTANT]  
        > Le serveur de conversation permanente mettra en cache ces messages en mémoire, de sorte que si vous augmentez ce nombre, d’autres messages seront mis en cache. Vous pouvez toujours accéder au contenu historique par recherche. Le nombre par défaut détermine simplement le nombre maximal de messages que vous avez initialement affiché lors de la connexion à une salle de conversation.

        
        </div>
    
      - Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale pour un fichier qui peut être téléchargée vers une salle de conversation dans le système (pour lequel les téléchargements de fichiers sont activés par le biais du paramètre **Catégorie** correspondant).
        
        <div>
        

        > [!IMPORTANT]  
        > Ce paramètre est appliqué sur le serveur car les applications personnalisées ou les clients de conversation de groupe précédents (serveur de conversation de groupe Office Communications Server 2007 R2 &nbsp; ou Lync server 2010, conversation de groupe) peuvent publier des fichiers dans une salle. Le client Lync 2013 ne dispose pas de la fonctionnalité de chargement/téléchargement de fichiers, de sorte que si vous avez un déploiement Lync 2013 pur ou un client Lync 2013, il n’est pas possible de publier des fichiers dans une salle de conversation de serveur de conversation permanente.

        
        </div>
    
      - Dans **Limite de mise à jour du participant :**, sélectionnez la limite pour les mises à jour de participants. Le serveur de conversation permanente envoie des informations sur la liste (qui est connectée à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés atteigne ce numéro. Par défaut, cette limite est de 75. Cette limite indique le nombre maximal de participants dans une salle donnée au-delà duquel le serveur de conversation permanente cesse d’envoyer des mises à jour de la liste aux clients connectés sur les personnes présentes dans la salle.
    
      - Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, laissez cette option vierge.
        
        Si vous souhaitez personnaliser l’expérience de création de votre salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion des salles personnalisée à l’aide du kit de développement logiciel (SDK) de serveur de conversation permanente, l’héberger quelque part et placer l’URL ici. Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.

7.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

