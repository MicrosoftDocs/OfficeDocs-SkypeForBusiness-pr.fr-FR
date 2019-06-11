---
title: 'Lync Server 2013 : Publication de la topologie mise à jour'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f3be1443f98444712a66942417e1812181efe7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="75f96-102">Publication de la topologie mise à jour dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75f96-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75f96-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="75f96-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="75f96-104">Après avoir effectué la mise à jour de votre topologie dans le générateur de topologie, vous devez publier la topologie dans le centre de gestion central avant de pouvoir configurer et utiliser le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="75f96-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="75f96-105">Les copies en lecture seule des données sont répliquées sur tous les serveurs de la topologie afin de maintenir la synchronisation de tous les serveurs avec la topologie et d’autres modifications intervenues dans la configuration.</span><span class="sxs-lookup"><span data-stu-id="75f96-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="75f96-106">Pour publier une topologie mise à jour</span><span class="sxs-lookup"><span data-stu-id="75f96-106">To publish an updated topology</span></span>

<span data-ttu-id="75f96-107">Avant de publier votre topologie, installez les bases de données pour le serveur de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="75f96-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="75f96-108">Utilisez le générateur de topologie pour installer des bases de données en sélectionnant **action** et **installer la base de données**.</span><span class="sxs-lookup"><span data-stu-id="75f96-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="75f96-109">Sur un ordinateur exécutant Lync Server 2013 ou sur lequel sont installés les outils d’administration de Lync Server, connectez-vous à l’aide d’un compte membre du groupe **administrateurs de domaine** et du groupe **RTCUniversalServerAdmins** et disposant du contrôle total. les autorisations (en lecture, en écriture et en modification) sur le magasin de fichiers à utiliser pour le stockage des fichiers du serveur de chat permanent (de sorte que le générateur de topologie puisse configurer les listes de contrôle d’accès discrétionnaire requises), ou un compte avec des droits d’utilisateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="75f96-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="75f96-110">Démarrer le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="75f96-110">Start Topology Builder.</span></span> <span data-ttu-id="75f96-111">Sélectionnez l’option **Télécharger la topologie à partir du déploiement existant**ou **Ouvrez la topologie à partir d’un fichier local** si vous l’avez enregistrée localement.</span><span class="sxs-lookup"><span data-stu-id="75f96-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="75f96-112">Dans l’arborescence de la console, cliquez avec le bouton droit sur **Lync Server 2013**, puis cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="75f96-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="75f96-113">Dans la page **Publier la topologie**, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="75f96-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="75f96-114">Dans la page **Assistant Publication terminé**, assurez-vous que la topologie a été publiée correctement, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="75f96-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="75f96-115">Après la publication de la topologie, vous devez configurer la prise en charge du serveur de chat permanent pour pouvoir archiver le contenu.</span><span class="sxs-lookup"><span data-stu-id="75f96-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

