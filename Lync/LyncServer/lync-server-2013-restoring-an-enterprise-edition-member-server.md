---
title: 'Lync Server 2013: restauration d’un serveur membre Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83f0283dc6525dbb75ce74809bd88f4e962a9aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="af7b1-102">Restauration d’un serveur membre Enterprise Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af7b1-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af7b1-103">_**Dernière modification de la rubrique:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="af7b1-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="af7b1-104">Si un serveur exécutant l’un des rôles serveur suivants ne fonctionne pas, suivez la procédure décrite dans cette rubrique pour restaurer le serveur.</span><span class="sxs-lookup"><span data-stu-id="af7b1-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="af7b1-105">Si plusieurs serveurs échouent indépendamment, suivez la procédure pour chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="af7b1-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="af7b1-106">serveur frontal</span><span class="sxs-lookup"><span data-stu-id="af7b1-106">Front End Server</span></span>

  - <span data-ttu-id="af7b1-107">serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="af7b1-107">Mediation Server</span></span>

  - <span data-ttu-id="af7b1-108">directeur</span><span class="sxs-lookup"><span data-stu-id="af7b1-108">Director</span></span>

  - <span data-ttu-id="af7b1-109">serveur de conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="af7b1-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="af7b1-110">serveur Edge</span><span class="sxs-lookup"><span data-stu-id="af7b1-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="af7b1-111">Nous vous recommandons de prendre une copie d’image du système avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="af7b1-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="af7b1-112">Vous pouvez utiliser cette image comme point de restauration en cas de problème de restauration.</span><span class="sxs-lookup"><span data-stu-id="af7b1-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="af7b1-113">Vous souhaiterez peut-être prendre la copie d’image après l’installation du système d’exploitation et de SQL Server, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="af7b1-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="af7b1-114">Pour restaurer un serveur membre</span><span class="sxs-lookup"><span data-stu-id="af7b1-114">To restore a member server</span></span>

1.  <span data-ttu-id="af7b1-115">Commencez par un serveur propre ou nouveau qui porte le même nom de domaine complet (FQDN) que le serveur en panne, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="af7b1-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af7b1-116">Pour effectuer cette étape, suivez les procédures de déploiement du serveur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="af7b1-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="af7b1-117">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="af7b1-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="af7b1-118">Recherchez le dossier d’installation ou le média de Lync Server et démarrez l’Assistant Déploiement de Lync Server \\situé\\à\\l’installation de Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="af7b1-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="af7b1-119">Suivez l’Assistant déploiement pour effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="af7b1-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="af7b1-120">Exécutez l' **étape 1: installer le magasin de configuration local** pour installer les fichiers de configuration locaux.</span><span class="sxs-lookup"><span data-stu-id="af7b1-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="af7b1-121">Exécutez l' **étape 2: configurer ou supprimer les composants serveur Lync** pour installer le rôle serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af7b1-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="af7b1-122">Exécutez l' **étape 3: demandez, installez ou attribuez des certificats** pour attribuer les certificats.</span><span class="sxs-lookup"><span data-stu-id="af7b1-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="af7b1-123">Exécutez l' **étape 4: démarrer des services** pour démarrer des services sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="af7b1-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="af7b1-124">Pour plus d’informations sur l’exécution de l’Assistant Déploiement, voir la documentation de déploiement pour le rôle de serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="af7b1-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

