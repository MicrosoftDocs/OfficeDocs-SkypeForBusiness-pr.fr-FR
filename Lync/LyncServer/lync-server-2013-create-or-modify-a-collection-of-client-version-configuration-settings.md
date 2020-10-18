---
title: Créer ou modifier une collection de paramètres de configuration de la version du client
description: Créez ou modifiez une collection de paramètres de configuration de la version du client.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0082b618b8417c9d0da44599f1606cd238dfd7e8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578310"
---
# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="39feb-103">Création ou modification d’une collection de paramètres de configuration de la version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39feb-103">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39feb-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="39feb-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="39feb-105">Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client.</span><span class="sxs-lookup"><span data-stu-id="39feb-105">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="39feb-106">La configuration de la version du client globale s’installe avec Lync Server et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur.</span><span class="sxs-lookup"><span data-stu-id="39feb-106">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="39feb-107">Vous pouvez également configurer les paramètres de configuration de la version du client pour des sites individuels.</span><span class="sxs-lookup"><span data-stu-id="39feb-107">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="39feb-108">Vous pouvez créer ou modifier les paramètres de configuration de la version du client à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="39feb-108">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="39feb-109">Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="39feb-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="39feb-110">Pour créer ou modifier des paramètres de configuration de la version du client à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="39feb-110">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="39feb-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="39feb-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="39feb-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="39feb-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="39feb-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="39feb-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="39feb-114">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .</span><span class="sxs-lookup"><span data-stu-id="39feb-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="39feb-115">Sur la page Configuration de la **version du client** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="39feb-115">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="39feb-116">Pour créer une nouvelle configuration, cliquez sur **nouveau**, sélectionnez un site, cliquez sur **OK** , puis mettez à jour les paramètres.</span><span class="sxs-lookup"><span data-stu-id="39feb-116">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="39feb-117">Pour modifier une configuration, sélectionnez la configuration, cliquez sur **modifier**, sur **afficher les détails**, puis apportez des modifications aux paramètres.</span><span class="sxs-lookup"><span data-stu-id="39feb-117">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="39feb-118">Création ou modification des paramètres de configuration de la version du client à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="39feb-118">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="39feb-119">Vous pouvez créer des paramètres de configuration de version des clients à l’aide de la cmdlet **New-CsClientVersionConfiguration** et les modifier à l’aide de l’applet de commande **Set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="39feb-119">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="39feb-120">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39feb-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="39feb-121">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="39feb-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="39feb-122">Pour créer une nouvelle collection de paramètres de configuration de la version du client</span><span class="sxs-lookup"><span data-stu-id="39feb-122">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="39feb-123">La commande suivante crée une nouvelle collection de paramètres de configuration de la version du client appliqués au site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="39feb-123">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="39feb-124">Dans cet exemple, le contrôle de version du client est désactivé pour le site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="39feb-124">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="39feb-125">Pour activer le contrôle de version du client pour un site</span><span class="sxs-lookup"><span data-stu-id="39feb-125">To enable client versioning for a site</span></span>

  - <span data-ttu-id="39feb-126">Cette commande active le contrôle de version du client pour le site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="39feb-126">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="39feb-127">Pour désactiver la gestion des versions du client au sein de l’Organisation</span><span class="sxs-lookup"><span data-stu-id="39feb-127">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="39feb-128">Dans cet exemple, le contrôle de version du client est désactivé pour tous les paramètres de configuration de la version du client utilisés dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="39feb-128">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="39feb-129">Pour plus d’informations, consultez la rubrique d’aide relative aux applets de commande [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) et [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="39feb-129">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

