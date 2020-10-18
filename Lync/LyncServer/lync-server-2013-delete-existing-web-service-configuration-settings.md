---
title: 'Lync Server 2013 : suppression des paramètres de configuration d’un service Web existant'
description: 'Lync Server 2013 : suppression des paramètres de configuration d’un service Web existant.'
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
ms.openlocfilehash: 5a28197f26a447112e29b6e4a831585dd49a9854
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575850"
---
# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="da265-103">Supprimer les paramètres de configuration de service Web existants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da265-103">Delete existing Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da265-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="da265-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="da265-105">Procédez comme suit pour supprimer les paramètres de configuration du service Web.</span><span class="sxs-lookup"><span data-stu-id="da265-105">Follow these steps to delete web service configuration settings.</span></span>

<div>

## <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="da265-106">Pour supprimer les paramètres de configuration d’un service Web</span><span class="sxs-lookup"><span data-stu-id="da265-106">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="da265-107">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da265-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="da265-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="da265-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="da265-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="da265-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="da265-110">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.</span><span class="sxs-lookup"><span data-stu-id="da265-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="da265-111">Dans le champ de recherche de la page **Service web**, tapez l’intégralité ou une partie du nom de la stratégie à supprimer.</span><span class="sxs-lookup"><span data-stu-id="da265-111">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="da265-112">Dans la liste des stratégies, cliquez sur la stratégie que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="da265-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="da265-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="da265-113">Click **OK**.</span></span>

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="da265-114">Suppression des paramètres de configuration des services Web à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="da265-114">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="da265-115">Vous pouvez supprimer les paramètres de configuration des services Web à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsWebServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="da265-115">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="da265-116">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da265-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="da265-117">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="da265-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="da265-118">Pour supprimer une collection de paramètres de configuration des services web</span><span class="sxs-lookup"><span data-stu-id="da265-118">To delete a specific collection of web service configuration settings</span></span>

  - <span data-ttu-id="da265-119">La commande suivante supprime les paramètres de sécurité des services web appliqués au site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="da265-119">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="da265-120">Pour supprimer tous les paramètres de configuration de service Web appliqués à l’étendue site</span><span class="sxs-lookup"><span data-stu-id="da265-120">To delete all of the web service configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="da265-121">La commande suivante supprime tous les paramètres de sécurité des services web appliqués à l’étendue des services :</span><span class="sxs-lookup"><span data-stu-id="da265-121">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="da265-122">Pour supprimer tous les paramètres de configuration de service Web qui autorisent l’authentification de certificats</span><span class="sxs-lookup"><span data-stu-id="da265-122">To delete all of the web service configuration settings that allow certificate authentication</span></span>

  - <span data-ttu-id="da265-123">La commande suivante supprime tous les paramètres de sécurité des services web qui autorisent l’authentification des certificats :</span><span class="sxs-lookup"><span data-stu-id="da265-123">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

<span data-ttu-id="da265-124">Pour plus d’informations, consultez la rubrique [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="da265-124">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da265-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da265-125">See Also</span></span>


[<span data-ttu-id="da265-126">Configuration de l’authentification dans le panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da265-126">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

