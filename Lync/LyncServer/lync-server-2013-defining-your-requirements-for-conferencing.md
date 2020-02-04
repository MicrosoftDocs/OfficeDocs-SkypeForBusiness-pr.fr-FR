---
title: 'Lync Server 2013 : Définition de la configuration requise pour les conférences'
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
ms.openlocfilehash: c19269ef06fc2aa7ec19e2ede53f406b345536b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="79b9b-102">Définition de la configuration requise pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79b9b-102">Defining your requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79b9b-103">_**Dernière modification de la rubrique :** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="79b9b-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="79b9b-104">Lorsque vous déterminez les fonctions de conférence à déployer, vous devez tenir compte des fonctionnalités que vous souhaitez mettre à disposition de vos utilisateurs et des capacités de votre bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="79b9b-104">When you are determining which conferencing capabilities to deploy, you need to consider the features that you want available to your users and your network bandwidth capabilities.</span></span> <span data-ttu-id="79b9b-105">La liste des questions suivante vous guide tout au long du processus de planification des conférences pour déterminer les fonctionnalités de la Conférence que vous devez déployer en fonction de la configuration requise pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="79b9b-105">The following list of questions guides you through the conferencing planning process to determine what features of conferencing you should deploy, based on your organization’s requirements.</span></span>

  - <span data-ttu-id="79b9b-106">**Souhaitez-vous activer la conférence web, qui inclut la collaboration sur des documents et le partage d’application ?**</span><span class="sxs-lookup"><span data-stu-id="79b9b-106">**Do you want to enable web conferencing, which includes document collaboration and application sharing?**</span></span>
    
    <span data-ttu-id="79b9b-107">Si tel est le cas, vous devez activer la Conférence pour votre liste frontale dans Microsoft Lync Server 2013, l’outil de planification ou le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="79b9b-107">If so, you must enable conferencing for your Front End pool in the Microsoft Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="79b9b-108">Lorsque vous activez la fonctionnalité de conférence, vous activez les conférences Web et la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="79b9b-108">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="79b9b-109">Le partage d’application nécessite et utilise plus de bande passante réseau que la collaboration sur des documents.</span><span class="sxs-lookup"><span data-stu-id="79b9b-109">Application sharing requires and uses more network bandwidth than document collaboration.</span></span> <span data-ttu-id="79b9b-110">Lync Server 2013 fournit un mécanisme de limitation pour contrôler chaque session de partage d’application.</span><span class="sxs-lookup"><span data-stu-id="79b9b-110">Lync Server 2013 provides a throttling mechanism to control each application sharing session.</span></span> <span data-ttu-id="79b9b-111">Par défaut, il est défini à 1,5 Ko/seconde pour chaque session.</span><span class="sxs-lookup"><span data-stu-id="79b9b-111">By default, this is set to 1.5 KB/second for each session.</span></span>
    
    <span data-ttu-id="79b9b-112">Si vous ne souhaitez pas activer le partage d’application, mais que vous voulez collaborer sur des documents, vous pouvez activer les conférences et utiliser les stratégies de réunion pour désactiver le partage d’application.</span><span class="sxs-lookup"><span data-stu-id="79b9b-112">If you do not want to enable application sharing but you do want document collaboration, you can enable conferencing and use meeting policies to disable application sharing.</span></span> <span data-ttu-id="79b9b-113">Pour plus d’informations sur la configuration des stratégies de réunion, voir [stratégies de conférence dans Lync Server 2013](lync-server-2013-conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="79b9b-113">For details about configuring meeting policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md).</span></span>
    
    <span data-ttu-id="79b9b-114">Pour autoriser les utilisateurs à partager des présentations PowerPoint, vous devez configurer Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="79b9b-114">To enable users to share PowerPoint presentations, you need to configure Office Web Apps Server.</span></span> <span data-ttu-id="79b9b-115">Pour plus d’informations sur la configuration d’Office Web Apps Server, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="79b9b-115">For details about configuring Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="79b9b-116">**Souhaitez-vous activer les conférences A/V ?**</span><span class="sxs-lookup"><span data-stu-id="79b9b-116">**Do you want to enable A/V conferencing?**</span></span>
    
    <span data-ttu-id="79b9b-117">Si tel est le cas, vous devez activer les conférences pour votre liste frontale dans l’outil de planification de Lync Server 2013, ou dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="79b9b-117">If so, you must enable conferencing for your Front End pool in the Lync Server 2013, Planning Tool or in Topology Builder.</span></span> <span data-ttu-id="79b9b-118">Lorsque vous activez la fonctionnalité de conférence, vous activez les conférences Web et la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="79b9b-118">When you enable conferencing, you enable both web conferencing and A/V conferencing.</span></span>
    
    <span data-ttu-id="79b9b-119">La fonction de conférence A/V nécessite et utilise davantage de bande passante réseau que les conférences Web (notamment la collaboration sur les documents et le partage d’applications).</span><span class="sxs-lookup"><span data-stu-id="79b9b-119">A/V conferencing requires and uses more network bandwidth than web conferencing (which includes document collaboration and application sharing).</span></span> <span data-ttu-id="79b9b-120">Si vous ne souhaitez pas activer la fonction de conférence A/V mais que vous voulez activer les conférences Web, vous pouvez activer les conférences et utiliser les stratégies de réunion pour désactiver les conférences A/V.</span><span class="sxs-lookup"><span data-stu-id="79b9b-120">If you do not want to enable A/V conferencing but you do want to enable web conferencing, you can enable conferencing and use meeting policies to disable A/V conferences.</span></span>
    
    <span data-ttu-id="79b9b-121">Si vous voulez activer les conférences audio sans visioconférence, vous pouvez activer les conférences A/V et utiliser des stratégies de réunion pour empêcher les visioconférences.</span><span class="sxs-lookup"><span data-stu-id="79b9b-121">If you do want to enable audio conferences but not video conferences, you can enable A/V conferencing and use meeting policies to prevent video conferences.</span></span> <span data-ttu-id="79b9b-122">De même, vous pouvez activer la conférence A/V et ne permettre qu’à certains utilisateurs de commencer une conférence A/V ou d’y participer.</span><span class="sxs-lookup"><span data-stu-id="79b9b-122">Alternatively, you can enable A/V conferencing and enable only certain users to start or participate in A/V conferences.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="79b9b-p109">Vous n’êtes pas obligé d’utiliser Voix Entreprise pour utiliser la conférence A/V. Si vous activez la conférence A/V, vos utilisateurs peuvent ajouter de l’audio à leurs conférences sous réserve qu’ils disposent de périphériques audio, et ce, même si vous utilisez un autocommutateur privé (PBX) pour votre solution téléphonique.</span><span class="sxs-lookup"><span data-stu-id="79b9b-p109">Enterprise Voice is not required for you to use A/V conferencing. If you enable A/V conferencing, your users can add audio to their conferences if they have audio devices, even if you use a PBX for your telephone solution.</span></span>

    
    </div>

  - <span data-ttu-id="79b9b-125">**Souhaitez-vous permettre aux utilisateurs d’accéder à la partie audio des conférences lors de l’utilisation d’un téléphone RTC ?**</span><span class="sxs-lookup"><span data-stu-id="79b9b-125">**Do you want to enable users to join the audio portion of conferences when using a PSTN phone?**</span></span>
    
    <span data-ttu-id="79b9b-p110">Si c’est le cas, déployez et activez la conférence rendez-vous. Les utilisateurs invités, à l’intérieur et à l’extérieur de votre organisation, peuvent alors participer à la partie audio des conférences par l’intermédiaire d’un téléphone RTC.</span><span class="sxs-lookup"><span data-stu-id="79b9b-p110">If so, deploy and enable dial-in conferencing. Invited users, both inside and outside your organization, can then join the audio portion of conferences by using a PSTN phone.</span></span>

  - <span data-ttu-id="79b9b-128">**Souhaitez-vous autoriser les utilisateurs externes disposant de clients Lync Server 2013 à rejoindre les types de conférences que vous avez activées ?**</span><span class="sxs-lookup"><span data-stu-id="79b9b-128">**Do you want to enable external users with Lync Server 2013 clients to join the types of conferences that you have enabled?**</span></span>
    
    <span data-ttu-id="79b9b-129">Si tel est le cas, vous devez déployer des serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="79b9b-129">If so, you should deploy Edge Servers.</span></span> <span data-ttu-id="79b9b-130">En autorisant la participation externe aux réunions, vous Maximisez votre investissement dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79b9b-130">By allowing external participation in meetings, you maximize your investment in Lync Server 2013.</span></span> <span data-ttu-id="79b9b-131">Par exemple, les utilisateurs d’ordinateurs portables dotés de Lync Server 2013 peuvent participer à des conférences où qu’elles se trouvent : chez vous, dans l’aéroport ou sur les sites du client.</span><span class="sxs-lookup"><span data-stu-id="79b9b-131">For example, users with laptops with Lync Server 2013 can join conferences from wherever they are—at home, in the airport, or at customer sites.</span></span>
    
    <span data-ttu-id="79b9b-132">De plus, avec les serveurs de périphérie déployés, vous pouvez créer des relations fédérées avec d’autres organisations, telles que vos clients ou fournisseurs, et les utilisateurs de ces organisations pourront plus facilement collaborer avec vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="79b9b-132">Additionally, with Edge Servers deployed you can create federated relationships with other organizations-such as your customers or vendors-and users from those organizations can more easily collaborate with your users.</span></span>
    
    <span data-ttu-id="79b9b-133">Pour plus d’informations sur le déploiement de serveurs Edge, voir [planification d’un accès utilisateur externe dans Lync server 2013](lync-server-2013-planning-for-external-user-access.md) et [déploiement d’un accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="79b9b-133">For details about deploying Edge Servers, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span> <span data-ttu-id="79b9b-134">Pour plus d’informations sur l’activation de l’accès externe pour Office Web Apps Server, voir [publication d’Office Web Apps Server dans Lync server 2013 à l’aide d’un serveur proxy inverse](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span><span class="sxs-lookup"><span data-stu-id="79b9b-134">For details about enabling external access for Office Web Apps Server, see [Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md).</span></span>

  - <span data-ttu-id="79b9b-135">**Souhaitez-vous contrôler les clients qui peuvent rejoindre des réunions Lync Server 2013 ?**</span><span class="sxs-lookup"><span data-stu-id="79b9b-135">**Do you want to control the clients that can join Lync Server 2013 meetings?**</span></span>
    
    <span data-ttu-id="79b9b-136">Si c’est le cas, vous devez configurer la page de participation aux réunions de sorte que seules les options du client à prendre en charge soient disponibles.</span><span class="sxs-lookup"><span data-stu-id="79b9b-136">If so, you should configure the meeting join page so that only the client options that you want to support are available.</span></span> <span data-ttu-id="79b9b-137">Chaque fois qu’un utilisateur clique sur un lien pour rejoindre une réunion planifiée, Lync Server 2013 détecte si un client est déjà installé sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="79b9b-137">Each time a user clicks a link to join a scheduled meeting, Lync Server 2013 detects whether a client is already installed on the computer.</span></span> <span data-ttu-id="79b9b-138">Il lance alors le client par défaut et ouvre la page de participation à la réunion qui contient des liens vers d’autres clients.</span><span class="sxs-lookup"><span data-stu-id="79b9b-138">It then starts the default client and opens the meeting join page, which contains links for alternate clients.</span></span> <span data-ttu-id="79b9b-139">La page de participation à une réunion contient toujours l’option d’utilisation de Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="79b9b-139">The meeting join page always contains the option to use Microsoft Lync Web App.</span></span> <span data-ttu-id="79b9b-140">Outre cette option, vous pouvez décider d’inclure ou non des liens vers Participant et les versions précédentes de Communicator.</span><span class="sxs-lookup"><span data-stu-id="79b9b-140">In addition to this option, you can decide whether to include links for Attendee and previous versions of Communicator.</span></span> <span data-ttu-id="79b9b-141">Pour plus d’informations, reportez-vous à [la rubrique Configuration de la page de participation à une réunion dans Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span><span class="sxs-lookup"><span data-stu-id="79b9b-141">For details, see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="79b9b-142">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="79b9b-142">In This Section</span></span>

  - [<span data-ttu-id="79b9b-143">Configuration requise pour les conférences Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79b9b-143">Web conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-requirements.md)

  - [<span data-ttu-id="79b9b-144">Exigences de conférence A/V dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79b9b-144">A/V conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-a-v-conferencing-requirements.md)

  - [<span data-ttu-id="79b9b-145">Configuration requise pour les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79b9b-145">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79b9b-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79b9b-146">See Also</span></span>


[<span data-ttu-id="79b9b-147">Planification des conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79b9b-147">Planning for conferencing in Lync Server 2013</span></span>](lync-server-2013-planning-for-conferencing.md)  
[<span data-ttu-id="79b9b-148">Liste de vérification du déploiement pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79b9b-148">Deployment checklist for conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

