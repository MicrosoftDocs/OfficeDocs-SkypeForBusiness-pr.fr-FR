---
title: Supprimer une collection existante de paramètres de configuration de Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce796b13ea69296fa72799a13d35cb2046a643b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514631"
---
# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6fe33-102">Supprimer une collection existante de paramètres de configuration Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe33-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fe33-103">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6fe33-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6fe33-104">Si vous ne souhaitez plus utiliser une collection de paramètres pour les appareils exécutant Lync Phone Edition, supprimez-le.</span><span class="sxs-lookup"><span data-stu-id="6fe33-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="6fe33-105">Si vous supprimez la collection de paramètres d’un site, les paramètres globaux s’appliqueront aux téléphones de ce site.</span><span class="sxs-lookup"><span data-stu-id="6fe33-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="6fe33-106">Vous ne pouvez pas supprimer la collection globale.</span><span class="sxs-lookup"><span data-stu-id="6fe33-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6fe33-107">Au lieu de supprimer une collection, vous pouvez simplement modifier certains des paramètres.</span><span class="sxs-lookup"><span data-stu-id="6fe33-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="6fe33-108">Pour plus d’informations sur la procédure à suivre, voir <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">créer ou modifier une collection de paramètres de configuration de Lync Phone Edition dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6fe33-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="6fe33-109">Pour supprimer une collection de paramètres de configuration de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="6fe33-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="6fe33-110">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="6fe33-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6fe33-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fe33-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6fe33-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6fe33-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6fe33-113">Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration du périphérique**.</span><span class="sxs-lookup"><span data-stu-id="6fe33-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="6fe33-114">Dans la page **Configuration du périphérique**, cliquez sur la collection à supprimer, sur le menu **Edition**, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6fe33-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6fe33-p104">Si vous supprimez la collection globale, les paramètres par défaut sont simplement rétablis. La collection ne disparaît pas.</span><span class="sxs-lookup"><span data-stu-id="6fe33-p104">If you delete the global collection, the settings just revert to the default settings. The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="6fe33-117">Dans la boîte de dialogue de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6fe33-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6fe33-118">Suppression des paramètres de configuration de Lync Phone Edition à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fe33-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6fe33-119">Vous pouvez supprimer les paramètres de configuration de Lync Phone Edition à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsUCConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="6fe33-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="6fe33-120">Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fe33-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6fe33-121">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="6fe33-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="6fe33-122">Pour supprimer une collection spécifique de paramètres de configuration de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="6fe33-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="6fe33-123">Cette commande permet de supprimer les paramètres de configuration du téléphone pour messagerie unifiée appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="6fe33-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="6fe33-124">Pour supprimer tous les paramètres de configuration de Lync Phone Edition appliqués à l’étendue site</span><span class="sxs-lookup"><span data-stu-id="6fe33-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="6fe33-125">Cette commande permet de supprimer tous les paramètres de configuration du téléphone pour messagerie unifiée appliqués à l’étendue Service :</span><span class="sxs-lookup"><span data-stu-id="6fe33-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="6fe33-126">Pour supprimer tous les paramètres de configuration de Lync Phone Edition où le verrouillage du téléphone est désactivé</span><span class="sxs-lookup"><span data-stu-id="6fe33-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="6fe33-127">Cette commande permet de supprimer les collections de paramètres de configuration du téléphone pour messagerie unifiée dans lesquels le verrouillage du téléphone a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="6fe33-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="6fe33-128">Pour plus d’informations, consultez la rubrique [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="6fe33-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

