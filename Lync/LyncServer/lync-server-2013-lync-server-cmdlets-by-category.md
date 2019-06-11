---
title: 'Lync Server 2013: cmdlets Lync Server par catégorie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c7a5e0b3fa81d6730caed1f4ce2f89adf0d7d96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a><span data-ttu-id="c3208-102">Applets de cmdlet Lync Server 2013 par catégorie</span><span class="sxs-lookup"><span data-stu-id="c3208-102">Lync Server 2013 cmdlets by category</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3208-103">_**Dernière modification de la rubrique:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="c3208-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<span data-ttu-id="c3208-104">Microsoft Lync Server 2013 est fourni avec une cmdlet presque 550 conçue spécifiquement pour permettre aux administrateurs de gérer Lync Server à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="c3208-104">Microsoft Lync Server 2013 ships with almost 550 cmdlets specifically designed to allow administrators to manage Lync Server from the command line.</span></span> <span data-ttu-id="c3208-105">Vous accédez aux cmdlets à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c3208-105">You access the cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="c3208-106">Vous pouvez obtenir de l’aide sur une cmdlet directement à partir de la ligne de commande en tapant une commande semblable à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="c3208-106">You can retrieve help on a cmdlet directly from the command line by typing a command similar to the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="c3208-107">La commande précédente récupère toutes les rubriques d’aide disponibles pour l’applet de commande **New-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="c3208-107">The preceding command will retrieve all the help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="c3208-108">Remplacez **New-CsVoicePolicy** par le nom de l’applet de recherche pour laquelle vous souhaitez obtenir de l’aide.</span><span class="sxs-lookup"><span data-stu-id="c3208-108">Substitute the reference to **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>

<span data-ttu-id="c3208-109">Pour obtenir la liste complète des applets de commande disponibles pour gérer Microsoft Lync Server 2013, à l’invite de commandes de Lync Server Management Shell, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="c3208-109">To retrieve a full list of cmdlets available for managing Microsoft Lync Server 2013, type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Command * -Module Lync -CommandType cmdlet

<span data-ttu-id="c3208-110">Si vous n’êtes pas sûr des cmdlets dont vous avez besoin, nous avons également fourni une liste classés des cmdlets et leurs rubriques d’aide.</span><span class="sxs-lookup"><span data-stu-id="c3208-110">If you are unsure which cmdlets you need, we have also provided a categorized list of cmdlets and their help topics.</span></span> <span data-ttu-id="c3208-111">Vous constaterez que certaines de ces applets de technologie apparaissent dans plusieurs catégories, ce qui était intentionnel lors de leur application à plusieurs zones du produit.</span><span class="sxs-lookup"><span data-stu-id="c3208-111">You will find that some of the cmdlets show up in more than one category, which was intentional as they apply to multiple areas of the product.</span></span> <span data-ttu-id="c3208-112">La liste suivante répertorie les catégories:</span><span class="sxs-lookup"><span data-stu-id="c3208-112">The following is a list of categories:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c3208-113">Référence sur les applets de la cmdlet Skype entreprise a été déplacée vers docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c3208-113">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="c3208-114">Cliquer sur les liens ci-dessous vous permet d’atteindre la nouvelle page docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c3208-114">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="c3208-115">Le contenu est désormais ouvert et est disponible pour les contributions de la Communauté par le biais de GitHub.</span><span class="sxs-lookup"><span data-stu-id="c3208-115">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="c3208-116">Vous voulez participer?</span><span class="sxs-lookup"><span data-stu-id="c3208-116">Interested in contributing?</span></span> <span data-ttu-id="c3208-117">Consultez le fichier README dans le référentiel Samples:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="c3208-117">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c3208-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c3208-118">In This Section</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3208-119"><a href="lync-server-2013-user-management-cmdlets.md">Cmdlets de gestion des utilisateurs dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-119"><a href="lync-server-2013-user-management-cmdlets.md">User management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c3208-120"><a href="lync-server-2013-voice-application-cmdlets.md">Cmdlets de l’application vocale dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-120"><a href="lync-server-2013-voice-application-cmdlets.md">Voice application cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3208-121"><a href="lync-server-2013-client-management-cmdlets.md">Cmdlets de gestion des clients dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-121"><a href="lync-server-2013-client-management-cmdlets.md">Client management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c3208-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Applets de applet voix entreprise avancées dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-122"><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Advanced Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3208-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">Cmdlets de la messagerie instantanée et de la présence dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-123"><a href="lync-server-2013-im-and-presence-cmdlets.md">IM and presence cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c3208-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Applets de connexion RTC dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-124"><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN connectivity cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3208-125"><a href="lync-server-2013-conferencing-cmdlets.md">Cmdlets de conférence dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-125"><a href="lync-server-2013-conferencing-cmdlets.md">Conferencing cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c3208-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Cmdlets et périphériques de téléphone dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-126"><a href="lync-server-2013-phones-and-devices-cmdlets.md">Phones and devices cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3208-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Cmdlets Infrastructure and Deployment dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-127"><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Infrastructure and deployment cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c3208-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Cmdlets de migration et de coexistence dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-128"><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Migration and coexistence cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3208-129"><a href="lync-server-2013-security-cmdlets.md">Cmdlets de sécurité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-129"><a href="lync-server-2013-security-cmdlets.md">Security cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c3208-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Cmdlets de configuration de Lync Server Management Shell dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-130"><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server Management Shell configuration cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3208-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Applets de service et rôles de serveur dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-131"><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Server roles and services cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c3208-132"><a href="lync-server-2013-mobility-cmdlets.md">Cmdlets de mobilité dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-132"><a href="lync-server-2013-mobility-cmdlets.md">Mobility cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3208-133"><a href="lync-server-2013-application-management-cmdlets.md">Cmdlets de gestion des applications dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-133"><a href="lync-server-2013-application-management-cmdlets.md">Application management cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c3208-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Cmdlets Server chat permanent dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-134"><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Persistent Chat Server cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3208-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Applets de la Fédération et accès externe dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-135"><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Federation and external access cmdlets in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c3208-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Cmdlets d’enregistrement centralisé dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-136"><a href="lync-server-2013-centralized-logging-cmdlets.md">Centralized Logging cmdlets in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3208-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Cmdlets voix entreprise dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c3208-137"><a href="lync-server-2013-enterprise-voice-cmdlets.md">Enterprise Voice cmdlets in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3208-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3208-138">See Also</span></span>


[<span data-ttu-id="c3208-139">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3208-139">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

