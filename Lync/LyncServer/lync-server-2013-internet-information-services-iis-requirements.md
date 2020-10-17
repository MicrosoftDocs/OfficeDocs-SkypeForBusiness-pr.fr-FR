---
title: 'Lync Server 2013 : configuration requise pour les services Internet (IIS)'
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
ms.openlocfilehash: 3b0c1c9966945554af6d1d9cec02a17dd884a857
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498481"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="bfd8a-102">Configuration requise pour les services Internet (IIS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfd8a-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfd8a-103">_**Dernière modification de la rubrique :** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="bfd8a-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="bfd8a-104">Plusieurs composants Lync Server 2013 nécessitent Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="bfd8a-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="bfd8a-105">Cette rubrique décrit les fonctionnalités IIS spécifiques requises pour prendre en charge Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="bfd8a-106">Les rubriques de cette section présentent les exigences relatives à certains composants pour IIS.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="bfd8a-p102">Lorsque le rôle serveur web (IIS) est activé sur Windows Server 2008, divers services de rôle sont installés par défaut. Le tableau suivant décrit les services de rôle supplémentaires devant être installés lorsque le rôle serveur web (IIS) est activé sur Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="bfd8a-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfd8a-109">Service de rôle</span><span class="sxs-lookup"><span data-stu-id="bfd8a-109">Role service</span></span></th>
<th><span data-ttu-id="bfd8a-110">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="bfd8a-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfd8a-111">Fonctionnalités HTTP communes</span><span class="sxs-lookup"><span data-stu-id="bfd8a-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-112">Redirection HTTP</span><span class="sxs-lookup"><span data-stu-id="bfd8a-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfd8a-113">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="bfd8a-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="bfd8a-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfd8a-115">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="bfd8a-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-116">Extensibilité .NET</span><span class="sxs-lookup"><span data-stu-id="bfd8a-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfd8a-117">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="bfd8a-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-118">Extensions ISAPI</span><span class="sxs-lookup"><span data-stu-id="bfd8a-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfd8a-119">Développement d’applications</span><span class="sxs-lookup"><span data-stu-id="bfd8a-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-120">Filtres ISAPI</span><span class="sxs-lookup"><span data-stu-id="bfd8a-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfd8a-121">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="bfd8a-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-122">Outils de journalisation</span><span class="sxs-lookup"><span data-stu-id="bfd8a-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfd8a-123">État de santé et diagnostics</span><span class="sxs-lookup"><span data-stu-id="bfd8a-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-124">Analyzer</span><span class="sxs-lookup"><span data-stu-id="bfd8a-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfd8a-125">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bfd8a-125">Security</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-126">Authentification de base</span><span class="sxs-lookup"><span data-stu-id="bfd8a-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfd8a-127">Sécurité</span><span class="sxs-lookup"><span data-stu-id="bfd8a-127">Security</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-128">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="bfd8a-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfd8a-129">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="bfd8a-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-130">Scripts et outils de gestion IIS</span><span class="sxs-lookup"><span data-stu-id="bfd8a-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfd8a-131">Outils de gestion</span><span class="sxs-lookup"><span data-stu-id="bfd8a-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="bfd8a-132">Compatibilité avec la gestion IIS 6</span><span class="sxs-lookup"><span data-stu-id="bfd8a-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" /><span data-ttu-id="bfd8a-134">Note de sécurité :</span><span class="sxs-lookup"><span data-stu-id="bfd8a-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bfd8a-135">Si vous utilisez IIS 7,0 sur un système d’exploitation Windows Server 2008, le programme d’installation de Lync Server désactive l’authentification en mode noyau dans les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="bfd8a-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bfd8a-136">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bfd8a-136">In This Section</span></span>

  - [<span data-ttu-id="bfd8a-137">Configuration requise pour les services Internet (IIS) pour les pools frontaux et les serveurs Standard Edition dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfd8a-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

