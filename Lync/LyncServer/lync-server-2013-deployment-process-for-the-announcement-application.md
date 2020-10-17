---
title: 'Lync Server 2013 : processus de déploiement de l’application annonce'
description: 'Lync Server 2013 : processus de déploiement de l’application annonce.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 559977c32f63fae312164b5b0c36698fa13afb09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550990"
---
# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="2aa21-103">Processus de déploiement de l’application annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2aa21-103">Deployment process for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2aa21-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2aa21-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2aa21-105">Cette section fournit une vue d’ensemble des étapes nécessaires au déploiement de l’application annonce.</span><span class="sxs-lookup"><span data-stu-id="2aa21-105">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="2aa21-106">Vous devez déployer voix entreprise avant de configurer les annonces.</span><span class="sxs-lookup"><span data-stu-id="2aa21-106">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="2aa21-107">Les composants requis par l’application d’annonce sont installés et activés lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="2aa21-107">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="2aa21-108">Processus de déploiement des annonces</span><span class="sxs-lookup"><span data-stu-id="2aa21-108">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2aa21-109">Phase</span><span class="sxs-lookup"><span data-stu-id="2aa21-109">Phase</span></span></th>
<th><span data-ttu-id="2aa21-110">Étapes</span><span class="sxs-lookup"><span data-stu-id="2aa21-110">Steps</span></span></th>
<th><span data-ttu-id="2aa21-111">Rôles</span><span class="sxs-lookup"><span data-stu-id="2aa21-111">Roles</span></span></th>
<th><span data-ttu-id="2aa21-112">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="2aa21-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2aa21-113">Configurer les paramètres d’annonce</span><span class="sxs-lookup"><span data-stu-id="2aa21-113">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2aa21-114">Créez l’annonce en enregistrant et en téléchargeant des fichiers audio ou en utilisant la synthèse vocale (TTS).</span><span class="sxs-lookup"><span data-stu-id="2aa21-114">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="2aa21-115">Configurez les plages de numéros non attribués dans la table des numéros non attribués et associez-les à l’annonce appropriée.</span><span class="sxs-lookup"><span data-stu-id="2aa21-115">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2aa21-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2aa21-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2aa21-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2aa21-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="2aa21-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2aa21-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2aa21-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2aa21-119">CsAdministrator</span></span></p>
<p><span data-ttu-id="2aa21-120">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="2aa21-120">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2aa21-121"><a href="lync-server-2013-create-an-announcement.md">Créer une annonce dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2aa21-121"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2aa21-122"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configuration de la table des numéros non attribués dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2aa21-122"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2aa21-123">Vérifier le déploiement de votre annonce</span><span class="sxs-lookup"><span data-stu-id="2aa21-123">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="2aa21-124">Testez vos annonces en les écoutant afin de vérifier que votre configuration fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="2aa21-124">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="2aa21-125"><a href="lync-server-2013-optional-verify-announcement-deployment.md">Module Vérifier le déploiement des annonces dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2aa21-125"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

