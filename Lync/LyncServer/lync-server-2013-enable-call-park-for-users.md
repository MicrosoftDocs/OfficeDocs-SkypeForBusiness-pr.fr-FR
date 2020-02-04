---
title: 'Lync Server 2013 : activer le parc d’appels pour les utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd89ba10f5cae16e88c65e6e56178fc517c71213
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a><span data-ttu-id="afd7d-102">Activer le parc d’appels pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afd7d-102">Enable Call Park for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afd7d-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="afd7d-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="afd7d-104">Les utilisateurs ne peuvent pas parcer les appels ou récupérer les appels en stationnement tant qu’ils sont activés pour le parc d’appels dans la politique vocale.</span><span class="sxs-lookup"><span data-stu-id="afd7d-104">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afd7d-105">Par défaut, le parc d’appels est désactivé pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="afd7d-105">By default, Call Park is disabled for all users.</span></span>



</div>

<span data-ttu-id="afd7d-106">Vous pouvez activer le parc d’appels au niveau de l’étendue globale, ou à l’étendue du site ou l’étendue de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="afd7d-106">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="afd7d-107">L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale.</span><span class="sxs-lookup"><span data-stu-id="afd7d-107">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="afd7d-108">Si vous avez plusieurs stratégies vocales, passez en revue toutes les stratégies pour activer le parc d’appels, pas seulement la politique globale.</span><span class="sxs-lookup"><span data-stu-id="afd7d-108">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="afd7d-109">Pour utiliser le panneau de configuration de Lync Server pour activer le parc d’appels pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="afd7d-109">To Use Lync Server Control Panel to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="afd7d-110">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="afd7d-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="afd7d-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afd7d-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="afd7d-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="afd7d-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="afd7d-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="afd7d-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="afd7d-114">Cliquez sur l’onglet **Stratégie de la voix**.</span><span class="sxs-lookup"><span data-stu-id="afd7d-114">Click the **Voice Policy** tab.</span></span>

5.  <span data-ttu-id="afd7d-115">Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.</span><span class="sxs-lookup"><span data-stu-id="afd7d-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>

6.  <span data-ttu-id="afd7d-116">Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.</span><span class="sxs-lookup"><span data-stu-id="afd7d-116">Under **Calling features**, select **Enable call park**.</span></span>

7.  <span data-ttu-id="afd7d-117">Cliquez sur **OK** pour enregistrer la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="afd7d-117">Click **OK** to save the voice policy</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="afd7d-118">Utiliser des cmdlets pour activer le parc d’appels pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="afd7d-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1.  <span data-ttu-id="afd7d-119">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="afd7d-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>

2.  <span data-ttu-id="afd7d-120">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="afd7d-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="afd7d-121">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="afd7d-121">Run:</span></span>
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    <span data-ttu-id="afd7d-122">Par exemple, pour activer le parc d’appels pour la stratégie vocale globale par défaut :</span><span class="sxs-lookup"><span data-stu-id="afd7d-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="afd7d-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="afd7d-123">See Also</span></span>


[<span data-ttu-id="afd7d-124">Créer une stratégie de voix et configurer les enregistrements d’utilisation RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afd7d-124">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

