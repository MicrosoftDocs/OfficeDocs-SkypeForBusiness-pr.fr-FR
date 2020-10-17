---
title: 'Lync Server 2013 : afficher les paramètres de configuration de la version du client'
description: 'Lync Server 2013 : afficher les paramètres de configuration de la version du client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04fc25a1ab4904cbc6ca7871e1568ac8bc488bdf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572500"
---
# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f5bc3-103">Afficher les paramètres de configuration de la version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5bc3-103">View client version configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5bc3-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f5bc3-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f5bc3-105">Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client.</span><span class="sxs-lookup"><span data-stu-id="f5bc3-105">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="f5bc3-106">La configuration de la version du client global s’installe avec Lync Server 2013 et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur.</span><span class="sxs-lookup"><span data-stu-id="f5bc3-106">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="f5bc3-107">Lorsque la configuration globale est activée, toutes les stratégies de version du client qui sont en place prendront effet lorsque les utilisateurs tenteront de se connecter.</span><span class="sxs-lookup"><span data-stu-id="f5bc3-107">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="f5bc3-108">Vous pouvez afficher les paramètres de configuration de la version du client à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f5bc3-108">You can view client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f5bc3-109">Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="f5bc3-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="f5bc3-110">Pour afficher les paramètres de configuration de la version du client à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="f5bc3-110">To view client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f5bc3-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f5bc3-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f5bc3-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5bc3-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f5bc3-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f5bc3-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f5bc3-114">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .</span><span class="sxs-lookup"><span data-stu-id="f5bc3-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="f5bc3-115">Double-cliquez sur le nom de la version du client que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="f5bc3-115">Double-click the name of the client version configuration you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f5bc3-116">Affichage des paramètres de configuration de version des clients à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5bc3-116">Viewing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f5bc3-117">Vous pouvez afficher les paramètres de configuration de la version du client à l’aide de la cmdlet **Get-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f5bc3-117">You can view client version configuration settings by using the **Get-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="f5bc3-118">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f5bc3-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f5bc3-119">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="f5bc3-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-configuration-information"></a><span data-ttu-id="f5bc3-120">Pour afficher les informations de configuration de la version du client</span><span class="sxs-lookup"><span data-stu-id="f5bc3-120">To view client version configuration information</span></span>

  - <span data-ttu-id="f5bc3-121">Pour afficher des informations sur tous les paramètres de configuration de la version du client, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="f5bc3-121">To view information about all your client version configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionConfiguration
    
    <span data-ttu-id="f5bc3-122">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f5bc3-122">That will return information similar to this:</span></span>
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

<span data-ttu-id="f5bc3-123">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="f5bc3-123">For details, see the Help topic for the [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

