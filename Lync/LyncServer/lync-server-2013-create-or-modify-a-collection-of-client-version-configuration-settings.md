---
title: Créer ou modifier une collection de paramètres de configuration de la version du client
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
ms.openlocfilehash: 6851a332b0b2c33d769328a0656f206d5f7d271c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="0c81e-102">Création ou modification d’une collection de paramètres de configuration de la version du client dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c81e-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c81e-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0c81e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0c81e-104">Les paramètres de configuration de version du client sont utilisés pour activer ou désactiver le contrôle de version du client.</span><span class="sxs-lookup"><span data-stu-id="0c81e-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="0c81e-105">La configuration de la version du client globale s’installe avec Lync Server et est utilisée pour activer ou désactiver le contrôle de version du client pour l’ensemble du déploiement du serveur.</span><span class="sxs-lookup"><span data-stu-id="0c81e-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="0c81e-106">Vous pouvez également configurer les paramètres de configuration de la version du client pour des sites individuels.</span><span class="sxs-lookup"><span data-stu-id="0c81e-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="0c81e-107">Vous pouvez créer ou modifier les paramètres de configuration de la version du client à partir du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0c81e-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="0c81e-108">Comme ils ne sont pas associés à un utilisateur, un site ou un service spécifiques, les utilisateurs anonymes sont uniquement affectés par les stratégies globales.</span><span class="sxs-lookup"><span data-stu-id="0c81e-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="0c81e-109">Pour créer ou modifier des paramètres de configuration de la version du client à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="0c81e-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0c81e-110">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0c81e-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0c81e-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0c81e-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0c81e-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0c81e-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0c81e-113">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de la **version du client** .</span><span class="sxs-lookup"><span data-stu-id="0c81e-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="0c81e-114">Sur la page Configuration de la **version du client** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0c81e-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="0c81e-115">Pour créer une nouvelle configuration, cliquez sur **nouveau**, sélectionnez un site, cliquez sur **OK** , puis mettez à jour les paramètres.</span><span class="sxs-lookup"><span data-stu-id="0c81e-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="0c81e-116">Pour modifier une configuration, sélectionnez la configuration, cliquez sur **modifier**, sur **afficher les détails**, puis apportez des modifications aux paramètres.</span><span class="sxs-lookup"><span data-stu-id="0c81e-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0c81e-117">Création ou modification des paramètres de configuration de la version du client à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c81e-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0c81e-118">Vous pouvez créer des paramètres de configuration de version des clients à l’aide de la cmdlet **New-CsClientVersionConfiguration** et les modifier à l’aide de l’applet de commande **Set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0c81e-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="0c81e-119">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c81e-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0c81e-120">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0c81e-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="0c81e-121">Pour créer une nouvelle collection de paramètres de configuration de la version du client</span><span class="sxs-lookup"><span data-stu-id="0c81e-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="0c81e-122">La commande suivante crée une nouvelle collection de paramètres de configuration de la version du client appliqués au site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="0c81e-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="0c81e-123">Dans cet exemple, le contrôle de version du client est désactivé pour le site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="0c81e-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="0c81e-124">Pour activer le contrôle de version du client pour un site</span><span class="sxs-lookup"><span data-stu-id="0c81e-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="0c81e-125">Cette commande active le contrôle de version du client pour le site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="0c81e-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="0c81e-126">Pour désactiver la gestion des versions du client au sein de l’Organisation</span><span class="sxs-lookup"><span data-stu-id="0c81e-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="0c81e-127">Dans cet exemple, le contrôle de version du client est désactivé pour tous les paramètres de configuration de la version du client utilisés dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="0c81e-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="0c81e-128">Pour plus d’informations, consultez la rubrique d’aide relative aux applets de commande [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) et [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="0c81e-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

