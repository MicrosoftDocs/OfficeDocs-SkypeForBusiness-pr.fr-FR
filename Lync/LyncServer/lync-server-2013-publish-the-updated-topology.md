---
title: 'Lync Server 2013 : publication de la topologie mise à jour'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b978d7a8d2cf05d4e9fa1b0a224bbef50e3fd7e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="3e597-102">Publier la topologie mise à jour dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e597-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e597-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3e597-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3e597-104">Après avoir mis à jour votre topologie dans le générateur de topologie, vous devez publier la topologie dans le magasin central de gestion avant de pouvoir configurer et utiliser le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="3e597-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="3e597-105">Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.</span><span class="sxs-lookup"><span data-stu-id="3e597-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="3e597-106">Pour publier une topologie mise à jour</span><span class="sxs-lookup"><span data-stu-id="3e597-106">To publish an updated topology</span></span>

<span data-ttu-id="3e597-107">Avant de publier votre topologie, installez les bases de données pour le serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="3e597-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="3e597-108">Utilisez le générateur de topologie pour installer des bases de données en sélectionnant **action** et **installer la base de données**.</span><span class="sxs-lookup"><span data-stu-id="3e597-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="3e597-109">Sur un ordinateur exécutant Lync Server 2013 ou sur lequel les outils d’administration Lync Server sont installés, ouvrez une session à l’aide d’un compte membre du groupe **administrateurs du domaine** et du groupe **RTCUniversalServerAdmins** et qui dispose des autorisations contrôle total (en lecture, écriture et modification) sur le magasin de fichiers à utiliser pour le magasin de fichiers du serveur de conversation permanente (afin que le générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaire (DACL) requises) ou un compte avec des droits d’utilisateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="3e597-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="3e597-110">Démarrez le Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="3e597-110">Start Topology Builder.</span></span> <span data-ttu-id="3e597-111">Sélectionnez **Télécharger la topologie à partir du déploiement existant** ou **Ouvrir une topologie depuis un fichier local** si vous l’avez enregistrée localement.</span><span class="sxs-lookup"><span data-stu-id="3e597-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="3e597-112">Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="3e597-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="3e597-113">Dans la page **Publier la topologie**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3e597-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="3e597-114">Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="3e597-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3e597-115">Après avoir publié la topologie, vous devez configurer la prise en charge du serveur de conversation permanente pour pouvoir archiver le contenu.</span><span class="sxs-lookup"><span data-stu-id="3e597-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

