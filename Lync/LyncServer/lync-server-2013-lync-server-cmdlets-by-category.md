---
title: 'Lync Server 2013 : applets de commande Lync Server par catégorie'
description: 'Lync Server 2013 : applets de commande Lync Server par catégorie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df562bd11d54c9ecda4fe3d6172ed1d8bd2627d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571870"
---
# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="5dd9a-103">Applets de commande Lync Server 2013 par catégorie</span><span class="sxs-lookup"><span data-stu-id="5dd9a-103">Lync Server 2013 cmdlets by category</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dd9a-104">_**Dernière modification de la rubrique :** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="5dd9a-104">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="5dd9a-105">Microsoft Lync Server 2013 est livré avec presque 550 cmdlets spécialement conçues pour permettre aux administrateurs de gérer Lync Server à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="5dd9a-105">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="5dd9a-106">Vous accédez aux applets de commande à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5dd9a-106">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="5dd9a-107">Vous pouvez obtenir de l’aide sur une applet de commande directement à partir de la ligne de commande en tapant une commande similaire à la suivante :</span><span class="sxs-lookup"><span data-stu-id="5dd9a-107">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="5dd9a-108">La commande précédente récupérera toute l’aide disponible pour l’applet de commande **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="5dd9a-108">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="5dd9a-109">Remplacez la référence à **New-CsVoicePolicy** par le nom de l’applet de commande pour laquelle vous souhaitez obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="5dd9a-109">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="5dd9a-110">Pour récupérer la liste complète des applets de commande disponibles pour la gestion de Microsoft Lync Server 2013, tapez ce qui suit à l’invite de commandes Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="5dd9a-110">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="5dd9a-p103">Si vous ne savez pas exactement de quelles applets de commande vous avez besoin, vous disposez aussi d’une liste d’applets de commande classées par catégories et de leurs rubriques d’aide. Vous remarquerez également que certaines applets de commande apparaissent dans plusieurs catégories, ce qui est normal puisqu’elles s’appliquent à plusieurs zones du produit. Vous trouverez ci-dessous une liste des catégories :</span><span class="sxs-lookup"><span data-stu-id="5dd9a-p103">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics. You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product. The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5dd9a-114">La référence de cmdlet Skype entreprise a été déplacée vers docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5dd9a-114">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="5dd9a-115">Cliquez sur les liens ci-dessous pour accéder à la nouvelle page docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5dd9a-115">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="5dd9a-116">Le contenu est désormais ouvert et disponible pour les contributions de la Communauté via GitHub.</span><span class="sxs-lookup"><span data-stu-id="5dd9a-116">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="5dd9a-117">Vous souhaitez contribuer ?</span><span class="sxs-lookup"><span data-stu-id="5dd9a-117">Interested in contributing?</span></span> <span data-ttu-id="5dd9a-118">Consultez le fichier Lisez-moi dans le référentiel ici : <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="5dd9a-118">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5dd9a-119">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5dd9a-119">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dd9a-120"><a href="lync-server-2013-user-management-cmdlets.md">Applets de commande de gestion des utilisateurs dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-120"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5dd9a-121"><a href="lync-server-2013-voice-application-cmdlets.md">Applets de commande pour les applications vocales dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-121"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd9a-122"><a href="lync-server-2013-client-management-cmdlets.md">Applets de commande de gestion des clients dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-122"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5dd9a-123"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Applets de commande voix entreprise avancées dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-123"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd9a-124"><a href="lync-server-2013-im-and-presence-cmdlets.md">Applets de commande de messagerie instantanée et de présence dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-124"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5dd9a-125"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Applets de commande de connectivité PSTN dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-125"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd9a-126"><a href="lync-server-2013-conferencing-cmdlets.md">Applets de commande de conférence dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-126"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5dd9a-127"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Applets de commande de téléphones et de périphériques dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-127"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd9a-128"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Applets de commande d’infrastructure et de déploiement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-128"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5dd9a-129"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Applets de commande de migration et de coexistence dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-129"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd9a-130"><a href="lync-server-2013-security-cmdlets.md">Cmdlets de sécurité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-130"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5dd9a-131"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Applets de commande de configuration de Lync Server Management Shell dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-131"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd9a-132"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Applets de commande de services et de rôles serveur dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-132"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5dd9a-133"><a href="lync-server-2013-mobility-cmdlets.md">Applets de commande de mobilité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-133"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd9a-134"><a href="lync-server-2013-application-management-cmdlets.md">Applets de commande de gestion des applications dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-134"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5dd9a-135"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Applets de commande de serveur de conversation permanente dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-135"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd9a-136"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Cmdlets de Fédération et d’accès externe dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-136"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="5dd9a-137"><a href="lync-server-2013-centralized-logging-cmdlets.md">Cmdlets de journalisation centralisée dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-137"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd9a-138"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Applets de commande voix entreprise dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5dd9a-138"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5dd9a-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5dd9a-139">See Also</span></span>


[<span data-ttu-id="5dd9a-140">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="5dd9a-140">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

