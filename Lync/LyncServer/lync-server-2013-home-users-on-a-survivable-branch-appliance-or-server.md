---
title: 'Lync Server 2013 : Hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Home users on a Survivable Branch Appliance or Server
ms:assetid: faf1ebb9-6d7d-4a58-8ff7-801b7b31d3ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413066(v=OCS.15)
ms:contentKeyID: 48185926
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceabf8fe7d8f9068e60bbc20406d2496f815b04b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="home-users-on-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="634c5-102">Hébergement des utilisateurs sur un Survivable Branch Appliance ou un serveur Survivable Branch Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="634c5-102">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="634c5-103">_**Dernière modification de la rubrique:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="634c5-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="634c5-104">Le processus d’hébergement des utilisateurs sur une unité de branchement survivant ou un serveur de succursale survivant est similaire au processus d’hébergement des utilisateurs sur un pool frontal.</span><span class="sxs-lookup"><span data-stu-id="634c5-104">The process of homing users on a Survivable Branch Appliance or a Survivable Branch Server is similar to the process of homing users on a Front End pool.</span></span> <span data-ttu-id="634c5-105">Exécutez l’application branche Survivable ou le serveur de succursales survivant sur le site central.</span><span class="sxs-lookup"><span data-stu-id="634c5-105">Perform the Survivable Branch Appliance or Survivable Branch Server procedure at the central site.</span></span>

<div>

## <a name="to-home-users-on-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="634c5-106">Pour les particuliers sur un appareil de succursale survivant ou un serveur de succursales survivant</span><span class="sxs-lookup"><span data-stu-id="634c5-106">To home users on Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="634c5-107">Avant de déplacer des utilisateurs vers un serveur de succursales ou un serveur de succursales survivant, ouvrez Lync Server Management Shell, puis effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="634c5-107">Before moving users to the Survivable Branch Server or Survivable Branch Server, open the Lync Server Management Shell, and then do all of the following:</span></span>
    
      - <span data-ttu-id="634c5-108">Exécutez l’applet de **contrôle test-CsPstnOutboundCall** pour vérifier que le serveur de succursales survivant est en cours d’exécution et que la connectivité PSTN (réseau téléphonique commuté) est configurée.</span><span class="sxs-lookup"><span data-stu-id="634c5-108">Run the cmdlet **Test-CsPstnOutboundCall** to verify that the Survivable Branch Server is running and that the public switched telephone network (PSTN) connectivity is configured.</span></span> <span data-ttu-id="634c5-109">Si vous devez modifier les propriétés de la passerelle RTC, utilisez la cmdlet **Set-CsPstnGateway**.</span><span class="sxs-lookup"><span data-stu-id="634c5-109">If you need to modify PSTN gateway properties, use the cmdlet **Set-CsPstnGateway**.</span></span>
    
      - <span data-ttu-id="634c5-110">Exécutez l’applet de contrôle **Get-CsVoicePolicy** pour vérifier que les utilisateurs qui sont hébergés sur le serveur de succursales survivables disposent de la stratégie de routage de VoIP appropriée.</span><span class="sxs-lookup"><span data-stu-id="634c5-110">Run the cmdlet **Get-CsVoicePolicy** to verify that the users who will be homed on the Survivable Branch Server have the appropriate VoIP routing policy.</span></span> <span data-ttu-id="634c5-111">Si vous avez besoin de modifier la stratégie VoIP, utilisez la cmdlet **Set-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="634c5-111">If you need to modify the VoIP policy, use the cmdlet **Set-CsVoicePolicy**.</span></span>
    
      - <span data-ttu-id="634c5-112">Exécutez l’applet de contrôle **Get-CsVoicemailReroutingConfiguration** pour vérifier que les paramètres de reroutage de la messagerie vocale sont configurés.</span><span class="sxs-lookup"><span data-stu-id="634c5-112">Run the cmdlet **Get-CsVoicemailReroutingConfiguration** to verify that the voice mail rerouting settings are configured.</span></span> <span data-ttu-id="634c5-113">Si vous devez modifier les paramètres de redirection de la messagerie vocale, utilisez la cmdlet **Set-CsVoicemailReroutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="634c5-113">If you need to modify the voice mail rerouting settings, use the cmdlet **Set-CsVoicemailReroutingConfiguration**.</span></span>

2.  <span data-ttu-id="634c5-114">Dans Lync Server Management Shell, exécutez l’applet de l’applet de **Csuser** pour déplacer les utilisateurs de l’accueil.</span><span class="sxs-lookup"><span data-stu-id="634c5-114">In the Lync Server Management Shell, run the cmdlet **Move-CsUser** to move home users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="634c5-115">Vous pouvez également utiliser le panneau de configuration de Lync Server pour vérifier les prérequis et les particuliers.</span><span class="sxs-lookup"><span data-stu-id="634c5-115">You can also use Lync Server Control Panel to verify prerequisites and home users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="634c5-116">Les utilisateurs qui sont hébergés sur une unité de branchement Survivable Lync Server ne peuvent pas créer de nouvelles salles de conversation ou afficher la carte de la salle pour les salles existantes.</span><span class="sxs-lookup"><span data-stu-id="634c5-116">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="634c5-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="634c5-117">See Also</span></span>


[<span data-ttu-id="634c5-118">Test-CsPstnOutboundCall</span><span class="sxs-lookup"><span data-stu-id="634c5-118">Test-CsPstnOutboundCall</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall)  
[<span data-ttu-id="634c5-119">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="634c5-119">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="634c5-120">Get-CsVoicemailReroutingConfiguration</span><span class="sxs-lookup"><span data-stu-id="634c5-120">Get-CsVoicemailReroutingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicemailReroutingConfiguration)  
[<span data-ttu-id="634c5-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="634c5-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

