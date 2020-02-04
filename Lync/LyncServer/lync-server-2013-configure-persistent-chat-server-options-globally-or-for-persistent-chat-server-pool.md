---
title: 'Lync Server 2013 : Configuration des options de serveur de conversation permanente au niveau global ou pour un pool de serveurs de conversation permanente'
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
ms.openlocfilehash: 86ee77dd34e3a43ea62ac6cffaf4af952b1c447e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="5ce27-102">Configuration des options de serveur de conversation permanente au niveau global ou pour un pool de serveurs de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ce27-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ce27-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5ce27-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5ce27-104">Dans Lync Server 2013 panneau de configuration, vous pouvez utiliser la section **configuration permanente** de conversation de la page de **conversation permanente** pour configurer les paramètres de conversation permanente dans le monde entier, à l’endroit où ils s’appliquent à tous les pools de serveurs de chat permanent ou à un pool de serveurs de chat permanent spécifique.</span><span class="sxs-lookup"><span data-stu-id="5ce27-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ce27-105">Pour configurer et utiliser le serveur de chat permanent, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de chat permanent à la topologie, puis publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="5ce27-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="5ce27-106">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajouter un serveur Chat permanent à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5ce27-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="5ce27-107">Pour configurer globalement les options de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="5ce27-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="5ce27-108">À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5ce27-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ce27-109">Dans le menu **Démarrer** , sélectionnez le panneau de configuration de Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="5ce27-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="5ce27-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5ce27-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5ce27-111">Vous pouvez également utiliser des cmdlets Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ce27-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5ce27-112">Pour plus d’informations, reportez-vous à <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuration du serveur de chat permanent à l’aide des cmdlets Windows PowerShell</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5ce27-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="5ce27-113">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="5ce27-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="5ce27-114">Dans la page **configuration de conversation permanente** , cliquez sur **nouveau,** puis cliquez sur **configuration de site**.</span><span class="sxs-lookup"><span data-stu-id="5ce27-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5ce27-115">Choisissez cette option si vous souhaitez que la configuration soit appliquée à tous les pools de serveurs de chat permanent déployés dans le site.</span><span class="sxs-lookup"><span data-stu-id="5ce27-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="5ce27-116">Cliquez sur <STRONG>configuration de réserve</STRONG> si vous voulez que la configuration soit appliquée à un pool de serveurs de chat permanent spécifique.</span><span class="sxs-lookup"><span data-stu-id="5ce27-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="5ce27-117">Dans **Sélectionner un site**, sélectionnez le site que vous voulez configurer pour la configuration du site serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="5ce27-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="5ce27-118">Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5ce27-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="5ce27-p105">Dans le champ **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site existe déjà.</span><span class="sxs-lookup"><span data-stu-id="5ce27-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="5ce27-p106">Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation traités pour chaque salle lors de la première demande. Par défaut, 30 messages seront traités. Il s’agit de la valeur par défaut globale : les administrateurs peuvent désactiver l’historique de conversation par catégorie.</span><span class="sxs-lookup"><span data-stu-id="5ce27-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="5ce27-124">Le serveur de conversation permanent va mettre en cache ces messages de façon à ce que, si vous augmentez ce nombre, les messages seront mis en cache.</span><span class="sxs-lookup"><span data-stu-id="5ce27-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="5ce27-125">Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche.</span><span class="sxs-lookup"><span data-stu-id="5ce27-125">You can always access historical content by search.</span></span> <span data-ttu-id="5ce27-126">Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="5ce27-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="5ce27-p108">Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale de fichier qui peut être téléchargée dans une salle de conversation sur le système (pour lequel les téléchargements de fichiers sont activés à l’aide du paramètre **Catégorie** correspondant).</span><span class="sxs-lookup"><span data-stu-id="5ce27-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="5ce27-130">Ce paramètre est appliqué sur le serveur, car des applications personnalisées ou des clients de discussion de groupe antérieurs à&nbsp;l’aide d’Office Communications Server 2007 R2 Server Chat Server ou de Lync Server 2010, une discussion de groupe peut publier des fichiers dans une salle.</span><span class="sxs-lookup"><span data-stu-id="5ce27-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="5ce27-131">Le client Lync 2013 ne disposant pas de la fonctionnalité de chargement et de téléchargement de fichiers, donc si vous avez un simple déploiement Lync 2013 ou un client Lync 2013, il est impossible de publier des fichiers dans une salle de conversation serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="5ce27-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="5ce27-132">Dans **Limite de mise à jour du participant**, sélectionnez la limite pour les mises à jour de participants.</span><span class="sxs-lookup"><span data-stu-id="5ce27-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="5ce27-133">Le serveur Chat permanent envoie les informations de la liste (qui est connectée à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés ait atteint ce numéro.</span><span class="sxs-lookup"><span data-stu-id="5ce27-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="5ce27-134">Par défaut, cette limite est de 75.</span><span class="sxs-lookup"><span data-stu-id="5ce27-134">By default, the number is 75.</span></span> <span data-ttu-id="5ce27-135">Cette limite indique le nombre maximal de participants dans une salle donnée au-delà du serveur de chat permanent qui cesse d’envoyer les mises à jour de la liste aux clients connectés sur les utilisateurs présents dans la salle.</span><span class="sxs-lookup"><span data-stu-id="5ce27-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="5ce27-p111">(Facultatif) Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’une gestion de salle personnalisée basée sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, ne renseignez pas cette option. Une fois l’URL définie, elle est appliquée comme URL de gestion de salle interne et externe.</span><span class="sxs-lookup"><span data-stu-id="5ce27-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="5ce27-140">Si vous souhaitez personnaliser l’interface de création de votre salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion des salles personnalisée à l’aide du kit de développement logiciel (SDK) serveur Chat permanent, l’héberger et placer l’URL ici.</span><span class="sxs-lookup"><span data-stu-id="5ce27-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="5ce27-141">Cette URL est envoyée au client, de sorte que lorsqu’un utilisateur essaie d’afficher ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5ce27-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="5ce27-142">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5ce27-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="5ce27-143">Pour configurer les options de conversation permanente pour un pool de serveurs de chat permanent spécifique</span><span class="sxs-lookup"><span data-stu-id="5ce27-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="5ce27-144">À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5ce27-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ce27-145">Dans le menu **Démarrer** , sélectionnez le panneau de configuration de Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="5ce27-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="5ce27-146">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5ce27-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5ce27-147">Vous pouvez également utiliser des cmdlets Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ce27-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5ce27-148">Pour plus d’informations, reportez-vous à <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuration du serveur de chat permanent à l’aide des cmdlets Windows PowerShell</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5ce27-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="5ce27-149">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Configuration de la conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="5ce27-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="5ce27-150">Dans la page **Configuration de la conversation permanente**, cliquez sur **Créer**, puis sur **Configuration du pool**.</span><span class="sxs-lookup"><span data-stu-id="5ce27-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="5ce27-151">Dans **Sélectionner un service**, sélectionnez le service associé au pool de serveurs de chat permanent à configurer.</span><span class="sxs-lookup"><span data-stu-id="5ce27-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="5ce27-152">Dans **Nouvelle configuration de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="5ce27-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="5ce27-p115">Dans **Nom**, spécifiez un nom pour les nouveaux paramètres de configuration. Par défaut, le nom du site du pool existe déjà.</span><span class="sxs-lookup"><span data-stu-id="5ce27-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="5ce27-p116">Dans **Historique de conversation par défaut**, définissez le nombre de messages de conversation traités pour chaque salle lors de la première demande. Par défaut, 30 messages seront traités. Il s’agit de la valeur par défaut globale : les administrateurs peuvent désactiver l’historique de conversation par catégorie.</span><span class="sxs-lookup"><span data-stu-id="5ce27-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="5ce27-158">Le serveur de conversation permanent va mettre en cache ces messages de façon à ce que, si vous augmentez ce nombre, les messages seront mis en cache.</span><span class="sxs-lookup"><span data-stu-id="5ce27-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="5ce27-159">Vous pouvez toujours accéder au contenu de l’historique à l’aide de la recherche.</span><span class="sxs-lookup"><span data-stu-id="5ce27-159">You can always access historical content by search.</span></span> <span data-ttu-id="5ce27-160">Le nombre par défaut détermine simplement la quantité maximale de messages visibles initialement lors de la connexion à une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="5ce27-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="5ce27-p118">Dans **Taille de fichier maximale (Ko)**, sélectionnez la taille de fichier maximale de chaque historique de conversation. Par défaut, la taille maximale est de 20 Mo (20 000 Ko). Il s’agit de la taille maximale de fichier qui peut être téléchargée dans une salle de conversation sur le système (pour lequel les téléchargements de fichiers sont activés à l’aide du paramètre **Catégorie** correspondant).</span><span class="sxs-lookup"><span data-stu-id="5ce27-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="5ce27-164">Ce paramètre est appliqué sur le serveur, car des applications personnalisées ou des clients de discussion de groupe antérieurs (&nbsp;Office Communications Server 2007 R2 Server Chat Server ou Lync Server 2010, discussion de groupe) peuvent publier des fichiers dans une salle.</span><span class="sxs-lookup"><span data-stu-id="5ce27-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="5ce27-165">Le client Lync 2013 ne disposant pas de la fonctionnalité de chargement et de téléchargement de fichiers, donc si vous avez un simple déploiement Lync 2013 ou un client Lync 2013, il est impossible de publier des fichiers dans une salle de conversation serveur Chat permanent.</span><span class="sxs-lookup"><span data-stu-id="5ce27-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="5ce27-166">Dans **Limite de mise à jour du participant**, sélectionnez la limite pour les mises à jour de participants.</span><span class="sxs-lookup"><span data-stu-id="5ce27-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="5ce27-167">Le serveur Chat permanent envoie les informations de la liste (qui est connectée à une salle de conversation) à tous les participants jusqu’à ce que le nombre d’utilisateurs connectés ait atteint ce numéro.</span><span class="sxs-lookup"><span data-stu-id="5ce27-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="5ce27-168">Par défaut, cette limite est de 75.</span><span class="sxs-lookup"><span data-stu-id="5ce27-168">By default, the number is 75.</span></span> <span data-ttu-id="5ce27-169">Cette limite indique le nombre maximal de participants dans une salle donnée au-delà du serveur de chat permanent qui cesse d’envoyer les mises à jour de la liste aux clients connectés sur les utilisateurs présents dans la salle.</span><span class="sxs-lookup"><span data-stu-id="5ce27-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="5ce27-p121">Dans **URL de gestion de salle**, sélectionnez l’URL de gestion de salle. Il s’agit de l’URL d’un déploiement de salle personnalisé basé sur le web. Si vous n’avez pas besoin de personnaliser la gestion de salle et que vous utilisez simplement le paramètre par défaut, ne renseignez pas cette option.</span><span class="sxs-lookup"><span data-stu-id="5ce27-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="5ce27-173">Si vous souhaitez personnaliser l’interface de création de votre salle et inclure votre flux de travail professionnel spécifique, vous pouvez créer une solution de gestion des salles personnalisée à l’aide du kit de développement logiciel (SDK) serveur Chat permanent, l’héberger et placer l’URL ici.</span><span class="sxs-lookup"><span data-stu-id="5ce27-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="5ce27-174">Cette URL est envoyée au client de sorte que lorsqu’un utilisateur essaie de visualiser ou de créer une salle, il est dirigé vers votre solution de gestion de salle personnalisée.</span><span class="sxs-lookup"><span data-stu-id="5ce27-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="5ce27-175">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5ce27-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

