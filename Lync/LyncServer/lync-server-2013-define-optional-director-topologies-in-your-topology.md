---
title: 'Lync Server 2013 : définition de topologies facultatives de directeur dans votre topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1da76c885eb290673836f518ab9a1bac9e516c3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a><span data-ttu-id="a83b1-102">Définir des topologies facultatives de directeur dans votre topologie pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a83b1-102">Define optional Director topologies in your topology for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a83b1-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a83b1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a83b1-104">Les directeurs Lync Server 2013 peuvent être des serveurs à instance unique ou être installés en tant que pool à charge équilibrée de plusieurs directeurs pour une disponibilité et une capacité supérieures.</span><span class="sxs-lookup"><span data-stu-id="a83b1-104">Lync Server 2013 Directors can be single-instance servers or they can be installed as a load-balanced pool of multiple Directors for higher availability and capacity.</span></span> <span data-ttu-id="a83b1-105">L’équilibrage de la charge matérielle et de la charge DNS sont tous deux pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a83b1-105">Both hardware load balancing and Domain Name System (DNS) load balancing are supported.</span></span> <span data-ttu-id="a83b1-106">Cette rubrique explique comment configurer l’équilibrage de la charge DNS pour les pools directeurs.</span><span class="sxs-lookup"><span data-stu-id="a83b1-106">This topic explains how to configure DNS load balancing for Director pools.</span></span>

<span data-ttu-id="a83b1-107">Pour réussir à publier, activer ou désactiver une topologie lorsque vous ajoutez ou supprimez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes **RTCUniversalServerAdmins** et **Domain Admins**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-107">To successfully publish, enable, or disable a topology when you add or remove a server role, you should be logged on as a user who is a member of the **RTCUniversalServerAdmins** and **Domain Admins** groups.</span></span> <span data-ttu-id="a83b1-108">Il est également possible de déléguer les droits et les autorisations d’administrateur appropriés pour ajouter des rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="a83b1-108">You can also delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="a83b1-109">Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) dans la documentation de déploiement du serveur Standard Edition Server ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a83b1-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="a83b1-110">En ce qui concerne les autres modifications de configuration, seule l’appartenance au groupe **RTCUniversalServerAdmins** est requise.</span><span class="sxs-lookup"><span data-stu-id="a83b1-110">For other configuration changes, only membership in the **RTCUniversalServerAdmins** group is required.</span></span>

<span data-ttu-id="a83b1-111">Cette rubrique décrit les étapes à suivre pour définir et publier la topologie pour les deux topologies de directeur :</span><span class="sxs-lookup"><span data-stu-id="a83b1-111">This topic describes the steps to define and publish the topology for the two Director topologies:</span></span>

  - <span data-ttu-id="a83b1-112">Pour définir le directeur (instance unique)</span><span class="sxs-lookup"><span data-stu-id="a83b1-112">To define the Director (single instance)</span></span>

  - <span data-ttu-id="a83b1-113">Pour définir le directeur (pool de plusieurs directeurs)</span><span class="sxs-lookup"><span data-stu-id="a83b1-113">To define the Director (multiple Director pool)</span></span>

<div>

## <a name="to-define-the-director-single-instance"></a><span data-ttu-id="a83b1-114">Pour définir le directeur (instance unique)</span><span class="sxs-lookup"><span data-stu-id="a83b1-114">To define the Director (single instance)</span></span>

1.  <span data-ttu-id="a83b1-115">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a83b1-116">Dans la page d’accueil, cliquez sur **Télécharger la topologie à partir du déploiement existant**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-116">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="a83b1-117">Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom et l’emplacement de la copie locale de la topologie existante, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-117">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="a83b1-118">Développez le site dans lequel vous planifiez d’ajouter le directeur , cliquez avec le bouton droit sur **Pools directeurs**, puis cliquez sur **Nouveau pool directeur**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-118">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="a83b1-119">Dans la boîte de dialogue **Définir le nom de domaine complet du pool directeur**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a83b1-119">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="a83b1-120">Dans **Nom de domaine complet du pool**, tapez le nom de domaine complet du pool directeur.</span><span class="sxs-lookup"><span data-stu-id="a83b1-120">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="a83b1-121">Cliquez sur **Pool d’un seul ordinateur**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-121">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="a83b1-122">Dans la boîte de dialogue **Définir le partage de fichiers**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a83b1-122">In the **Define the file share** dialog box, do one of the following:</span></span>
    
    1.  <span data-ttu-id="a83b1-123">Pour utiliser un partage de fichiers existant, cliquez sur **Utiliser un partage de fichiers précédemment défini**, sélectionnez un partage de fichiers dans la liste, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-123">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
    2.  <span data-ttu-id="a83b1-124">Pour créer un partage de fichiers, cliquez sur **Définir un nouveau partage de fichiers**, tapez le nom de domaine complet de l’emplacement du partage de fichiers dans **Nom de domaine complet du serveur de fichiers**, tapez le nom du partage dans **Partage de fichiers**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-124">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a83b1-125">Le partage de fichiers que vous spécifiez ou créez à cette étape doit exister ou être créé avant de publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="a83b1-125">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="a83b1-126">Le partage de fichiers attribué à un directeur n’est pas utilisé, si bien que vous pouvez attribuer le partage de fichiers de n’importe quel pool dans l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a83b1-126">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

7.  <span data-ttu-id="a83b1-127">Dans la boîte de dialogue **Spécifier l’URL des services Web**, dans **URL de base externe**, spécifiez le nom de domaine complet des directeurs, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-127">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a83b1-128">Le nom doit pouvoir être résolu à partir des serveurs DNS Internet et doit pointer vers l’adresse IP publique du proxy inverse. Celui-ci écoute les demandes HTTP/HTTPS envoyées à cette URL et les transmet via le serveur proxy au répertoire virtuel des services web externes sur ce directeur.</span><span class="sxs-lookup"><span data-stu-id="a83b1-128">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests to that URL and proxies them to the external Web Services virtual directory on that Director.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a83b1-129">Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet (FQDN) des services Web externes doit être unique.</span><span class="sxs-lookup"><span data-stu-id="a83b1-129">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="a83b1-130">Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a83b1-130">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="a83b1-131">Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour tout directeur ou pool directeur doit être unique à partir d’un autre directeur ou pool Directeur, ainsi que d’un pool frontal ou d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a83b1-131">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="a83b1-132">Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.</span><span class="sxs-lookup"><span data-stu-id="a83b1-132">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

8.  <span data-ttu-id="a83b1-133">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="a83b1-133">Publish the topology.</span></span>

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a><span data-ttu-id="a83b1-134">Pour définir le directeur (pool de plusieurs directeurs)</span><span class="sxs-lookup"><span data-stu-id="a83b1-134">To define the Director (multiple Director pool)</span></span>

1.  <span data-ttu-id="a83b1-135">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-135">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a83b1-136">Dans la page d’accueil, cliquez sur **Télécharger la topologie à partir du déploiement existant**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-136">On the welcome page, click **Download Topology from Existing Deployment**.</span></span>

3.  <span data-ttu-id="a83b1-137">Dans la boîte de dialogue **Enregistrer la topologie sous**, tapez le nom et l’emplacement de la copie locale de la topologie existante, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-137">In the **Save Topology As** dialog box, type the name and location of the local copy of the existing topology, and then click **Save**.</span></span>

4.  <span data-ttu-id="a83b1-138">Développez le site dans lequel vous planifiez d’ajouter le directeur , cliquez avec le bouton droit sur **Pools directeurs**, puis cliquez sur **Nouveau pool directeur**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-138">Expand the site in which you plan to add the Director, right-click **Director pools**, and then click **New Director Pool**.</span></span>

5.  <span data-ttu-id="a83b1-139">Dans la boîte de dialogue **Définir le nom de domaine complet du pool directeur**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a83b1-139">In the **Define the Director pool FQDN** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="a83b1-140">Dans **Nom de domaine complet du pool**, tapez le nom de domaine complet du pool directeur.</span><span class="sxs-lookup"><span data-stu-id="a83b1-140">In **Pool FQDN**, type the FQDN for the Director pool.</span></span>
    
      - <span data-ttu-id="a83b1-141">Cliquez sur **Pool de plusieurs ordinateurs**, puis sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-141">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="a83b1-142">Dans la boîte de dialogue **Définissez les ordinateurs inclus dans ce pool**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a83b1-142">In the **Define the computers in this pool** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="a83b1-143">Spécifiez le nom de domaine complet d’ordinateur du premier membre du pool, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-143">Specify the computer FQDN of the first pool member, and then click **Add**.</span></span>
    
      - <span data-ttu-id="a83b1-p104">Répétez l’étape précédente pour chaque ordinateur à ajouter. Lorsque vous avez terminé, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-p104">Repeat the previous step for each computer that you want to add. When you are finished, click **Next**.</span></span>

7.  <span data-ttu-id="a83b1-146">Dans la boîte de dialogue **Définir le partage de fichiers**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a83b1-146">In the **Define the file share** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="a83b1-147">Pour utiliser un partage de fichiers existant, cliquez sur **Utiliser un partage de fichiers précédemment défini**, sélectionnez un partage de fichiers dans la liste, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-147">To use an existing file share, click **Use a previously defined file share**, select a file share from the list, and then click **Next**.</span></span>
    
      - <span data-ttu-id="a83b1-148">Pour créer un partage de fichiers, cliquez sur **Définir un nouveau partage de fichiers**, tapez le nom de domaine complet de l’emplacement du partage de fichiers dans **Nom de domaine complet du serveur de fichiers**, tapez le nom du partage dans **Partage de fichiers**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-148">To create a new file share, click **Define a new file share**, type the FQDN for the location of the file share in **File Server FQDN**, type the name of the share in **File Share**, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a83b1-149">Le partage de fichiers que vous spécifiez ou créez à cette étape doit exister ou être créé avant de publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="a83b1-149">The file share that you specify or create in this step must exist or be created prior to publishing the topology.</span></span><BR><span data-ttu-id="a83b1-150">Le partage de fichiers attribué à un directeur n’est pas utilisé, si bien que vous pouvez attribuer le partage de fichiers de n’importe quel pool dans l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a83b1-150">The file share assigned to a Director is not actually used, so you can assign the file share of any pool in the organization.</span></span>

    
    </div>

8.  <span data-ttu-id="a83b1-151">Dans la boîte de dialogue **Spécifier l’URL des services Web**, dans **URL de base externe**, spécifiez le nom de domaine complet des directeurs, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a83b1-151">In the **Specify the Web Services URL** dialog box, in **External Base URL**, specify the FQDN for the Directors, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a83b1-152">Le nom doit pouvoir être résolu à partir des serveurs DNS Internet et doit pointer vers l’adresse IP publique du proxy inverse. Celui-ci écoute les demandes HTTP/HTTPS envoyées à cette URL et les redirige via proxy au répertoire virtuel des services Web externes sur ce pool directeur.</span><span class="sxs-lookup"><span data-stu-id="a83b1-152">The name must be resolvable from Internet DNS servers and point to the public IP address of the reverse proxy, which listens for HTTP/HTTPS requests sent to that URL and proxies them to the external Web Services virtual directory on that Director pool.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a83b1-153">Si vous avez plusieurs pools frontaux ou serveurs frontaux, le nom de domaine complet (FQDN) des services Web externes doit être unique.</span><span class="sxs-lookup"><span data-stu-id="a83b1-153">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="a83b1-154">Par exemple, si vous définissez le nom de domaine complet des services Web externes d’un serveur frontal en tant que <STRONG>pool01.contoso.com</STRONG>, vous ne pouvez pas utiliser <STRONG>pool01.contoso.com</STRONG> pour un autre pool frontal ou serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a83b1-154">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="a83b1-155">Si vous déployez également des directeurs, le nom de domaine complet des services Web externes défini pour tout directeur ou pool directeur doit être unique à partir d’un autre directeur ou pool Directeur, ainsi que d’un pool frontal ou d’un serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="a83b1-155">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="a83b1-156">Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.</span><span class="sxs-lookup"><span data-stu-id="a83b1-156">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

9.  <span data-ttu-id="a83b1-157">Publiez la topologie.</span><span class="sxs-lookup"><span data-stu-id="a83b1-157">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

