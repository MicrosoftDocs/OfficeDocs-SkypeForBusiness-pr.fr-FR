---
title: 'Lync Server 2013 : restauration d’un serveur membre Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48af9dd5b35676ee0141b771f8e50e1fbdedae6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="7b7da-102">Restauration d’un serveur membre Enterprise Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b7da-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b7da-103">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="7b7da-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="7b7da-104">Si un serveur exécutant l’un des rôles serveur suivants échoue, suivez la procédure décrite dans cette rubrique pour restaurer le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b7da-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="7b7da-105">Si plusieurs serveurs connaissent une défaillance, appliquez la procédure à chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="7b7da-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="7b7da-106">serveur frontal</span><span class="sxs-lookup"><span data-stu-id="7b7da-106">Front End Server</span></span>

  - <span data-ttu-id="7b7da-107">Serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="7b7da-107">Mediation Server</span></span>

  - <span data-ttu-id="7b7da-108">48000b</span><span class="sxs-lookup"><span data-stu-id="7b7da-108">Director</span></span>

  - <span data-ttu-id="7b7da-109">serveur de conversations permanentes</span><span class="sxs-lookup"><span data-stu-id="7b7da-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="7b7da-110">Serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7b7da-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7b7da-111">Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration.</span><span class="sxs-lookup"><span data-stu-id="7b7da-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="7b7da-112">Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration.</span><span class="sxs-lookup"><span data-stu-id="7b7da-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="7b7da-113">Vous pouvez utiliser la copie d’image après avoir installé le système d’exploitation et SQL Server, et restaurer ou réinscrire les certificats.</span><span class="sxs-lookup"><span data-stu-id="7b7da-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="7b7da-114">Pour restaurer un serveur membre</span><span class="sxs-lookup"><span data-stu-id="7b7da-114">To restore a member server</span></span>

1.  <span data-ttu-id="7b7da-115">Démarrez avec un serveur nouveau ou propre qui a le même nom de domaine complet (FQDN) que le serveur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.</span><span class="sxs-lookup"><span data-stu-id="7b7da-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b7da-116">Suivez les procédures de déploiement de serveur de votre organisation pour effectuer cette étape.</span><span class="sxs-lookup"><span data-stu-id="7b7da-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="7b7da-117">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="7b7da-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="7b7da-118">Accédez au dossier ou au support d’installation de Lync Server et démarrez l’Assistant Déploiement de Lync Server \\situé\\à\\l’installation de amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="7b7da-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="7b7da-119">Utilisez l’Assistant Déploiement pour faire ce que suit :</span><span class="sxs-lookup"><span data-stu-id="7b7da-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="7b7da-120">Exécutez l’**Étape 1 : Installer le magasin de configurations local** pour installer les fichiers de configuration locaux.</span><span class="sxs-lookup"><span data-stu-id="7b7da-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="7b7da-121">Exécutez l' **étape 2 : installer ou supprimer des composants Lync Server** pour installer le rôle serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b7da-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="7b7da-122">Exécuter l’**Étape 3 : Demander, installer ou assigner les certificats** pour assigner les certificats.</span><span class="sxs-lookup"><span data-stu-id="7b7da-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="7b7da-123">Exécutez l’**Étape 4 : Démarrer les services** pour démarrer les services sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b7da-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="7b7da-124">Pour plus d’informations sur l’exécution de l’Assistant Déploiement, reportez-vous à la documentation de déploiement du rôle serveur que vous restaurez.</span><span class="sxs-lookup"><span data-stu-id="7b7da-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

