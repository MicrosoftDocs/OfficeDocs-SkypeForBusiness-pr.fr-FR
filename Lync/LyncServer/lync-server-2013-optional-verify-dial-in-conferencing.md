---
title: 'Lync Server 2013 : (facultatif) vérifier la Conférence rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 133d0bccb919e537998878306b3bbf85d77bd0cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="529aa-102">Module Vérifier les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="529aa-102">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="529aa-103">_**Dernière modification de la rubrique :** 2011-01-21_</span><span class="sxs-lookup"><span data-stu-id="529aa-103">_**Topic Last Modified:** 2011-01-21_</span></span>

<span data-ttu-id="529aa-104">Pour vérifier que la page web Paramètres de conférence rendez-vous et les numéros d’accès entrants fonctionnent correctement, vous devez :</span><span class="sxs-lookup"><span data-stu-id="529aa-104">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>

  - <span data-ttu-id="529aa-105">tester la page web Paramètres de conférence rendez-vous en vous connectant à l’URL simple ;</span><span class="sxs-lookup"><span data-stu-id="529aa-105">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>

  - <span data-ttu-id="529aa-p101">tester les numéros d’accès d’un pool spécifique en exécutant le script présenté plus loin dans cette rubrique. Ce script simule les appels vers les numéros d’accès. Pour l’utiliser, vous devez disposer de l’adresse SIP et des informations d’identification de l’un des clients de communications unifiées hébergés sur le pool.</span><span class="sxs-lookup"><span data-stu-id="529aa-p101">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>

<span data-ttu-id="529aa-109">Cette étape est facultative.</span><span class="sxs-lookup"><span data-stu-id="529aa-109">This step is optional.</span></span>

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="529aa-110">Pour tester les numéros d’accès à un pool spécifique</span><span class="sxs-lookup"><span data-stu-id="529aa-110">To test access numbers for a specific pool</span></span>

1.  <span data-ttu-id="529aa-111">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-ServerAdministratorr** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="529aa-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="529aa-112">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="529aa-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="529aa-113">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="529aa-113">Run the following at the command prompt:</span></span>
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    <span data-ttu-id="529aa-p102">Le rapport obtenu indique Opération réussie ou Échec ainsi que des informations de diagnostic. L’indicateur -Verbose permet d’obtenir des informations plus détaillées ainsi que le nombre de numéros d’accès trouvés.</span><span class="sxs-lookup"><span data-stu-id="529aa-p102">The resulting report shows either Success or Failure, along with specific diagnostic information. The –Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

