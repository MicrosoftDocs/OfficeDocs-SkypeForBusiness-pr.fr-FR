---
title: 'Lync Server 2013 : configuration requise pour les services Internet (IIS)'
description: 'Lync Server 2013 : configuration requise pour les services Internet (IIS).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8de55fa4611c3ab29eac7d7c28c522b418e77d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543990"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="7e39b-103">Configuration requise pour les services Internet (IIS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e39b-103">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e39b-104">_**Dernière modification de la rubrique :** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="7e39b-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="7e39b-105">Plusieurs composants Lync Server 2013 nécessitent Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="7e39b-105">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="7e39b-106">Cette rubrique décrit les fonctionnalités IIS spécifiques requises pour prendre en charge Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7e39b-106">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="7e39b-107">Les rubriques de cette section présentent les exigences relatives à certains composants pour IIS.</span><span class="sxs-lookup"><span data-stu-id="7e39b-107">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="7e39b-p102">Lorsque le rôle serveur web (IIS) est activé sur Windows Server 2008, divers services de rôle sont installés par défaut. Le tableau suivant décrit les services de rôle supplémentaires devant être installés lorsque le rôle serveur web (IIS) est activé sur Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="7e39b-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e39b-110">Service de rôle</span><span class="sxs-lookup"><span data-stu-id="7e39b-110">Role service</span></span></th>
<th><span data-ttu-id="7e39b-111">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="7e39b-111">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e39b-112">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="7e39b-112">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="7e39b-113">Redirection HTTP</span><span class="sxs-lookup"><span data-stu-id="7e39b-113">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e39b-114">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="7e39b-114">Application Development</span></span></p></td>
<td><p><span data-ttu-id="7e39b-115">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7e39b-115">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e39b-116">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="7e39b-116">Application Development</span></span></p></td>
<td><p><span data-ttu-id="7e39b-117">Extensibilité .NET</span><span class="sxs-lookup"><span data-stu-id="7e39b-117">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e39b-118">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="7e39b-118">Application Development</span></span></p></td>
<td><p><span data-ttu-id="7e39b-119">Extensions ISAPI</span><span class="sxs-lookup"><span data-stu-id="7e39b-119">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e39b-120">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="7e39b-120">Application Development</span></span></p></td>
<td><p><span data-ttu-id="7e39b-121">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="7e39b-121">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e39b-122">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="7e39b-122">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="7e39b-123">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="7e39b-123">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e39b-124">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="7e39b-124">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="7e39b-125">Analyzer</span><span class="sxs-lookup"><span data-stu-id="7e39b-125">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e39b-126">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7e39b-126">Security</span></span></p></td>
<td><p><span data-ttu-id="7e39b-127">Authentification de base</span><span class="sxs-lookup"><span data-stu-id="7e39b-127">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e39b-128">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7e39b-128">Security</span></span></p></td>
<td><p><span data-ttu-id="7e39b-129">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="7e39b-129">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e39b-130">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="7e39b-130">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="7e39b-131">Scripts et outils de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="7e39b-131">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e39b-132">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="7e39b-132">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="7e39b-133">Compatibilité avec la gestion IIS 6</span><span class="sxs-lookup"><span data-stu-id="7e39b-133">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" /><span data-ttu-id="7e39b-135">Note de sécurité :</span><span class="sxs-lookup"><span data-stu-id="7e39b-135">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7e39b-136">Si vous utilisez IIS 7,0 sur un système d’exploitation Windows Server 2008, le programme d’installation de Lync Server désactive l’authentification en mode noyau dans les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="7e39b-136">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7e39b-137">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7e39b-137">In This Section</span></span>

  - [<span data-ttu-id="7e39b-138">Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e39b-138">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

