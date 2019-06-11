---
title: 'Lync Server 2013 : Configuration des annonces pour les numéros non affectés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8375e3481703078013d85060d20d0e9f500374b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="44a1c-102">Configuration des annonces pour les numéros non affectés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44a1c-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44a1c-103">_**Dernière modification de la rubrique:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="44a1c-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="44a1c-104">L’application d’annonce est une fonctionnalité voix entreprise qui permet de configurer ce qui arrive aux appels d’extensions non attribuées (extensions valides pour votre organisation, mais qui ne sont pas attribuées à une personne ou à un téléphone).</span><span class="sxs-lookup"><span data-stu-id="44a1c-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="44a1c-105">Par exemple, vous pouvez définir que les appels passés à des numéros non attribués doivent déclencher la lecture d’un message et/ou qu’ils doivent être transférés vers une autre destination.</span><span class="sxs-lookup"><span data-stu-id="44a1c-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="44a1c-106">L’application d’annonce est installée en tant que fonctionnalité de l’application de groupe de réponse sur le serveur frontal ou le serveur Standard Edition Server lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="44a1c-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="44a1c-107">Vous devez configurer les annonces en téléchargeant vos fichiers audio ou en configurant la synthèse vocale (TTS) et la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="44a1c-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="44a1c-108">Cette section vous guide dans la configuration des annonces du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="44a1c-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="44a1c-109">Il part du principe que vous avez déjà lu les sections de planification relatives aux annonces et déployé un serveur Enterprise Edition ou un serveur Standard Edition avec Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="44a1c-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="44a1c-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="44a1c-110">In This Section</span></span>

  - [<span data-ttu-id="44a1c-111">Conditions prérequises et rôles de configuration d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44a1c-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="44a1c-112">Processus de déploiement de l’application d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44a1c-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="44a1c-113">Créer une annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44a1c-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="44a1c-114">Configuration de la table des numéros non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44a1c-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="44a1c-115">Facultatif Vérifier le déploiement d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44a1c-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="44a1c-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="44a1c-116">See Also</span></span>


[<span data-ttu-id="44a1c-117">Planifier les fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44a1c-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

