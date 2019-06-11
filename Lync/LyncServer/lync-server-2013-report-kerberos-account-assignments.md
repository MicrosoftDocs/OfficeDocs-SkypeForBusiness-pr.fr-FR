---
title: 'Lync Server 2013 : Consignation des affectations de comptes Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02eb3cae7a7d2bbeb4cc3b9dce0a7daa8ee5c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="67a67-102">Consignation des affectations de comptes Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67a67-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67a67-103">_**Dernière modification de la rubrique:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="67a67-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="67a67-104">Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="67a67-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="67a67-105">Vous pouvez utiliser l’applet de requête **Get-CsKerberosAccountAssignment** pour rechercher des informations sur les affectations de compte d’authentification Kerberos et des informations de rapport sur les affectations actuelles dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="67a67-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="67a67-106">Pour interroger les affectations de compte d’authentification Kerberos pour un site</span><span class="sxs-lookup"><span data-stu-id="67a67-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="67a67-107">En tant que membre du groupe RTCUniversalServerAdmins, connectez-vous à un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="67a67-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="67a67-108">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="67a67-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="67a67-109">À partir de la ligne de commande, exécutez l’une des commandes suivantes:</span><span class="sxs-lookup"><span data-stu-id="67a67-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="67a67-110">Pour interroger toutes les affectations de compte d’authentification Kerberos au sein de votre organisation et retourner des informations d’attribution sur chacun d’eux, exécutez l’applet de requête sans paramètres:</span><span class="sxs-lookup"><span data-stu-id="67a67-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="67a67-111">Pour interroger toutes les affectations de compte d’authentification Kerberos dans votre déploiement et retourner les informations d’affectation de site sur chacun d’eux, exécutez l’applet de requête avec le paramètre Identity:</span><span class="sxs-lookup"><span data-stu-id="67a67-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="67a67-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="67a67-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="67a67-113">Pour interroger toutes les affectations de compte d’authentification Kerberos dans un site unique et retourner les informations d’affectation de chacune d’elles, exécutez l’applet de requête avec le paramètre de filtre:</span><span class="sxs-lookup"><span data-stu-id="67a67-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="67a67-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="67a67-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="67a67-115">Si vous spécifiez \* SiteName pour le paramètre de filtre, les informations relatives à tous les sites contenant le nom de site spécifié n’importe où dans l’identificateur de site (par exemple, tous les sites contenant la chaîne Redmond dans l’identificateur de site).</span><span class="sxs-lookup"><span data-stu-id="67a67-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

