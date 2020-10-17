---
title: 'Lync Server 2013 : définition de la configuration requise pour les conférences'
description: 'Lync Server 2013 : définition de la configuration requise pour les conférences.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 009a80d2fd48341723743bb6a06ad2ee05289a6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545410"
---
# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="e0924-103">Définition de la configuration requise pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0924-103">Defining your requirements for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0924-104">_**Dernière modification de la rubrique :** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="e0924-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="e0924-p101">Lorsque vous déterminez les fonctionnalités de conférence à déployer, vous devez tenir compte des fonctionnalités que vous souhaitez mettre à disposition de vos utilisateurs et des capacités de votre bande passante réseau. La liste de questions suivante va vous guider tout au long du processus de planification du système de conférence afin que vous puissiez déterminer les fonctionnalités de conférence à déployer en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e0924-p101">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities. The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="e0924-107">**Souhaitez-vous activer la conférence web, qui inclut la collaboration sur des documents et le partage d’application ?**</span><span class="sxs-lookup"><span data-stu-id="e0924-107">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="e0924-108">Si c’est le cas, vous devez activer la Conférence pour votre pool frontal dans l’outil de planification de Microsoft Lync Server 2013, ou dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="e0924-108">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="e0924-109">Lorsque vous activez la conférence, vous activez à la fois la conférence web et la conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="e0924-109">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="e0924-110">Le partage d’application requiert et utilise plus de bande passante réseau que la collaboration sur des documents.</span><span class="sxs-lookup"><span data-stu-id="e0924-110">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="e0924-111">Lync Server 2013 fournit un mécanisme de limitation pour contrôler chaque session de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="e0924-111">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="e0924-112">Par défaut, il est défini à 1,5 Ko/seconde pour chaque session.</span><span class="sxs-lookup"><span data-stu-id="e0924-112">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="e0924-113">Si vous ne souhaitez pas activer le partage d’application, mais que vous voulez autoriser la collaboration sur des documents, vous pouvez activer la conférence et utiliser des stratégies de réunion pour désactiver le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="e0924-113">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="e0924-114">Pour plus d’informations sur la configuration des stratégies de réunion, voir [stratégies de conférence dans Lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e0924-114">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="e0924-115">Pour permettre aux utilisateurs de partager des présentations PowerPoint, vous devez configurer Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="e0924-115">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="e0924-116">Pour plus d’informations sur la configuration d’Office Web Apps Server, voir Configuration de l' [intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="e0924-116">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="e0924-117">**Souhaitez-vous activer la conférence A/V ?**</span><span class="sxs-lookup"><span data-stu-id="e0924-117">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="e0924-118">Si c’est le cas, vous devez activer la Conférence pour votre pool frontal dans l’outil de planification Lync Server 2013 ou dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="e0924-118">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="e0924-119">Lorsque vous activez la conférence, vous activez à la fois la conférence web et la conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="e0924-119">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="e0924-p107">La conférence A/V requiert et utilise plus de bande passante réseau que la conférence web (qui inclut la collaboration sur des documents et le partage d’applications). Si vous ne souhaitez pas activer la conférence A/V, mais que vous voulez activer la conférence web, vous pouvez activer la fonctionnalité de conférence et utiliser des stratégies de réunion pour désactiver la conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="e0924-p107">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing). If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="e0924-p108">Si vous souhaitez activer la conférence audio, mais pas la conférence vidéo, vous pouvez activer la conférence A/V et utiliser des stratégies de réunion pour interdire la conférence vidéo. De même, vous pouvez activer la conférence A/V, et autoriser uniquement certains utilisateurs à initier une conférence A/V ou à y prendre part.</span><span class="sxs-lookup"><span data-stu-id="e0924-p108">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences. Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e0924-124">Voix entreprise n’est pas nécessaire pour utiliser la conférence A/V.</span><span class="sxs-lookup"><span data-stu-id="e0924-124">Enterprise Voice is not required for you to use A/V conferencing.</span></span> <span data-ttu-id="e0924-125">Si vous activez la conférence A/V, vos utilisateurs peuvent ajouter de l’audio à leurs conférences pourvu qu’ils disposent de périphériques audio, et ce même si vous utilisez un autocommutateur privé (PBX) pour votre solution téléphonique.</span><span class="sxs-lookup"><span data-stu-id="e0924-125">If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="e0924-126">**Souhaitez-vous autoriser les utilisateurs à participer à la partie audio des conférences lorsqu’ils utilisent un téléphone PSTN ?**</span><span class="sxs-lookup"><span data-stu-id="e0924-126">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="e0924-p110">Dans l’affirmative, déployez et activez la conférence rendez-vous. Les utilisateurs invités, à l’intérieur et à l’extérieur de votre organisation, peuvent alors prendre part à la partie audio des conférences par l’intermédiaire d’un téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="e0924-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="e0924-129">**Voulez-vous autoriser les utilisateurs externes avec des clients Lync Server 2013 à rejoindre les types de conférences que vous avez activés ?**</span><span class="sxs-lookup"><span data-stu-id="e0924-129">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="e0924-130">Si c’est le cas, vous devez déployer des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="e0924-130">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="e0924-131">En autorisant une participation externe aux réunions, vous optimisez votre investissement dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0924-131">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="e0924-132">Par exemple, les utilisateurs disposant d’ordinateurs portables avec Lync Server 2013 peuvent participer à des conférences où qu’ils soient, depuis leur domicile, dans l’aéroport ou sur les sites des clients.</span><span class="sxs-lookup"><span data-stu-id="e0924-132">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="e0924-133">En outre, si les serveurs Edge sont déployés, vous pouvez créer des relations fédérées avec d’autres organisations, afin que les clients ou fournisseurs de ces organisations puissent plus facilement collaborer avec vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e0924-133">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="e0924-134">Pour plus d’informations sur le déploiement des serveurs Edge, reportez-vous à la rubrique [planification de l’accès des utilisateurs externes dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) et [déploiement de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="e0924-134">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="e0924-135">Pour plus d’informations sur l’activation de l’accès externe pour Office Web Apps Server, consultez [la rubrique Publishing Office Web Apps Server in Lync Server 2013 using a reverse Proxy Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="e0924-135">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="e0924-136">**Souhaitez-vous contrôler les clients qui peuvent rejoindre des réunions Lync Server 2013 ?**</span><span class="sxs-lookup"><span data-stu-id="e0924-136">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="e0924-137">Dans l’affirmative, vous devez configurer la page de participation aux réunions, afin que seules les options clientes que vous souhaitez prendre en charge soient disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0924-137">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="e0924-138">Chaque fois qu’un utilisateur clique sur un lien pour participer à une réunion planifiée, Lync Server 2013 détecte si un client est déjà installé sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e0924-138">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="e0924-139">Il démarre alors le client par défaut et ouvre la page de participation à la réunion qui contient des liens vers d’autres clients.</span><span class="sxs-lookup"><span data-stu-id="e0924-139">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="e0924-140">La page de participation aux réunions contient toujours l’option d’utilisation de Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="e0924-140">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="e0924-141">En plus de cette option, vous pouvez décider s’il faut inclure des liens pour les participants et les versions précédentes de Communicator.</span><span class="sxs-lookup"><span data-stu-id="e0924-141">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="e0924-142">Pour plus d’informations, reportez-vous à [la rubrique Configuration de la page de participation aux réunions dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="e0924-142">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e0924-143">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e0924-143">In This Section</span></span>

  - [<span data-ttu-id="e0924-144">Configuration requise pour la conférence Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0924-144">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="e0924-145">Configuration requise pour les conférences A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0924-145">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="e0924-146">Exigences en matière de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0924-146">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0924-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e0924-147">See Also</span></span>


[<span data-ttu-id="e0924-148">Planification de la Conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0924-148">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="e0924-149">Liste de vérification du déploiement pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0924-149">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

