---
title: 'Lync Server 2013 : activer ou désactiver les conférences rendez-vous pour les réunions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable dial-in conferencing for meetings
ms:assetid: 418dcf2d-c8d6-4b2c-b1ab-8723c7ef53e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688036(v=OCS.15)
ms:contentKeyID: 49733627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4600d5f978c553699029416951505c952f62bb62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a><span data-ttu-id="c2fec-102">Activer ou désactiver les conférences rendez-vous pour les réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2fec-102">Enable or disable dial-in conferencing for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2fec-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c2fec-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c2fec-104">La procédure suivante vous explique comment permettre aux utilisateurs de participer à une réunion à l’aide d’un composant WebPart.</span><span class="sxs-lookup"><span data-stu-id="c2fec-104">The following procedure describes how to allow user to join a meeting using dial-in.</span></span>

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a><span data-ttu-id="c2fec-105">Pour activer ou désactiver la Conférence rendez-vous</span><span class="sxs-lookup"><span data-stu-id="c2fec-105">To enable or disable dial-in conferencing</span></span>

1.  <span data-ttu-id="c2fec-106">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="c2fec-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c2fec-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c2fec-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c2fec-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c2fec-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c2fec-109">Dans la barre de navigation de gauche, cliquez sur **Conférence** , puis sur **stratégie de conférence**.</span><span class="sxs-lookup"><span data-stu-id="c2fec-109">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="c2fec-110">Dans la liste des stratégies de conférence, sélectionnez celle pour laquelle vous voulez activer la conférence rendez-vous, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="c2fec-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="c2fec-p102">Pour autoriser les utilisateurs à rejoindre une réunion en composant un numéro d’accès, activez la case à cocher **Activer la conférence rendez-vous RTC**. Par défaut, les utilisateurs peuvent accéder aux réunions par le biais du réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="c2fec-p102">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>

6.  <span data-ttu-id="c2fec-113">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="c2fec-113">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

