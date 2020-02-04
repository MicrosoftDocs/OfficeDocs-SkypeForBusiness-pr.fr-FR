---
title: 'Lync Server 2013 : processus de déploiement de l’application annonce'
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
ms.openlocfilehash: dcb56f197a32403d1207cf0a15d47e0459fc41bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="4dae4-102">Processus de déploiement de l’application d’annonce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dae4-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dae4-103">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4dae4-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4dae4-104">Cette section fournit une vue d’ensemble des étapes de déploiement de l’application d’annonce.</span><span class="sxs-lookup"><span data-stu-id="4dae4-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="4dae4-105">Vous devez déployer Enterprise Voice avant de configurer les annonces.</span><span class="sxs-lookup"><span data-stu-id="4dae4-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="4dae4-106">Les composants requis par l’application d’annonce sont installés et activés lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4dae4-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="4dae4-107">Procédure de déploiement des annonces</span><span class="sxs-lookup"><span data-stu-id="4dae4-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4dae4-108">Phase</span><span class="sxs-lookup"><span data-stu-id="4dae4-108">Phase</span></span></th>
<th><span data-ttu-id="4dae4-109">Étapes</span><span class="sxs-lookup"><span data-stu-id="4dae4-109">Steps</span></span></th>
<th><span data-ttu-id="4dae4-110">Rôles</span><span class="sxs-lookup"><span data-stu-id="4dae4-110">Roles</span></span></th>
<th><span data-ttu-id="4dae4-111">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="4dae4-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4dae4-112">Configurer les paramètres d’annonce</span><span class="sxs-lookup"><span data-stu-id="4dae4-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4dae4-113">Créez l’annonce en enregistrant et en téléchargeant des fichiers audio ou en utilisant la synthèse vocale (TTS).</span><span class="sxs-lookup"><span data-stu-id="4dae4-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="4dae4-114">Configurez les plages de numéros non attribués dans la table des numéros non attribués et associez-les à l’annonce appropriée.</span><span class="sxs-lookup"><span data-stu-id="4dae4-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4dae4-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4dae4-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="4dae4-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="4dae4-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="4dae4-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4dae4-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="4dae4-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4dae4-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="4dae4-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="4dae4-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4dae4-120"><a href="lync-server-2013-create-an-announcement.md">Créer une annonce dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dae4-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="4dae4-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configuration de la table des numéros non attribués dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dae4-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4dae4-122">Vérifier le déploiement de votre annonce</span><span class="sxs-lookup"><span data-stu-id="4dae4-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="4dae4-123">Testez vos annonces en les écoutant afin de vérifier que votre configuration fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="4dae4-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="4dae4-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">Facultatif Vérifier le déploiement d’annonce dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4dae4-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

