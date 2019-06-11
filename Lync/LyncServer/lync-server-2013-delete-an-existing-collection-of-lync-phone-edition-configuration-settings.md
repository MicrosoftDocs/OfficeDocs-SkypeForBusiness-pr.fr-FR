---
title: Supprimer une collection existante de paramètres de configuration de Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2be234fdbb2beb9d2f6f038acbdad03dd8d2048
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="cb600-102">Supprimer une collection existante de paramètres de configuration de Lync Phone Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb600-102">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb600-103">_**Dernière modification de la rubrique:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cb600-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cb600-104">Si vous ne voulez plus utiliser un ensemble de paramètres pour les appareils exécutant Lync Phone Edition, supprimez-le.</span><span class="sxs-lookup"><span data-stu-id="cb600-104">If you no longer want to use a collection of settings for devices running Lync Phone Edition, delete it.</span></span> <span data-ttu-id="cb600-105">Si vous supprimez une collection pour un site, les paramètres globaux s’appliquent aux téléphones de ce site.</span><span class="sxs-lookup"><span data-stu-id="cb600-105">If you delete a collection for a site, the global settings will apply to the phones in that site.</span></span> <span data-ttu-id="cb600-106">Vous ne pouvez pas supprimer la collection globale.</span><span class="sxs-lookup"><span data-stu-id="cb600-106">You cannot delete the global collection.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cb600-107">Au lieu de supprimer une collection, il est possible que vous vouliez simplement modifier certains paramètres.</span><span class="sxs-lookup"><span data-stu-id="cb600-107">Instead of deleting a collection, you might just want to change some of the settings.</span></span> <span data-ttu-id="cb600-108">Pour plus d’informations sur la façon de procéder, voir <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">créer ou modifier un ensemble de paramètres de configuration de Lync Phone Edition dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cb600-108">For details about how to do so, see <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="cb600-109">Pour supprimer une collection de paramètres de configuration de Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="cb600-109">To delete a collection of Lync Phone Edition configuration settings</span></span>

1.  <span data-ttu-id="cb600-110">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="cb600-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cb600-111">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cb600-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cb600-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cb600-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cb600-113">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton navigation de **configuration d’appareil** .</span><span class="sxs-lookup"><span data-stu-id="cb600-113">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="cb600-114">Dans la page Configuration de l' **appareil** , cliquez sur la collection que vous voulez supprimer, cliquez sur le menu **modifier** , puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="cb600-114">On the **Device Configuration** page, click the collection you want to delete, click the **Edit** menu, and then click **Delete**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="cb600-115">Si vous supprimez la collection globale, les paramètres sont restaurés par défaut.</span><span class="sxs-lookup"><span data-stu-id="cb600-115">If you delete the global collection, the settings just revert to the default settings.</span></span> <span data-ttu-id="cb600-116">La collection n’est pas déplacée.</span><span class="sxs-lookup"><span data-stu-id="cb600-116">The collection does not go away.</span></span>

    
    </div>

5.  <span data-ttu-id="cb600-117">Dans la boîte de confirmation, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb600-117">In the confirmation box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cb600-118">Supprimer les paramètres de configuration de Lync Phone Edition en utilisant des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb600-118">Removing Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cb600-119">Vous pouvez supprimer des paramètres de configuration de Lync Phone Edition à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsUCConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="cb600-119">You can delete Lync Phone Edition configuration settings by using Windows PowerShell and the **Remove-CsUCConfiguration** cmdlet.</span></span> <span data-ttu-id="cb600-120">Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb600-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cb600-121">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="cb600-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a><span data-ttu-id="cb600-122">Pour supprimer une collection de paramètres de configuration de Lync Phone Edition spécifiée</span><span class="sxs-lookup"><span data-stu-id="cb600-122">To remove a specified collection of Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="cb600-123">Cette commande supprime les paramètres de configuration de téléphone UC appliqués au site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="cb600-123">This command deletes the UC phone configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="cb600-124">Pour supprimer tous les paramètres de configuration de Lync Phone Edition appliqués à l’étendue du site</span><span class="sxs-lookup"><span data-stu-id="cb600-124">To remove all of the Lync Phone Edition configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="cb600-125">Cette commande supprime tous les paramètres de configuration de téléphone de UC appliqués à l’étendue du service:</span><span class="sxs-lookup"><span data-stu-id="cb600-125">This command removes all the UC phone configuration settings applied to the service scope:</span></span>
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a><span data-ttu-id="cb600-126">Pour supprimer tous les paramètres de configuration de Lync Phone Edition dans lesquels le verrouillage de téléphone est désactivé</span><span class="sxs-lookup"><span data-stu-id="cb600-126">To remove all of the Lync Phone Edition configuration settings where phone locking is disabled</span></span>

  - <span data-ttu-id="cb600-127">Cette commande supprime tous les ensembles de paramètres de configuration du téléphone de type UC pour lesquels le verrouillage du téléphone a été désactivé:</span><span class="sxs-lookup"><span data-stu-id="cb600-127">This command deletes any collection of UC phone configuration settings where phone locking has been disabled:</span></span>
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

<span data-ttu-id="cb600-128">Pour plus d’informations, consultez la rubrique [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="cb600-128">For details, see [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

