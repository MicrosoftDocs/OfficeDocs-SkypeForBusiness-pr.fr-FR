---
title: Test et signalement de la disponibilité fonctionnelle pour l’authentification Kerberos
description: Testez et signalez la préparation fonctionnelle de l’authentification Kerberos.
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
ms.openlocfilehash: 5d32591a8cced7dce2e0bb78cc26189dce1900a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554060"
---
# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="a09a6-103">Test et signalement de la disponibilité fonctionnelle pour l’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a09a6-103">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a09a6-104">_**Dernière modification de la rubrique :** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="a09a6-104">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="a09a6-105">Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a09a6-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="a09a6-106">Vous pouvez utiliser l’applet de commande Windows PowerShell **test-CsKerberosAccountAssignment**   pour tester et signaler la disponibilité fonctionnelle d’une affectation de site pour l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a09a6-106">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="a09a6-107">Cette commande interroge le site spécifié dans le paramètre Identity obligatoire.</span><span class="sxs-lookup"><span data-stu-id="a09a6-107">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="a09a6-108">Le paramètre de rapport facultatif fait en sorte que l’applet de commande écrive un rapport HTML dans C : \\ logs sur l’ordinateur sur lequel la commande est exécutée.</span><span class="sxs-lookup"><span data-stu-id="a09a6-108">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="a09a6-109">Le paramètre Verbose facultatif affiche des informations d’activité à l’écran.</span><span class="sxs-lookup"><span data-stu-id="a09a6-109">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="a09a6-110">Pour tester et signaler la disponibilité fonctionnelle pour l’authentification Kerberos d’un site</span><span class="sxs-lookup"><span data-stu-id="a09a6-110">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="a09a6-111">En tant que membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur du domaine exécutant Lync Server 2013 ou sur l’ordinateur sur lequel les outils d’administration sont installés.</span><span class="sxs-lookup"><span data-stu-id="a09a6-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="a09a6-112">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a09a6-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a09a6-113">Depuis la ligne de commande , exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="a09a6-113">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="a09a6-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a09a6-114">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

