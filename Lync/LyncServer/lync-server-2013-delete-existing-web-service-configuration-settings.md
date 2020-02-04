---
title: 'Lync Server 2013 : supprimer les paramètres de configuration d’un service Web existant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb310836e78d46f94412018f3034a4a5f7d7173
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="088d2-102">Supprimer les paramètres de configuration d’un service Web existant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="088d2-102">Delete existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="088d2-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="088d2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="088d2-104">Pour supprimer les paramètres de configuration des services web, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="088d2-104">Follow these steps to delete web service configuration settings.</span></span>

<div>

## <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="088d2-105">Pour supprimer des paramètres de configuration d’un service web existant</span><span class="sxs-lookup"><span data-stu-id="088d2-105">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="088d2-106">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="088d2-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="088d2-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="088d2-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="088d2-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="088d2-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="088d2-109">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.</span><span class="sxs-lookup"><span data-stu-id="088d2-109">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="088d2-110">Dans le champ de recherche de la page **Service web**, tapez l’intégralité ou une partie du nom de la stratégie à supprimer.</span><span class="sxs-lookup"><span data-stu-id="088d2-110">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="088d2-111">Dans la liste des stratégies, cliquez sur la stratégie à supprimer, sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="088d2-111">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="088d2-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="088d2-112">Click **OK**.</span></span>

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="088d2-113">Supprimer des paramètres de configuration de service Web à l’aide des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="088d2-113">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="088d2-114">Vous pouvez supprimer des paramètres de configuration de service Web à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsWebServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="088d2-114">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="088d2-115">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="088d2-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="088d2-116">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="088d2-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="088d2-117">Pour supprimer une collection de paramètres de configuration des services web</span><span class="sxs-lookup"><span data-stu-id="088d2-117">To delete a specific collection of web service configuration settings</span></span>

  - <span data-ttu-id="088d2-118">La commande ci-dessous supprime les paramètres de sécurité des services web appliqués au site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="088d2-118">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="088d2-119">Pour supprimer tous les paramètres de configuration des services web appliqués à l’étendue du site</span><span class="sxs-lookup"><span data-stu-id="088d2-119">To delete all of the web service configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="088d2-120">La commande ci-dessous supprime tous les paramètres de sécurité des services web appliqués à l’étendue des services :</span><span class="sxs-lookup"><span data-stu-id="088d2-120">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="088d2-121">Pour supprimer tous les paramètres de configuration des services web qui autorisent l’authentification des certificats</span><span class="sxs-lookup"><span data-stu-id="088d2-121">To delete all of the web service configuration settings that allow certificate authentication</span></span>

  - <span data-ttu-id="088d2-122">La commande ci-dessous supprime tous les paramètres de sécurité des services web qui autorisent l’authentification des certificats :</span><span class="sxs-lookup"><span data-stu-id="088d2-122">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

<span data-ttu-id="088d2-123">Pour plus d’informations, consultez la rubrique [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="088d2-123">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="088d2-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="088d2-124">See Also</span></span>


[<span data-ttu-id="088d2-125">Configuration de l’authentification dans le panneau de configuration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="088d2-125">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

