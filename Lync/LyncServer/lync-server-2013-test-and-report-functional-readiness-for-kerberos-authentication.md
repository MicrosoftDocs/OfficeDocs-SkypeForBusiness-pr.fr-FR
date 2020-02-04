---
title: Test et signalement de la disponibilité fonctionnelle de l’authentification Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8763203827afd3d14638b68474c4f9bd9d6d0cfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="9d404-102">Test et signalement de la disponibilité fonctionnelle de l’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d404-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d404-103">_**Dernière modification de la rubrique :** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="9d404-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="9d404-104">Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9d404-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="9d404-105">Vous pouvez utiliser l’applet de contrôle Windows PowerShell **test-CsKerberosAccountAssignment** pour tester et signaler la disponibilité fonctionnelle d’une affectation de site pour l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="9d404-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="9d404-106">Cette commande interroge le site spécifié dans le paramètre d’identité obligatoire.</span><span class="sxs-lookup"><span data-stu-id="9d404-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="9d404-107">Le paramètre de rapport facultatif implique que l’applet de commande rédige un rapport HTML\\vers C : logs sur l’ordinateur sur lequel la commande est exécutée.</span><span class="sxs-lookup"><span data-stu-id="9d404-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="9d404-108">Le paramètre facultatif détaillé signale les informations d’activité à l’écran.</span><span class="sxs-lookup"><span data-stu-id="9d404-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="9d404-109">Pour tester et signaler la compatibilité fonctionnelle pour l’authentification Kerberos pour un site</span><span class="sxs-lookup"><span data-stu-id="9d404-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="9d404-110">En tant que membre du groupe RTCUniversalServerAdmins, connectez-vous à un ordinateur du domaine exécutant Lync Server 2013 ou sur l’ordinateur sur lequel les outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="9d404-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="9d404-111">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9d404-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9d404-112">À partir de la ligne de commande, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9d404-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="9d404-113">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9d404-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

