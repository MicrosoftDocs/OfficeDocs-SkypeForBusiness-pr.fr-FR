---
title: 'Lync Server 2013 : configuration des annonces pour les numéros non attribués'
description: 'Lync Server 2013 : configuration des annonces pour les numéros non attribués.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16ab636f0c6157118a00d5e46521555086c5e520
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570030"
---
# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="91793-103">Configuration des annonces pour les numéros non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91793-103">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91793-104">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="91793-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="91793-105">L’application d’annonce est une fonctionnalité voix entreprise qui vous permet de configurer les appels vers des extensions non attribuées (extensions valides pour votre organisation, mais qui ne sont pas affectées à une personne ou à un téléphone).</span><span class="sxs-lookup"><span data-stu-id="91793-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="91793-106">Par exemple, vous pouvez définir que les appels passés à des numéros non attribués doivent déclencher la lecture d’un message et/ou qu’ils doivent être transférés vers une autre destination.</span><span class="sxs-lookup"><span data-stu-id="91793-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="91793-107">L’application d’annonce est installée en tant que fonctionnalité de application Response Group sur le serveur frontal ou le serveur Standard Edition lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="91793-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="91793-108">Vous devez configurer les annonces en téléchargeant vos fichiers audio ou en configurant la synthèse vocale (TTS) et la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="91793-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="91793-109">Cette section vous guide tout au long de la configuration des annonces Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91793-109">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="91793-110">Il part du principe que vous avez déjà lu les sections de planification relatives aux annonces et déployé un serveur Enterprise Edition ou un serveur Standard Edition avec voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="91793-110">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="91793-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="91793-111">In This Section</span></span>

  - [<span data-ttu-id="91793-112">Conditions préalables et rôles de configuration d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91793-112">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="91793-113">Processus de déploiement de l’application annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91793-113">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="91793-114">Créer une annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91793-114">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="91793-115">Configuration de la table des numéros non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91793-115">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="91793-116">Module Vérifier le déploiement des annonces dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91793-116">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="91793-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="91793-117">See Also</span></span>


[<span data-ttu-id="91793-118">Planification des fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91793-118">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

